---
title: Verificador de inputs distintos
description: Saiba mais sobre o Microsoft QDK Distinct Inputs Checker, que verifica o seu código Q# para potenciais conflitos com qubits partilhados.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 11a0573242c8afb12f242aa3be5f9cff18290452
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907108"
---
# <a name="distinct-inputs-checker"></a>Verificador de inputs distintos

O `Distinct Inputs Checker` faz parte do simulador de [rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro)do computador quântico. Foi concebido para detetar potenciais bugs no código. Considere a seguinte peça do código Q# para ilustrar as questões detetadas por este pacote:

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

Quando o utilizador olha para este programa, assume que a ordem em que `op1` e `op2` são chamados não importa porque `q1` e `q2` são diferentes qubits e operações agindo em diferentes qubits comutados. Consideremos agora um exemplo, em que esta operação é utilizada:

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

Agora `op1` e `op2` são ambos obtidos usando aplicação parcial e partilham um qubit. Quando o utilizador ligar `ApplyBoth` no exemplo acima do resultado da operação dependerá da ordem de `op1` e `op2` no interior `ApplyBoth`. Isto definitivamente não é o que o utilizador esperaria que acontecesse. O `Distinct Inputs Checker` detetará tais situações quando ativado e lançará `DistinctInputsCheckerException`. Consulte a documentação da API sobre [a DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) para obter mais detalhes.

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a>Utilização do Verificador de C# Inputs Distintos no seu Programa

Segue-se um C# exemplo de código do condutor para a utilização do simulador de vestígios de computador quântico com o `Distinct Inputs Checker` habilitado:

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

A classe `QCTraceSimulatorConfiguration` armazena a configuração do simulador de vestígios de computador quântico e pode ser fornecida como um argumento para o construtor `QCTraceSimulator`. Quando `useDistinctInputsChecker` for verdadeira, o `Distinct Inputs Checker` está ativado. Consulte a documentação da API no [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) e na [QCTraceSimulatorConfigura](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) para obter mais detalhes.

## <a name="see-also"></a>Consulte também

- A visão geral do simulador de [rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro) do computador quântico.
