---
title: Estimativa de recursos do kit de desenvolvimento quântico  Microsoft Docs
description: Visão geral do estimador de recursos do kit de desenvolvimento quântico da Microsoft
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 960fda3dade7648f9cd24496c3a49fd11d6f807a
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820866"
---
# <a name="the-resourcesestimator-target-machine"></a>A Máquina-Alvo do Estimativa de Recursos

Como o nome indica, o `ResourcesEstimator` estima os recursos necessários para executar uma determinada instância de uma operação Q# num computador quântico.
Consegue-o executando a operação quântica sem simular o estado de um computador quântico; por esta razão, pode estimar recursos para operações Q# que usam milhares de qubits.

## <a name="usage"></a>Utilização

O `ResourcesEstimator` é apenas mais um tipo de máquina-alvo, pelo que pode ser usado para executar qualquer operação Q#. 

Como outras máquinas-alvo, C# usá-lo num programa de acolhimento criar uma instância e passá-la como o primeiro parâmetro do método `Run` da operação:

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

Como o exemplo mostra, o `ResourcesEstimator` fornece um método `ToTSV()` para gerar uma tabela com valores separados (TSV) que podem ser guardados num ficheiro ou escritos à consola para análise. A saída do programa acima deve ser algo assim:

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

Além de uma tabela TSV, os recursos estimados podem ser recuperados programáticamente através da propriedade `Data` do `ResourcesEstimator`. `Data` fornece um `System.DataTable` instância com duas colunas: `Metric` e `Sum`, indexadas pelos nomes das métricas.

O seguinte código mostra como recuperar e imprimir o número total de `QubitClifford`, `T` e `CNOT` portões utilizados por uma operação Q#:

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

Segue-se a lista de métricas estimada si a `ResourcesEstimator`:

* __CNOT__: A contagem de portões CNOT (também conhecido como portão Pauli X controlado) executada.
* __QubitClifford__: A contagem de qualquer portão qubit Clifford e Pauli executado.
* __Medida__: Contagem de quaisquer medições executadas.
* __R:__ Contagem de eventuais rotações qubit executadas, excluindo portões T, Clifford e Pauli.
* __T:__ A contagem dos portões T e dos seus conjugados, incluindo o portão T, T_x = H.T.H, e T_y = Hy.T.Hy, executado.
* __Profundidade__: Profundidade do circuito quântico executado pela operação Q#. Por defeito, apenas os portões T são contados na profundidade, consulte o contador de [profundidade](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) para obter detalhes.
* __Largura__: Número máximo de qubits atribuídos durante a execução da operação Q#
* __Largura emprestada__: Número máximo de qubits emprestados dentro da operação Q#


## <a name="providing-the-probability-of-measurement-outcomes"></a>Fornecer a Probabilidade de Resultados de Medição

<xref:microsoft.quantum.intrinsic.assertprob> do espaço de nome <xref:microsoft.quantum.intrinsic> pode ser usado para fornecer informações sobre a probabilidade esperada de uma medição para ajudar a impulsionar a execução do programa Q#. O exemplo seguinte ilustra isso mesmo:

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

Quando o `ResourcesEstimator` se encontrar `AssertProb` registará que a medição `PauliZ` em `source` e `q` deve ser dado um resultado de `Zero` com probabilidade de 0,5. Quando executar `M` mais tarde, encontrará os valores registados das probabilidades de resultados e `M` devolverá `Zero` ou `One` com probabilidade 0,5.


## <a name="see-also"></a>Ver também

O `ResourcesEstimator` é construído em cima do simulador de [rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de computador quântico, que fornece um conjunto mais rico de métricas, a capacidade de reportar métricas no gráfico de chamadas completo, e características como verificador de [inputs distintos](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) para ajudar a encontrar bugs em programas Q#. Consulte a documentação do simulador de [vestígios](xref:microsoft.quantum.machines.qc-trace-simulator.intro) para obter mais informações.

