---
title: Verificador de utilização de qubits invalidados
description: Saiba mais sobre o Microsoft QDK Invalidado Qubits Use Checker, que verifica o seu código Q# para qubits potencialmente inválidos.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: e2bbb12448e27f28db030a0084302fb24f46f26b
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907074"
---
# <a name="invalidated-qubits-use-checker"></a>Verificador de utilização de Qubits invalidados

O `Invalidated Qubits Use Checker` é uma parte do computador quântico [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) projetado para detetar potenciais bugs no código. Considere a seguinte peça do código Q# para ilustrar as questões detetadas pelo `Invalidated Qubits Use Checker`.

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

Quando `H` é aplicada à `q[0]` aponta para um qubit já lançado. Isto pode causar um comportamento indefinido. Quando o `Invalidated Qubits Use Checker` estiver ativado, a exceção `InvalidatedQubitsUseCheckerException` será lançada se uma operação for aplicada a um qubit já lançado. Consulte a documentação da API sobre [invalidadoQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) para mais detalhes.

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a>Utilização do Verificador de Utilização C# de Qubits Invalidados no seu Programa

Segue-se um C# exemplo de código do condutor para a utilização do `Trace
Simulator` informático quântico com o `Invalidated Qubits Use Checker` habilitado: 

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

A classe `QCTraceSimulatorConfiguration` armazena a configuração do simulador de vestígios de computador quântico e pode ser fornecida como um argumento para o construtor `QCTraceSimulator`. Quando `useInvalidatedQubitsUseChecker` for verdadeira, o `Invalidated Qubits Use Checker` está ativado. Consulte a documentação da API no [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) e na [QCTraceSimulatorConfigura](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) para obter mais detalhes.

## <a name="see-also"></a>Consulte também ##

- A visão geral do simulador de [rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro) do computador quântico.
