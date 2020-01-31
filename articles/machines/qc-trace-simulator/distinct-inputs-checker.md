---
title: Verificador de inputs distintos  Simulador de vestígios de computador quântico  Microsoft Docs
description: Descrição geral do simulador de rastreio do computador quântico
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 3c21a54f5da83bf1ea0792e79cc773be5fba71e8
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820968"
---
# <a name="distinct-inputs-checker"></a><span data-ttu-id="ec72d-103">Verificador de inputs distintos</span><span class="sxs-lookup"><span data-stu-id="ec72d-103">Distinct Inputs Checker</span></span>

<span data-ttu-id="ec72d-104">O `Distinct Inputs Checker` faz parte do simulador de [rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro)do computador quântico.</span><span class="sxs-lookup"><span data-stu-id="ec72d-104">The `Distinct Inputs Checker` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="ec72d-105">Foi concebido para detetar potenciais bugs no código.</span><span class="sxs-lookup"><span data-stu-id="ec72d-105">It is designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="ec72d-106">Considere a seguinte peça do código Q# para ilustrar as questões detetadas por este pacote:</span><span class="sxs-lookup"><span data-stu-id="ec72d-106">Consider the following piece of Q# code to illustrate the issues detected by this package:</span></span>

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

<span data-ttu-id="ec72d-107">Quando o utilizador olha para este programa, assume que a ordem em que `op1` e `op2` são chamados não importa porque `q1` e `q2` são diferentes qubits e operações agindo em diferentes qubits comutados.</span><span class="sxs-lookup"><span data-stu-id="ec72d-107">When the user looks at this program, they assume that the order in which `op1` and `op2` are called does not matter because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> <span data-ttu-id="ec72d-108">Consideremos agora um exemplo, em que esta operação é utilizada:</span><span class="sxs-lookup"><span data-stu-id="ec72d-108">Let us now consider an example, where this operation is used:</span></span>

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

<span data-ttu-id="ec72d-109">Agora `op1` e `op2` são ambos obtidos usando aplicação parcial e partilham um qubit.</span><span class="sxs-lookup"><span data-stu-id="ec72d-109">Now `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="ec72d-110">Quando o utilizador ligar `ApplyBoth` no exemplo acima do resultado da operação dependerá da ordem de `op1` e `op2` no interior `ApplyBoth`.</span><span class="sxs-lookup"><span data-stu-id="ec72d-110">When the user calls `ApplyBoth` in the example above the result of the operation will depend on the order of `op1` and `op2` inside `ApplyBoth`.</span></span> <span data-ttu-id="ec72d-111">Isto definitivamente não é o que o utilizador esperaria que acontecesse.</span><span class="sxs-lookup"><span data-stu-id="ec72d-111">This is definitely not what the user would expect to happen.</span></span> <span data-ttu-id="ec72d-112">O `Distinct Inputs Checker` detetará tais situações quando ativado e lançará `DistinctInputsCheckerException`.</span><span class="sxs-lookup"><span data-stu-id="ec72d-112">The `Distinct Inputs Checker` will detect such situations when enabled and will throw `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="ec72d-113">Consulte a documentação da API sobre [a DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="ec72d-113">See the API documentation on [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) for more details.</span></span>

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a><span data-ttu-id="ec72d-114">Utilização do Verificador de C# Inputs Distintos no seu Programa</span><span class="sxs-lookup"><span data-stu-id="ec72d-114">Using the Distinct Inputs Checker in your C# Program</span></span>

<span data-ttu-id="ec72d-115">Segue-se um C# exemplo de código do condutor para a utilização do simulador de vestígios de computador quântico com o `Distinct Inputs Checker` habilitado:</span><span class="sxs-lookup"><span data-stu-id="ec72d-115">The following is an example of C# driver code for using the quantum computer trace simulator with the `Distinct Inputs Checker` enabled:</span></span>

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

<span data-ttu-id="ec72d-116">A classe `QCTraceSimulatorConfiguration` armazena a configuração do simulador de vestígios de computador quântico e pode ser fornecida como um argumento para o construtor `QCTraceSimulator`.</span><span class="sxs-lookup"><span data-stu-id="ec72d-116">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="ec72d-117">Quando `useDistinctInputsChecker` for verdadeira, o `Distinct Inputs Checker` está ativado.</span><span class="sxs-lookup"><span data-stu-id="ec72d-117">When `useDistinctInputsChecker` is set to true the `Distinct Inputs Checker` is enabled.</span></span> <span data-ttu-id="ec72d-118">Consulte a documentação da API no [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) e na [QCTraceSimulatorConfigura](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="ec72d-118">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec72d-119">Ver também</span><span class="sxs-lookup"><span data-stu-id="ec72d-119">See also</span></span>

- <span data-ttu-id="ec72d-120">A visão geral do simulador de [rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro) do computador quântico.</span><span class="sxs-lookup"><span data-stu-id="ec72d-120">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
