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
# <a name="distinct-inputs-checker"></a><span data-ttu-id="04dc8-103">Verificador de entradas distintos</span><span class="sxs-lookup"><span data-stu-id="04dc8-103">Distinct Inputs Checker</span></span>

<span data-ttu-id="04dc8-104">Faz `Distinct Inputs Checker` parte do [simulador](xref:microsoft.quantum.machines.qc-trace-simulator.intro)de rastreio de computador quântico.</span><span class="sxs-lookup"><span data-stu-id="04dc8-104">The `Distinct Inputs Checker` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="04dc8-105">Foi concebido para detetar potenciais bugs no código.</span><span class="sxs-lookup"><span data-stu-id="04dc8-105">It is designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="04dc8-106">Considere o seguinte pedaço de código Q# para ilustrar as questões detetadas por este pacote:</span><span class="sxs-lookup"><span data-stu-id="04dc8-106">Consider the following piece of Q# code to illustrate the issues detected by this package:</span></span>

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

<span data-ttu-id="04dc8-107">Quando o utilizador olha para este programa, assume que a ordem em que `op1` e `op2` são chamados não importa porque e são `q1` `q2` diferentes qubits e operações agindo em diferentes qubits comuta.</span><span class="sxs-lookup"><span data-stu-id="04dc8-107">When the user looks at this program, they assume that the order in which `op1` and `op2` are called does not matter because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> <span data-ttu-id="04dc8-108">Consideremos agora um exemplo, onde esta operação é utilizada:</span><span class="sxs-lookup"><span data-stu-id="04dc8-108">Let us now consider an example, where this operation is used:</span></span>

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

<span data-ttu-id="04dc8-109">Agora `op1` e ambos são `op2` obtidos usando aplicação parcial e compartilham um qubit.</span><span class="sxs-lookup"><span data-stu-id="04dc8-109">Now `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="04dc8-110">Quando o utilizador ligar `ApplyBoth` no exemplo acima, o resultado da operação dependerá da ordem de `op1` e para dentro `op2` `ApplyBoth` .</span><span class="sxs-lookup"><span data-stu-id="04dc8-110">When the user calls `ApplyBoth` in the example above the result of the operation will depend on the order of `op1` and `op2` inside `ApplyBoth`.</span></span> <span data-ttu-id="04dc8-111">Isto definitivamente não é o que o utilizador esperaria que acontecesse.</span><span class="sxs-lookup"><span data-stu-id="04dc8-111">This is definitely not what the user would expect to happen.</span></span> <span data-ttu-id="04dc8-112">A `Distinct Inputs Checker` vontade detetará tais situações quando ativada e lançará `DistinctInputsCheckerException` .</span><span class="sxs-lookup"><span data-stu-id="04dc8-112">The `Distinct Inputs Checker` will detect such situations when enabled and will throw `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="04dc8-113">Consulte a documentação da API sobre [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="04dc8-113">See the API documentation on [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) for more details.</span></span>

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a><span data-ttu-id="04dc8-114">Utilizando o verificador de entradas distintos no seu programa C#</span><span class="sxs-lookup"><span data-stu-id="04dc8-114">Using the Distinct Inputs Checker in your C# Program</span></span>

<span data-ttu-id="04dc8-115">Segue-se um exemplo do código do controlador C# para a utilização do simulador de traços de computador quântico com o `Distinct Inputs Checker` ativado:</span><span class="sxs-lookup"><span data-stu-id="04dc8-115">The following is an example of C# driver code for using the quantum computer trace simulator with the `Distinct Inputs Checker` enabled:</span></span>

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

<span data-ttu-id="04dc8-116">A classe `QCTraceSimulatorConfiguration` armazena a configuração do simulador de traços de computador quântico e pode ser fornecida como um argumento para o `QCTraceSimulator` construtor.</span><span class="sxs-lookup"><span data-stu-id="04dc8-116">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="04dc8-117">Quando `useDistinctInputsChecker` é definido para verdadeiro o está `Distinct Inputs Checker` ativado.</span><span class="sxs-lookup"><span data-stu-id="04dc8-117">When `useDistinctInputsChecker` is set to true the `Distinct Inputs Checker` is enabled.</span></span> <span data-ttu-id="04dc8-118">Consulte a documentação da API sobre [o QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) e [a QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) para mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="04dc8-118">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="04dc8-119">Ver também</span><span class="sxs-lookup"><span data-stu-id="04dc8-119">See also</span></span>

- <span data-ttu-id="04dc8-120">A visão geral [do Trace Simulator do](xref:microsoft.quantum.machines.qc-trace-simulator.intro) computador quântico.</span><span class="sxs-lookup"><span data-stu-id="04dc8-120">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
