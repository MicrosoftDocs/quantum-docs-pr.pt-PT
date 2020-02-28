---
title: Contador de Operações Primitivas
description: Conheça o Contador de Operações Primitivas Microsoft QDK, que rastreia o número de execuções primitivas usadas por operações num programa quântico.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 8bdb0aed370e72b58b23025f1685ad7ce1a77a43
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77905952"
---
# <a name="primitive-operations-counter"></a>Contador de Operações Primitivas  

O `Primitive Operations Counter` faz parte do simulador de [rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro)do computador quântico. Conta o número de execuções primitivas usadas por cada operação invocada num programa quântico. Todas as operações de `Microsoft.Quantum.Intrinsic` são expressas em termos de rotações de qubit simples, portões T, portões simples de Qubit Clifford, portões CNOT e medições de observáveis multiqubit Pauli. As estatísticas recolhidas são agregadas sobre as bordas do gráfico de chamadas de operações. Contemos agora quantas portas `T` são necessárias para implementar a operação `CCNOT`. 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a>Utilização do Contador C# de Operações Primitivas dentro de um Programa

Para verificar se `CCNOT` requer 7 portões `T` e que `ApplySampleWithCCNOT` executa C# 8 portas `T` podemos usar o seguinte código:

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

A primeira parte do programa executa `ApplySampleWithCCNOT`. Na segunda parte, utilizamos o método `QCTraceSimulator.GetMetric` para executar o número de portões T por `ApplySampleWithCCNOT`: 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

Quando `GetMetric` é chamado com dois parâmetros de tipo, devolve o valor da métrica associada a uma determinada borda do gráfico de chamada. No nosso exemplo, a operação `Primitive.CCNOT` é chamada dentro `ApplySampleWithCCNOT` e, portanto, o gráfico de chamada contém a borda `<Primitive.CCNOT, ApplySampleWithCCNOT>`. 

Para obter o número de portões `CNOT` usados, podemos adicionar a seguinte linha:
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

Finalmente, para obter todas as estatísticas recolhidas pelo balcão do portal em formato CSV podemos usar o seguinte:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Consulte também ##

- A visão geral do simulador de [rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro) do computador quântico.
