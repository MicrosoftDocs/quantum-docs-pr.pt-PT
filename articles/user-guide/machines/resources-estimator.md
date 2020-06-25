---
title: Estimativa de recursos do kit de desenvolvimento quântico
description: Conheça o Estimativa de Recursos, que estima os recursos necessários para executar uma determinada instância de uma operação Q# num computador quântico.
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: b0c800c3946d2e4ba4457127fb9495dc9dcf2934
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275547"
---
# <a name="the-resources-estimator-target-machine"></a>A Máquina-Alvo do Estimador de Recursos

Como o nome indica, `ResourcesEstimator` estima os recursos necessários para executar uma determinada instância de uma operação Q# num computador quântico.
Consegue-o executando a operação quântica sem simular o estado de um computador quântico; por esta razão, pode estimar recursos para operações Q# que usam milhares de qubits, se a parte clássica do código pode ser executada em um tempo razoável.

## <a name="usage"></a>Utilização

Este `ResourcesEstimator` é apenas mais um tipo de máquina alvo, portanto pode ser usado para executar qualquer operação Q#. 

Como outras máquinas-alvo, usá-lo num programa de anfitrião C# criar uma instância e passá-la como o primeiro parâmetro do método da `Run` operação:

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

Como mostra o exemplo, `ResourcesEstimator` o método fornece um método para gerar uma tabela com `ToTSV()` valores separados por separados (TSV) que pode ser guardado num ficheiro ou escrito na consola para análise. A saída do programa acima deve ser algo assim:

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
> O `ResourcesEstimator` não reinicia os seus cálculos em cada execução, se for utilizado o mesmo caso para executar outra operação, manterá as contagens agregadas para além dos resultados existentes.
> Se precisar de redefinir os cálculos entre as execuções, crie uma nova instância para cada execução.


## <a name="programmatically-retrieving-the-estimated-data"></a>Recuperação programática dos dados estimados

Além de uma tabela de TSV, os recursos estimados podem ser recuperados programáticamente através `ResourcesEstimator` da `Data` propriedade. `Data`fornece um `System.DataTable` caso com duas colunas: `Metric` `Sum` e, indexado pelos nomes das métricas.

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

* __CNOT__: A contagem dos portões CNOT (também conhecido como portão Controlado Pauli X) executada.
* __QubitClifford:__ A contagem de qualquer qubit Clifford e pauli portões executados.
* __Medida__: A contagem de quaisquer medições executadas.
* __R__: A contagem de quaisquer rotações de qubit executadas, excluindo os portões T, Clifford e Pauli.
* __T__: A contagem de portões T e seus conjugados, incluindo o portão T, T_x = H.T.H, e T_y = Hy.T.Hy, executado.
* __Profundidade__: Profundidade do circuito quântico executada pela operação Q#. Por predefinição, apenas os portões T são contados na profundidade, consulte o [contador de profundidade](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) para obter detalhes.
* __Largura__: Número máximo de qubits atribuídos durante a execução da operação Q#.
* __BorrowedWidth__: Número máximo de qubits emprestados dentro da operação Q#.


## <a name="providing-the-probability-of-measurement-outcomes"></a>Fornecer a Probabilidade de Resultados de Medição

<xref:microsoft.quantum.intrinsic.assertprob>a partir do <xref:microsoft.quantum.intrinsic> espaço de nomes pode ser usado para fornecer informações sobre a probabilidade esperada de uma medição para ajudar a impulsionar a execução do programa Q#. O exemplo seguinte ilustra isso mesmo:

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

Quando os `ResourcesEstimator` encontros `AssertProb` registarem essa medição `PauliZ` e deve ser dado um resultado com probabilidade de `source` `q` `Zero` 0,5. Quando executar `M` mais tarde, encontrará os valores registados das probabilidades de resultado e `M` regressará `Zero` ou com probabilidade `One` 0.5.


## <a name="see-also"></a>Ver também

O `ResourcesEstimator` é construído em cima do simulador de [traços](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de computador quântico, que fornece um conjunto mais rico de métricas, a capacidade de reportar métricas no gráfico de chamada completo, e apresenta características como [verificador de entradas distintas](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) para ajudar a encontrar bugs em programas Q#. Consulte a documentação do [simulador de rastreios](xref:microsoft.quantum.machines.qc-trace-simulator.intro) para obter mais informações.

