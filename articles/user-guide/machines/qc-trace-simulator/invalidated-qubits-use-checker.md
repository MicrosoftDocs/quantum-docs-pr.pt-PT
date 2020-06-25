---
title: Verificador de utilização de qubits invalidados
description: Saiba mais sobre o Verificador de Utilização de Qubits invalidados do Microsoft QDK, que verifica o seu código Q# para qubits potencialmente inválidos.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: e2bbb12448e27f28db030a0084302fb24f46f26b
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275572"
---
# <a name="invalidated-qubits-use-checker"></a>Qubits invalidados usam verificador

É `Invalidated Qubits Use Checker` uma parte do computador quântico [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) projetado para detetar potenciais bugs no código. Considere o seguinte pedaço de código Q# para ilustrar as questões detetadas pelo `Invalidated Qubits Use Checker` .

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

Quando `H` é aplicado a ele aponta para um `q[0]` qubit já lançado. Isto pode causar um comportamento indefinido. Quando a `Invalidated Qubits Use Checker` ativação estiver ativada, a exceção `InvalidatedQubitsUseCheckerException` será lançada se uma operação for aplicada a um qubit já libertado. Consulte a documentação da API sobre [invalidadoQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) para obter mais detalhes.

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a>Utilizando o verificador de utilização de qubits invalidados no seu programa C#

Segue-se um exemplo do código do controlador C# para a utilização do computador quântico `Trace
Simulator` com o `Invalidated Qubits Use Checker` ativado: 

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
            traceSimCfg.useInvalidatedQubitsUseChecker = true; // enables useInvalidatedQubitsUseChecker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

A classe `QCTraceSimulatorConfiguration` armazena a configuração do simulador de traços de computador quântico e pode ser fornecida como um argumento para o `QCTraceSimulator` construtor. Quando `useInvalidatedQubitsUseChecker` é definido para verdadeiro o está `Invalidated Qubits Use Checker` ativado. Consulte a documentação da API sobre [o QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) e [a QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) para mais detalhes.

## <a name="see-also"></a>Ver também ##

- A visão geral [do Trace Simulator do](xref:microsoft.quantum.machines.qc-trace-simulator.intro) computador quântico.
