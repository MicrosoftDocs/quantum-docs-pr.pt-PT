---
title: Contador de largura
description: Saiba mais sobre o Contador de Largura QDK do Microsoft, que conta o número de qubits atribuídos e emprestados por cada operação num programa quântico.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: a76292222950310acc90dded02980e4a5b792e76
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275563"
---
# <a name="width-counter"></a>Contador de largura

O `Width Counter` número de qubits atribuídos e emprestados por cada operação.
Todas as operações do `Microsoft.Quantum.Intrinsic` espaço de nome são expressas em termos de rotações de qubit único, portões T, portões de Clifford de qubit único, portões CNOT e medições de observáveis Pauli multi-qubit. Algumas das operações primitivas podem alocar qubits extra. Por exemplo, multiplique `X` portões controlados ou `T` portões controlados. Vamos calcular o número de qubits extra atribuídos pela implementação de um portão controlado por `X` multiplicação:

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a>Utilização do Contador de Largura dentro de um programa C#

A atuação controlada por `X` multiplicação num total de 5 qubits irá afetar 2 qubits auxiliares e a sua largura de entrada será de 5. Para verificar se este é o caso, podemos usar o seguinte programa C#:

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = ApplyMultiControlledX.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

A primeira parte do programa `ApplyMultiControlledX` executa. Na segunda parte utilizamos o método `QCTraceSimulator.GetMetric` para obter o número de qubits atribuídos, bem como o número de qubits que o Controlled recebeu como `X` entrada. 

Finalmente, para obter todas as estatísticas recolhidas por contador de largura no formato CSV podemos utilizar o seguinte:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Ver também ##

- A visão geral [do Trace Simulator do](xref:microsoft.quantum.machines.qc-trace-simulator.intro) computador quântico.
