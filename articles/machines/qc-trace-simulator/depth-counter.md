---
title: Contador de profundidade
description: Conheça o Contador de Profundidade QDK da Microsoft, que reúne contagens da profundidade de cada operação invocada num programa quântico.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: d532a9f512b8c87d83d62ed26e3bb67e1b6f668b
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906105"
---
# <a name="depth-counter"></a>Contador de profundidade

O `Depth Counter` faz parte do simulador de [rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro)do computador quântico.
É usado para recolher contagens da profundidade de cada operação invocada num programa quântico. Todas as operações de <xref:microsoft.quantum.intrinsic> são expressas em termos de rotações de qubit simples, portões T, portões simples de Qubit Clifford, portões CNOT e medições de observáveis multiqubit Pauli. Os utilizadores podem definir a profundidade para cada uma das operações primitivas através do campo `gateTimes` de <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.

Por defeito, todas as operações têm profundidade 0 exceto o portão T que tem profundidade 1. Isto significa que, por padrão, apenas a profundidade T das operações é calculada (o que é muitas vezes desejável). As estatísticas recolhidas são agregadas sobre todas as bordas do gráfico de chamadas de operações. 

Vamos agora calcular a profundidade <xref:microsoft.quantum.intrinsic.t> da operação <xref:microsoft.quantum.intrinsic.ccnot>. Usaremos o seguinte código de amostra Q#:

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a>Usando o Contador C# de Profundidade dentro de um programa

Para verificar se `CCNOT` tem `T` profundidade 5 e `ApplySampleWithCCNOT` C# tem `T` profundidade 6 podemos usar o seguinte código:

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

A primeira parte do programa executa `ApplySampleWithCCNOT`. Na segunda parte, utilizamos o método `QCTraceSimulator.GetMetric` para obter a profundidade `T` de `CCNOT` e `ApplySampleWithCCNOT`: 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

Finalmente, para obter todas as estatísticas recolhidas por `Depth Counter` em formato CSV podemos usar o seguinte:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>Consulte também ##

- A visão geral do simulador de [rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro) do computador quântico.
