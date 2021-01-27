---
title: Contador de profundidade - Kit de Desenvolvimento Quântico
description: Conheça o contador de profundidade microsoft QDK, que utiliza o simulador de traços Quânticos para recolher contagens da profundidade de cada operação invocada num Q# programa.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9c3a772861582e5c49fe5ad27519c25a59d617b1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859035"
---
# <a name="quantum-trace-simulator-depth-counter"></a>Simulador de vestígios quânticos: contador de profundidade

O contador de profundidade faz parte do simulador de [traços quânticos](xref:microsoft.quantum.machines.qc-trace-simulator.intro)do Kit de Desenvolvimento Quântico.
Pode usá-lo para recolher contagens que representam o limite inferior da profundidade de cada operação invocada num programa quântico. 

## <a name="depth-values"></a>Valores de profundidade

Por predefinição, todas as operações têm uma profundidade de **0,** exceto a `T` operação, que tem uma profundidade de **1**. Isto significa que, por defeito, apenas a `T` profundidade das operações é calculada (o que é muitas vezes desejável). O contador de profundidade agrega e recolhe estatísticas sobre todas as bordas do gráfico de chamada da [operação](https://en.wikipedia.org/wiki/Call_graph).

Todas as <xref:Microsoft.Quantum.Intrinsic> operações são expressas em termos de rotações de um único qubit, <xref:Microsoft.Quantum.Intrinsic.T> operações, operações <xref:Microsoft.Quantum.Intrinsic.CNOT> e medições de observações pauli multi-qubit. Os utilizadores podem definir a profundidade para cada uma das operações primitivas através do `gateTimes` campo de <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .

## <a name="invoking-the-depth-counter"></a>Invocando o contador de profundidade

Para executar o simulador de traços quânticos com o contador de profundidade, você deve criar um <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> exemplo, definir a sua `UseDepthCounter` propriedade para **verdade**, e, em seguida, criar um novo exemplo com como <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> o `QCTraceSimulatorConfiguration` parâmetro. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-depth-counter-in-a-c-host-program"></a>Usando o contador de profundidade num programa de anfitrião C#

O exemplo C# que segue nesta secção calcula a `T` profundidade da `CCNOT` operação, com base no seguinte Q# código de amostra:

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

Para verificar se `CCNOT` tem `T` profundidade **5** e `ApplySampleWithCCNOT` tem profundidade `T` **6,** utilize o seguinte código C#:

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

A primeira parte do programa `ApplySampleWithCCNOT` é. A segunda parte utiliza o [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) método para recuperar a profundidade de e `T` `CCNOT` `ApplySampleWithCCNOT` . 

Finalmente, pode descodutar todas as estatísticas recolhidas pelo contador de profundidade no formato CSV utilizando o seguinte:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>Veja também

- A visão geral do [simulador de traços quânticos](xref:microsoft.quantum.machines.qc-trace-simulator.intro) do Kit de Desenvolvimento Quântico.
- A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> referência da API.
- A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> referência da API.
- A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter> referência da API.
