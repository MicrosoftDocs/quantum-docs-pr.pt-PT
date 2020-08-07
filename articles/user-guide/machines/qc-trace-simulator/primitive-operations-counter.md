---
title: Contador de operação primitiva - Kit de Desenvolvimento Quântico
description: Saiba mais sobre o contador de operações primitivos microsoft QDK, que usa o simulador de traços quânticos para rastrear execuções primitivas usadas por operações num Q# programa.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: ceb70cef6dc0a4530b992b5a529248a8b283c17f
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868241"
---
# <a name="quantum-trace-simulator-primitive-operations-counter"></a>Simulador de vestígios quânticos: contador de operações primitivas

O contador de operações primitiva faz parte do simulador de [traços quânticos](xref:microsoft.quantum.machines.qc-trace-simulator.intro)do Kit de Desenvolvimento Quântico. Conta o número de execuções primitivas usadas por todas as operações invocadas num programa quântico. 

Todas as <xref:microsoft.quantum.intrinsic> operações são expressas em termos de rotações de um único qubit, operações T, operações de Clifford de um único qubit, operações CNOT e medições de observáveis Pauli multi-qubit. O Contador de Operações Primitiva agrega e recolhe estatísticas sobre todas as bordas do gráfico de chamada da [operação](https://en.wikipedia.org/wiki/Call_graph).

## <a name="invoking-the-primitive-operation-counter"></a>Invocando o contador de operações primitiva

Para executar o simulador de traços quânticos com o contador de operação primitivo, você deve criar um <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> exemplo, definir a `UsePrimitiveOperationsCounter` propriedade para **verdade**, e, em seguida, criar um novo caso com o como <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> o `QCTraceSimulatorConfiguration` parâmetro.

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-primitive-operation-counter-in-a-c-host-program"></a>Usando o contador de operações primitiva num programa de anfitrião C#

O exemplo C# que se segue nesta secção conta quantas <xref:microsoft.quantum.intrinsic.t> operações são necessárias para implementar a <xref:microsoft.quantum.intrinsic.ccnot> operação, com base no seguinte Q# código de amostra:

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

Para verificar se `CCNOT` são necessárias sete `T` operações e que `ApplySampleWithCCNOT` executa oito `T` operações, utilize o seguinte código C# :

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

A primeira parte do programa `ApplySampleWithCCNOT` é. A segunda parte utiliza o [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) método para recuperar o número de `T` operações executadas `ApplySampleWithCCNOT` por: 

Quando se liga `GetMetric` com dois parâmetros do tipo, devolve o valor da métrica associada a uma determinada borda do gráfico de chamada. No exemplo anterior, o programa chama a `Primitive.CCNOT` operação interior `ApplySampleWithCCNOT` e, portanto, o gráfico de chamada contém a borda `<Primitive.CCNOT, ApplySampleWithCCNOT>` . 

Para recuperar o número de `CNOT` operações utilizadas, adicione a seguinte linha:
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

Finalmente, pode descodutar todas as estatísticas recolhidas pelo Contador de Operações Primitivas em formato CSV utilizando o seguinte:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Ver também

- A visão geral do [simulador de traços quânticos](xref:microsoft.quantum.machines.qc-trace-simulator.intro) do Kit de Desenvolvimento Quântico.
- A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> referência da API.
- A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> referência da API.
- A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames> referência da API.