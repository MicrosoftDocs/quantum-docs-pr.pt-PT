---
title: Estimativa de recursos do kit de desenvolvimento quântico
description: Conheça o Estimativador de Recursos, que estima os recursos necessários para executar uma determinada instância de uma operação Q# num computador quântico.
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 01d242ed405bdd326f65e534f82ff378a464ee7d
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426866"
---
# <a name="the-resources-estimator-target-machine"></a>A Máquina-Alvo do Estimador de Recursos

Como o nome indica, as `ResourcesEstimator` estimativas dos recursos necessários para executar uma determinada instância de uma operação Q# num computador quântico.
Consegue-o executando a operação quântica sem simular o estado de um computador quântico; por esta razão, pode estimar recursos para operações Q# que usam milhares de qubits, se a parte clássica do código pode ser executada em um tempo razoável.

## <a name="usage"></a>Utilização

É `ResourcesEstimator` apenas mais um tipo de máquina-alvo, pelo que pode ser usada para executar qualquer operação Q#. 

Como outras máquinas-alvo, usá-lo num programa de anfitriões C# criar uma instância e passá-la como o primeiro parâmetro do método da `Run` operação:

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();
            Console.WriteLine(estimator.ToTSV());
        }
    }
}
```

Como o exemplo mostra, o `ResourcesEstimator` fornece um método para gerar uma tabela com `ToTSV()` valores separados (TSV) que podem ser guardados num ficheiro ou escritos na consola para análise. A saída do programa acima deve ser algo assim:

```Output
Metric          Sum
CNOT            1000
QubitClifford   1000
R               0
Measure         4002
T               0
Depth           0
Width           2
BorrowedWidth   0
```

> [!NOTE]
> O `ResourcesEstimator` não reinicia os seus cálculos em cada execução, se a mesma instância for utilizada para executar outra operação, continuará a agregar as contagens para além dos resultados existentes.
> Se precisar de repor os cálculos entre as corridas, crie uma nova instância para cada execução.


## <a name="programmatically-retrieving-the-estimated-data"></a>Recuperação programática dos dados estimados

Além de uma tabela TSV, os recursos estimados podem ser recuperados programáticamente através `ResourcesEstimator` da `Data` propriedade. `Data`fornece uma `System.DataTable` instância com duas colunas: `Metric` `Sum` e, indexada pelos nomes das métricas.

O seguinte código mostra como recuperar e imprimir o número total de `QubitClifford` , `T` e `CNOT` portões utilizados por uma operação Q#:

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();

            var data = estimator.Data;
            Console.WriteLine($"QubitCliffords: {data.Rows.Find("QubitClifford")["Sum"]}");
            Console.WriteLine($"Ts: {data.Rows.Find("T")["Sum"]}");
            Console.WriteLine($"CNOTs: {data.Rows.Find("CNOT")["Sum"]}");
        }
    }
}
```

## <a name="metrics-reported"></a>Métricas Reportadas

Segue-se a lista de métricas estimadas pelo `ResourcesEstimator` seguinte:

* __CNOT__: A contagem de portões CNOT (também conhecido como portão Pauli X controlado) executada.
* __QubitClifford__: A contagem de qualquer portão qubit Clifford e Pauli executado.
* __Medida__: Contagem de quaisquer medições executadas.
* __R:__ Contagem de eventuais rotações qubit executadas, excluindo portões T, Clifford e Pauli.
* __T:__ A contagem dos portões T e dos seus conjugados, incluindo o portão T, T_x = H.T.H, e T_y = Hy.T.Hy, executado.
* __Profundidade__: Profundidade do circuito quântico executado pela operação Q#. Por defeito, apenas os portões T são contados na profundidade, consulte o contador de [profundidade](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) para obter detalhes.
* __Largura__: Número máximo de qubits atribuídos durante a execução da operação Q#
* __Largura emprestada__: Número máximo de qubits emprestados dentro da operação Q#


## <a name="providing-the-probability-of-measurement-outcomes"></a>Fornecer a Probabilidade de Resultados de Medição

<xref:microsoft.quantum.intrinsic.assertprob>a partir do <xref:microsoft.quantum.intrinsic> espaço de nome pode ser usado para fornecer informações sobre a probabilidade esperada de uma medição para ajudar a impulsionar a execução do programa Q#. O exemplo seguinte ilustra isso mesmo:

```qsharp
operation Teleport(source : Qubit, target : Qubit) : Unit {

    using (qubit = Qubit()) {

        H(q);
        CNOT(qubit, target);

        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [qubit], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(qubit) == One) { X(target); X(qubit); }
    }
}
```

Quando os `ResourcesEstimator` encontros `AssertProb` registarão que mede `PauliZ` e deve ser `source` `q` dado um resultado com probabilidade de `Zero` 0,5. Quando for executado `M` mais tarde, encontrará os valores registados das probabilidades de resultado e `M` regressará ou com probabilidade `Zero` `One` 0,5.


## <a name="see-also"></a>Ver também

O é construído em cima do simulador de rastreio de `ResourcesEstimator` computador quântico, que fornece um conjunto mais rico de métricas, a capacidade de reportar métricas no gráfico de chamada completo, e apresenta-se como verificador de [inputs distintos](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) para ajudar a encontrar bugs em programas Q#. [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Consulte a documentação do simulador de [vestígios](xref:microsoft.quantum.machines.qc-trace-simulator.intro) para obter mais informações.

