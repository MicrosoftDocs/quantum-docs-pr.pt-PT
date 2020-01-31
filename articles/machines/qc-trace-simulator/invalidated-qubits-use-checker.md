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
# <a name="invalidated-qubits-use-checker"></a><span data-ttu-id="68ab3-103">Verificador de utilização de Qubits invalidados</span><span class="sxs-lookup"><span data-stu-id="68ab3-103">Invalidated Qubits Use Checker</span></span>

<span data-ttu-id="68ab3-104">O `Invalidated Qubits Use Checker` é uma parte do computador quântico [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) projetado para detetar potenciais bugs no código.</span><span class="sxs-lookup"><span data-stu-id="68ab3-104">The `Invalidated Qubits Use Checker` is a part of the quantum computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="68ab3-105">Considere a seguinte peça do código Q# para ilustrar as questões detetadas pelo `Invalidated Qubits Use Checker`.</span><span class="sxs-lookup"><span data-stu-id="68ab3-105">Consider the following piece of Q# code to illustrate the issues detected by the `Invalidated Qubits Use Checker`.</span></span>

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="68ab3-106">Quando `H` é aplicada à `q[0]` aponta para um qubit já lançado.</span><span class="sxs-lookup"><span data-stu-id="68ab3-106">When `H` is applied to `q[0]` it points to an already released qubit.</span></span> <span data-ttu-id="68ab3-107">Isto pode causar um comportamento indefinido.</span><span class="sxs-lookup"><span data-stu-id="68ab3-107">This can cause undefined behavior.</span></span> <span data-ttu-id="68ab3-108">Quando o `Invalidated Qubits Use Checker` estiver ativado, a exceção `InvalidatedQubitsUseCheckerException` será lançada se uma operação for aplicada a um qubit já lançado.</span><span class="sxs-lookup"><span data-stu-id="68ab3-108">When the `Invalidated Qubits Use Checker` is enabled, the exception `InvalidatedQubitsUseCheckerException` will be thrown if an operation is applied to an already released qubit.</span></span> <span data-ttu-id="68ab3-109">Consulte a documentação da API sobre [invalidadoQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) para mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="68ab3-109">See the API documentation on [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) for more details.</span></span>

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a><span data-ttu-id="68ab3-110">Utilização do Verificador de Utilização C# de Qubits Invalidados no seu Programa</span><span class="sxs-lookup"><span data-stu-id="68ab3-110">Using the Invalidated Qubits Use Checker in your C# Program</span></span>

<span data-ttu-id="68ab3-111">Segue-se um C# exemplo de código do condutor para a utilização do `Trace
Simulator` informático quântico com o `Invalidated Qubits Use Checker` habilitado:</span><span class="sxs-lookup"><span data-stu-id="68ab3-111">The following is an example of C# driver code for using the quantum computer `Trace
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

<span data-ttu-id="68ab3-112">A classe `QCTraceSimulatorConfiguration` armazena a configuração do simulador de vestígios de computador quântico e pode ser fornecida como um argumento para o construtor `QCTraceSimulator`.</span><span class="sxs-lookup"><span data-stu-id="68ab3-112">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="68ab3-113">Quando `useInvalidatedQubitsUseChecker` for verdadeira, o `Invalidated Qubits Use Checker` está ativado.</span><span class="sxs-lookup"><span data-stu-id="68ab3-113">When `useInvalidatedQubitsUseChecker` is set to true the `Invalidated Qubits Use Checker` is enabled.</span></span> <span data-ttu-id="68ab3-114">Consulte a documentação da API no [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) e na [QCTraceSimulatorConfigura](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="68ab3-114">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="68ab3-115">Ver também</span><span class="sxs-lookup"><span data-stu-id="68ab3-115">See also</span></span> ##

- <span data-ttu-id="68ab3-116">A visão geral do simulador de [rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro) do computador quântico.</span><span class="sxs-lookup"><span data-stu-id="68ab3-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
