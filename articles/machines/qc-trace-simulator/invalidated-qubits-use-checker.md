---
title: Qubits invalidados usam verificador / Simulador de vestígios de computador quântico  Microsoft Docs
description: Descrição geral do simulador de rastreio do computador quântico
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: 093937346488725eacb69ef7da6affde764ec5c1
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820883"
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

## <a name="see-also"></a>Ver também ##

- A visão geral do simulador de [rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro) do computador quântico.
