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
# <a name="invalidated-qubits-use-checker"></a><span data-ttu-id="03791-103">Qubits invalidados usam verificador</span><span class="sxs-lookup"><span data-stu-id="03791-103">Invalidated Qubits Use Checker</span></span>

<span data-ttu-id="03791-104">É `Invalidated Qubits Use Checker` uma parte do computador quântico [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) projetado para detetar potenciais bugs no código.</span><span class="sxs-lookup"><span data-stu-id="03791-104">The `Invalidated Qubits Use Checker` is a part of the quantum computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="03791-105">Considere o seguinte pedaço de código Q# para ilustrar as questões detetadas pelo `Invalidated Qubits Use Checker` .</span><span class="sxs-lookup"><span data-stu-id="03791-105">Consider the following piece of Q# code to illustrate the issues detected by the `Invalidated Qubits Use Checker`.</span></span>

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="03791-106">Quando `H` é aplicado a ele aponta para um `q[0]` qubit já lançado.</span><span class="sxs-lookup"><span data-stu-id="03791-106">When `H` is applied to `q[0]` it points to an already released qubit.</span></span> <span data-ttu-id="03791-107">Isto pode causar um comportamento indefinido.</span><span class="sxs-lookup"><span data-stu-id="03791-107">This can cause undefined behavior.</span></span> <span data-ttu-id="03791-108">Quando a `Invalidated Qubits Use Checker` ativação estiver ativada, a exceção `InvalidatedQubitsUseCheckerException` será lançada se uma operação for aplicada a um qubit já libertado.</span><span class="sxs-lookup"><span data-stu-id="03791-108">When the `Invalidated Qubits Use Checker` is enabled, the exception `InvalidatedQubitsUseCheckerException` will be thrown if an operation is applied to an already released qubit.</span></span> <span data-ttu-id="03791-109">Consulte a documentação da API sobre [invalidadoQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="03791-109">See the API documentation on [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) for more details.</span></span>

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a><span data-ttu-id="03791-110">Utilizando o verificador de utilização de qubits invalidados no seu programa C#</span><span class="sxs-lookup"><span data-stu-id="03791-110">Using the Invalidated Qubits Use Checker in your C# Program</span></span>

<span data-ttu-id="03791-111">Segue-se um exemplo do código do controlador C# para a utilização do computador quântico `Trace
Simulator` com o `Invalidated Qubits Use Checker` ativado:</span><span class="sxs-lookup"><span data-stu-id="03791-111">The following is an example of C# driver code for using the quantum computer `Trace
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

<span data-ttu-id="03791-112">A classe `QCTraceSimulatorConfiguration` armazena a configuração do simulador de traços de computador quântico e pode ser fornecida como um argumento para o `QCTraceSimulator` construtor.</span><span class="sxs-lookup"><span data-stu-id="03791-112">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="03791-113">Quando `useInvalidatedQubitsUseChecker` é definido para verdadeiro o está `Invalidated Qubits Use Checker` ativado.</span><span class="sxs-lookup"><span data-stu-id="03791-113">When `useInvalidatedQubitsUseChecker` is set to true the `Invalidated Qubits Use Checker` is enabled.</span></span> <span data-ttu-id="03791-114">Consulte a documentação da API sobre [o QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) e [a QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) para mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="03791-114">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="03791-115">Ver também</span><span class="sxs-lookup"><span data-stu-id="03791-115">See also</span></span> ##

- <span data-ttu-id="03791-116">A visão geral [do Trace Simulator do](xref:microsoft.quantum.machines.qc-trace-simulator.intro) computador quântico.</span><span class="sxs-lookup"><span data-stu-id="03791-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
