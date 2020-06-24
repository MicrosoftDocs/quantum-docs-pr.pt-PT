---
title: Contador de profundidade
description: Conheça o Contador de Profundidade QDK da Microsoft, que reúne contagens da profundidade de cada operação invocada num programa quântico.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: d532a9f512b8c87d83d62ed26e3bb67e1b6f668b
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275627"
---
# <a name="depth-counter"></a>Contador de profundidade

Faz `Depth Counter` parte do [simulador](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de rastreio de computador quântico.
É usado para recolher contagens da profundidade de cada operação invocada num programa quântico. Todas as operações <xref:microsoft.quantum.intrinsic> são expressas em termos de rotações de qubit único, portões T, portões de Clifford de qubit único, portões CNOT e medições de observáveis Pauli multi-qubit. Os utilizadores podem definir a profundidade para cada uma das operações primitivas através do `gateTimes` campo de <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .

Por predefinição, todas as operações têm profundidade 0, exceto o portão T que tem profundidade 1. Isto significa que, por defeito, apenas a profundidade T das operações é calculada (o que é muitas vezes desejável). As estatísticas recolhidas são agregadas em todas as bordas do gráfico de chamadas de operações. 

Vamos agora calcular a <xref:microsoft.quantum.intrinsic.t> profundidade da <xref:microsoft.quantum.intrinsic.ccnot> operação. Utilizaremos o seguinte código de amostra Q#:

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a>Utilização do Contador de Profundidade dentro de um programa C#

Para verificar se `CCNOT` tem `T` profundidade 5 e tem profundidade `ApplySampleWithCCNOT` `T` 6, podemos usar o seguinte código C#:

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

A primeira parte do programa `ApplySampleWithCCNOT` executa. Na segunda parte, usamos o método `QCTraceSimulator.GetMetric` para obter a profundidade de `T` `CCNOT` `ApplySampleWithCCNOT` e: 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

Finalmente, para obter todas as estatísticas `Depth Counter` recolhidas em formato CSV podemos utilizar o seguinte:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>Ver também ##

- A visão geral [do Trace Simulator do](xref:microsoft.quantum.machines.qc-trace-simulator.intro) computador quântico.
