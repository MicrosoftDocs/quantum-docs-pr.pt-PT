---
title: Contador de largura
description: Conheça o Contador de Largura QDK da Microsoft, que conta o número de qubits atribuídos e emprestados por cada operação num programa quântico.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: a76292222950310acc90dded02980e4a5b792e76
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907091"
---
# <a name="width-counter"></a>Contador de largura

O `Width Counter` conta o número de qubits atribuídos e emprestados por cada operação.
Todas as operações do espaço de nome `Microsoft.Quantum.Intrinsic` são expressas em termos de rotações simples de qubit, portões T, portões simples de Qubit Clifford, portões CNOT e medições de observáveis multiqubit Pauli. Algumas das operações primitivas podem alocar qubits extras. Por exemplo, multiplique portões `X` controlados ou portões de `T` controlados. Calculemos o número de qubits extra atribuídos pela implementação de um portão de `X` controlado multiplicado:

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a>Utilização do C# Contador de Largura dentro de um Programa

Multiplicar `X` controlados num total de 5 qubits atribuirá 2 qubits auxiliares e a sua largura de entrada será de 5. Para verificar se este é o caso, podemos usar o seguinte C# programa:

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

A primeira parte do programa executa `ApplyMultiControlledX`. Na segunda parte utilizamos o método `QCTraceSimulator.GetMetric` para obter o número de qubits atribuídos, bem como o número de qubits que controlou `X` recebidos como entrada. 

Finalmente, para obter todas as estatísticas recolhidas por contador de largura em formato CSV podemos usar o seguinte:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Consulte também ##

- A visão geral do simulador de [rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro) do computador quântico.
