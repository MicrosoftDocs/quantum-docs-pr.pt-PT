---
title: Contador de Operações Primitivas
description: Conheça o Contador de Operações Primitivas da Microsoft QDK, que acompanha o número de execuções primitivas usadas por operações num programa quântico.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 8bdb0aed370e72b58b23025f1685ad7ce1a77a43
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275556"
---
# <a name="primitive-operations-counter"></a>Contador de Operações Primitivas  

Faz `Primitive Operations Counter` parte do [simulador](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de rastreio de computador quântico. Conta o número de execuções primitivas usadas por todas as operações invocadas num programa quântico. Todas as operações `Microsoft.Quantum.Intrinsic` são expressas em termos de rotações de qubit único, portões T, portões de Clifford de qubit único, portões CNOT e medições de observáveis Pauli multi-qubit. As estatísticas recolhidas são agregadas sobre as bordas do gráfico de chamadas de operações. Contemos agora quantos `T` portões são necessários para implementar a `CCNOT` operação. 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a>Utilização do Contador de Operações Primitivas dentro de um Programa C#

Para verificar `CCNOT` se, de facto, requer 7 `T` portões e que `ApplySampleWithCCNOT` executa 8 `T` portões podemos usar o seguinte código C#:

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

A primeira parte do programa `ApplySampleWithCCNOT` executa. Na segunda parte, usamos o método `QCTraceSimulator.GetMetric` para executar o número de portões T `ApplySampleWithCCNOT` por: 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

Quando `GetMetric` é chamado com dois parâmetros de tipo, devolve o valor da métrica associada a uma determinada borda do gráfico de chamada. No nosso exemplo, a `Primitive.CCNOT` operação é chamada dentro `ApplySampleWithCCNOT` e, portanto, o gráfico de chamada contém a borda `<Primitive.CCNOT, ApplySampleWithCCNOT>` . 

Para obter o número de `CNOT` portões usados, podemos adicionar a seguinte linha:
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

Finalmente, para obter todas as estatísticas recolhidas pelo contador de portais em formato CSV podemos utilizar o seguinte:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Ver também ##

- A visão geral [do Trace Simulator do](xref:microsoft.quantum.machines.qc-trace-simulator.intro) computador quântico.
