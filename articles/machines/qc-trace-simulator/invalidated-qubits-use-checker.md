---
title: Verificador de uso qubits invalidado | Simulador de rastreamento de computador Quantum | Microsoft Docs
description: Visão geral do simulador de rastreamento de computador Quantum
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: 7403381b995ab660aa5cbc5a52b1e12c5c9ce442
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184972"
---
# <a name="invalidated-qubits-use-checker"></a><span data-ttu-id="0af69-103">Verificador de uso qubits invalidado</span><span class="sxs-lookup"><span data-stu-id="0af69-103">Invalidated Qubits Use Checker</span></span>

<span data-ttu-id="0af69-104">O `Invalidated Qubits Use Checker` é uma parte do computador Quantum [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) projetado para detectar possíveis bugs no código.</span><span class="sxs-lookup"><span data-stu-id="0af69-104">The `Invalidated Qubits Use Checker` is a part of the quantum computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="0af69-105">Considere a seguinte parte do código do Q # para ilustrar os problemas detectados pelo `Invalidated Qubits Use Checker`.</span><span class="sxs-lookup"><span data-stu-id="0af69-105">Consider the following piece of Q# code to illustrate the issues detected by the `Invalidated Qubits Use Checker`.</span></span>

```qsharp
operation UseReleasedQubitTest () : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="0af69-106">Quando `H` é aplicado a `q[0]` aponta para um qubit já liberado.</span><span class="sxs-lookup"><span data-stu-id="0af69-106">When `H` is applied to `q[0]` it points to an already released qubit.</span></span> <span data-ttu-id="0af69-107">Isso pode causar um comportamento indefinido.</span><span class="sxs-lookup"><span data-stu-id="0af69-107">This can cause undefined behavior.</span></span> <span data-ttu-id="0af69-108">Quando a `Invalidated Qubits Use Checker` estiver habilitada, a exceção `InvalidatedQubitsUseCheckerException` será lançada se uma operação for aplicada a um qubit já liberado.</span><span class="sxs-lookup"><span data-stu-id="0af69-108">When the `Invalidated Qubits Use Checker` is enabled, the exception `InvalidatedQubitsUseCheckerException` will be thrown if an operation is applied to an already released qubit.</span></span> <span data-ttu-id="0af69-109">Consulte a documentação da API em [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="0af69-109">See the API documentation on [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) for more details.</span></span>

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a><span data-ttu-id="0af69-110">Usando o verificador de uso invalidado do C# qubits em seu programa</span><span class="sxs-lookup"><span data-stu-id="0af69-110">Using the Invalidated Qubits Use Checker in your C# Program</span></span>

<span data-ttu-id="0af69-111">Veja a seguir um exemplo de C# código de driver para usar o computador Quantum `Trace
Simulator` com o `Invalidated Qubits Use Checker` habilitado:</span><span class="sxs-lookup"><span data-stu-id="0af69-111">The following is an example of C# driver code for using the quantum computer `Trace
Simulator` with the `Invalidated Qubits Use Checker` enabled:</span></span> 

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

<span data-ttu-id="0af69-112">A classe `QCTraceSimulatorConfiguration` armazena a configuração do simulador de rastreamento do computador Quantum e pode ser fornecida como um argumento para o Construtor `QCTraceSimulator`.</span><span class="sxs-lookup"><span data-stu-id="0af69-112">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="0af69-113">Quando `useInvalidatedQubitsUseChecker` é definido como true, o `Invalidated Qubits Use Checker` está habilitado.</span><span class="sxs-lookup"><span data-stu-id="0af69-113">When `useInvalidatedQubitsUseChecker` is set to true the `Invalidated Qubits Use Checker` is enabled.</span></span> <span data-ttu-id="0af69-114">Consulte a documentação da API em [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) e [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="0af69-114">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="0af69-115">Ver também</span><span class="sxs-lookup"><span data-stu-id="0af69-115">See also</span></span> ##

- <span data-ttu-id="0af69-116">A visão geral do [simulador de rastreamento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) do computador Quantum.</span><span class="sxs-lookup"><span data-stu-id="0af69-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
