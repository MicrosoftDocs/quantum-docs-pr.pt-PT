---
title: Verificador de entradas distintos - Kit de Desenvolvimento Quântico
description: Saiba mais sobre o verificador de entradas distintos microsoft QDK, que utiliza o simulador de traços Quânticos para verificar o seu Q# código para potenciais conflitos com qubits partilhados.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 750c94e7f861678d37f051619ff5b29bf4fd3d3e
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868275"
---
# <a name="quantum-trace-simulator-distinct-inputs-checker"></a>Simulador de vestígios quânticos: verificador de entradas distintos

O verificador de entradas distintos faz parte do simulador de [traços quânticos](xref:microsoft.quantum.machines.qc-trace-simulator.intro)do Kit de Desenvolvimento Quântico. Pode usá-lo para detetar potenciais bugs no código causados por conflitos com qubits partilhados. 

## <a name="conflicts-with-shared-qubits"></a>Conflitos com qubits partilhados

Considere o seguinte pedaço de Q# código para ilustrar as questões detetadas pelo verificador de entradas distintos:

```qsharp
operation ApplyBoth(
    q1 : Qubit,
    q2 : Qubit,
    op1 : (Qubit => Unit),
    op2 : (Qubit => Unit))
: Unit {
    op1(q1);
    op2(q2);
}
```

Quando olhamos para este programa, podemos assumir que a ordem pela qual chama `op1` e `op2` não importa, porque são `q1` `q2` diferentes qubits e operações agindo em diferentes qubits. 

Agora, considere este exemplo:

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

Note que `op1` e `op2` ambos são obtidos usando aplicação parcial e compartilham um qubit. Quando se chama `ApplyBoth` este exemplo, o resultado da operação depende da ordem de `op1` e para dentro - não do que se esperaria que `op2` `ApplyBoth` acontecesse. Quando ativa o verificador de entradas distintos, deteta tais situações e atira um `DistinctInputsCheckerException` . Para mais informações, consulte <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> na biblioteca da Q# API.

## <a name="invoking-the-distinct-inputs-checker"></a>Invocando o verificador de entradas distintos

Para executar o simulador de traços quânticos com o verificador de entradas distintos deve criar um <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> exemplo, definir a `UseDistinctInputsChecker` propriedade como **verdadeiro**, e, em seguida, criar um novo exemplo com como <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> o `QCTraceSimulatorConfiguration` parâmetro. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDistinctInputsChecker = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-distinct-inputs-checker-in-a-c-host-program"></a>Usando o verificador de entradas distinto num programa de anfitrião C#

Segue-se um exemplo do programa de anfitrião C# que utiliza o simulador de traços quânticos com o verificador de entradas distinto ativado:

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            var traceSimCfg = new QCTraceSimulatorConfiguration();
            traceSimCfg.UseDistinctInputsChecker = true; //enables distinct inputs checker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="see-also"></a>Ver também

- A visão geral do [simulador de traços quânticos](xref:microsoft.quantum.machines.qc-trace-simulator.intro) do Kit de Desenvolvimento Quântico.
- A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> referência da API.
- A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> referência da API.
- A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> referência da API.
