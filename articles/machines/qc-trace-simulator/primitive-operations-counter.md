---
title: Contador de operações primitivas | Simulador de rastreamento de computador Quantum | Microsoft Docs
description: Visão geral do simulador de rastreamento de computador Quantum
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: b7ec8b0d7a713051e36cb778c087050f0257710f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184887"
---
# <a name="primitive-operations-counter"></a>Contador de operações primitivas  

O `Primitive Operations Counter` é uma parte do [simulador de rastreamento](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de computador Quantum. Ele conta o número de execuções primitivas usadas por cada operação invocada em um programa Quantum. Todas as operações de `Microsoft.Quantum.Primitive` são expressas em termos de rotações qubit únicas, T Gates, Single qubit Clifford Gates, CNOT Gates e medidas de qubit de vários Pauli observáveis. As estatísticas coletadas são agregadas nas bordas do grafo de chamada de operações. Agora, vamos contar quantas `T` Gates são necessárias para implementar a operação `CCNOT`. 

```qsharp
open Microsoft.Quantum.Primitive;
operation CCNOTDriver() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a>Usando o contador de operações primitivas C# dentro de um programa

Para verificar se `CCNOT` realmente requer 7 `T` Gates e que `CCNOTDriver` executa 8 `T` Gates, podemos usar o seguinte C# código:

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = CCNOTDriver.Run(sim).Result;

double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

A primeira parte do programa executa `CCNOTDriver`. Na segunda parte, usamos o método `QCTraceSimulator.GetMetric` para obter o número de T Gates executadas por `CCNOTDriver`: 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

Quando `GetMetric` é chamado com dois parâmetros de tipo, ele retorna o valor da métrica associada a uma determinada borda de gráfico de chamada. Em nosso `Primitive.CCNOT` de operação de exemplo é chamado dentro de `CCNOTDriver` e, portanto, o grafo de chamadas contém o `<Primitive.CCNOT,CCNOTDriver>`de borda. 

Para obter o número de `CNOT` Gates usado, podemos adicionar a seguinte linha:
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.CX);
```

Por fim, para gerar todas as estatísticas coletadas pelo contador portão no formato CSV, podemos usar o seguinte:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Ver também ##

- A visão geral do [simulador de rastreamento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) do computador Quantum.
