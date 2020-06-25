---
title: Verificador de entradas distintos
description: Saiba mais sobre o Verificador de Entradas Distintas Microsoft QDK, que verifica o seu código Q# para potenciais conflitos com qubits partilhados.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 11a0573242c8afb12f242aa3be5f9cff18290452
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275620"
---
# <a name="distinct-inputs-checker"></a>Verificador de entradas distintos

Faz `Distinct Inputs Checker` parte do [simulador](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de rastreio de computador quântico. Foi concebido para detetar potenciais bugs no código. Considere o seguinte pedaço de código Q# para ilustrar as questões detetadas por este pacote:

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

Quando o utilizador olha para este programa, assume que a ordem em que `op1` e `op2` são chamados não importa porque e são `q1` `q2` diferentes qubits e operações agindo em diferentes qubits comuta. Consideremos agora um exemplo, onde esta operação é utilizada:

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

Agora `op1` e ambos são `op2` obtidos usando aplicação parcial e compartilham um qubit. Quando o utilizador ligar `ApplyBoth` no exemplo acima, o resultado da operação dependerá da ordem de `op1` e para dentro `op2` `ApplyBoth` . Isto definitivamente não é o que o utilizador esperaria que acontecesse. A `Distinct Inputs Checker` vontade detetará tais situações quando ativada e lançará `DistinctInputsCheckerException` . Consulte a documentação da API sobre [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) para obter mais detalhes.

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a>Utilizando o verificador de entradas distintos no seu programa C#

Segue-se um exemplo do código do controlador C# para a utilização do simulador de traços de computador quântico com o `Distinct Inputs Checker` ativado:

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
            traceSimCfg.useDistinctInputsChecker = true; //enables distinct inputs checker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

A classe `QCTraceSimulatorConfiguration` armazena a configuração do simulador de traços de computador quântico e pode ser fornecida como um argumento para o `QCTraceSimulator` construtor. Quando `useDistinctInputsChecker` é definido para verdadeiro o está `Distinct Inputs Checker` ativado. Consulte a documentação da API sobre [o QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) e [a QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) para mais detalhes.

## <a name="see-also"></a>Ver também

- A visão geral [do Trace Simulator do](xref:microsoft.quantum.machines.qc-trace-simulator.intro) computador quântico.
