---
title: Contador de largura - Kit de Desenvolvimento Quântico
description: Saiba mais sobre o contador de largura do Microsoft QDK, que utiliza o simulador de traços Quânticos para contar o número de qubits atribuídos e emprestados por operações num programa Q#.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: af8609dc5c05f7a19b8d21755281427feb29b84c
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871525"
---
# <a name="quantum-trace-simulator-width-counter"></a>Simulador de vestígios quânticos: contador de largura

O contador de largura faz parte do simulador de [traços quânticos](xref:microsoft.quantum.machines.qc-trace-simulator.intro)do Kit de Desenvolvimento Quântico. Pode usá-lo para contar o número de qubits atribuídos e emprestados por cada operação num programa Q#. Algumas operações primitivas podem alocar qubits extra, por exemplo, multiplicar operações controladas `X` ou `T` operações controladas.

## <a name="invoking-the-width-counter"></a>Invocando o contador de largura

Para executar o simulador de traços quânticos com o contador de largura, você deve criar um <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> exemplo, definir a `UseWidthCounter` propriedade para **verdade**, e, em seguida, criar um novo caso com o como <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> o `QCTraceSimulatorConfiguration` parâmetro. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a>Usando o contador de largura num programa de anfitrião C#

O exemplo C# que segue nesta secção calcula o número de qubits extra atribuídos pela implementação de uma operação controlada por <xref:microsoft.quantum.intrinsic.x> multiplicação, com base no seguinte código de amostra Q#:

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

A operação controlada por multiplicação <xref:microsoft.quantum.intrinsic.x> atua num total de cinco qubits, atribui dois [qubits auxiliares,](xref:microsoft.quantum.glossary#ancilla)e tem uma largura de entrada de **5**. Utilize o seguinte programa C# para verificar as contagens:

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
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

A primeira parte do programa executa a `ApplyMultiControlledX` operação. A segunda parte utiliza o [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) método para recuperar o número de qubits atribuídos, bem como o número de qubits que a `Controlled X` operação recebeu como entrada. 

Finalmente, pode descodutar todas as estatísticas recolhidas pelo contador de largura em formato CSV utilizando o seguinte:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Ver também

- A visão geral do [simulador de traços quânticos](xref:microsoft.quantum.machines.qc-trace-simulator.intro) do Kit de Desenvolvimento Quântico.
- A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> referência da API.
- A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> referência da API.
- A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter> referência da API.
