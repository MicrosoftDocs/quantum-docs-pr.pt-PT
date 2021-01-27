---
title: Verificador de entradas distintos - Kit de Desenvolvimento Quântico
description: Saiba mais sobre o verificador de entradas distintos microsoft QDK, que utiliza o simulador de traços Quânticos para verificar o seu Q# código para potenciais conflitos com qubits partilhados.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8076a705b1960ae8e23be4cea87e613329a24f77
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858651"
---
# <a name="quantum-trace-simulator-distinct-inputs-checker"></a><span data-ttu-id="54d5d-103">Simulador de vestígios quânticos: verificador de entradas distintos</span><span class="sxs-lookup"><span data-stu-id="54d5d-103">Quantum trace simulator: distinct inputs checker</span></span>

<span data-ttu-id="54d5d-104">O verificador de entradas distintos faz parte do simulador de [traços quânticos](xref:microsoft.quantum.machines.qc-trace-simulator.intro)do Kit de Desenvolvimento Quântico.</span><span class="sxs-lookup"><span data-stu-id="54d5d-104">The distinct inputs checker is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="54d5d-105">Pode usá-lo para detetar potenciais bugs no código causados por conflitos com qubits partilhados.</span><span class="sxs-lookup"><span data-stu-id="54d5d-105">You can use it to detect potential bugs in the code caused by conflicts with shared qubits.</span></span> 

## <a name="conflicts-with-shared-qubits"></a><span data-ttu-id="54d5d-106">Conflitos com qubits partilhados</span><span class="sxs-lookup"><span data-stu-id="54d5d-106">Conflicts with shared qubits</span></span>

<span data-ttu-id="54d5d-107">Considere o seguinte pedaço de Q# código para ilustrar as questões detetadas pelo verificador de entradas distintos:</span><span class="sxs-lookup"><span data-stu-id="54d5d-107">Consider the following piece of Q# code to illustrate the issues detected by the distinct inputs checker:</span></span>

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

<span data-ttu-id="54d5d-108">Quando olhamos para este programa, podemos assumir que a ordem pela qual chama `op1` e `op2` não importa, porque são `q1` `q2` diferentes qubits e operações agindo em diferentes qubits.</span><span class="sxs-lookup"><span data-stu-id="54d5d-108">When you look at this program, you can assume that the order in which it calls `op1` and `op2` does not matter, because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> 

<span data-ttu-id="54d5d-109">Agora, considere este exemplo:</span><span class="sxs-lookup"><span data-stu-id="54d5d-109">Now, consider this example:</span></span>

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

<span data-ttu-id="54d5d-110">Note que `op1` e `op2` ambos são obtidos usando aplicação parcial e compartilham um qubit.</span><span class="sxs-lookup"><span data-stu-id="54d5d-110">Note that `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="54d5d-111">Quando se chama `ApplyBoth` este exemplo, o resultado da operação depende da ordem de `op1` e para dentro - não do que se esperaria que `op2` `ApplyBoth` acontecesse.</span><span class="sxs-lookup"><span data-stu-id="54d5d-111">When you call `ApplyBoth` in this example, the result of the operation depends on the order of `op1` and `op2` inside `ApplyBoth` - not what you would expect to happen.</span></span> <span data-ttu-id="54d5d-112">Quando ativa o verificador de entradas distintos, deteta tais situações e atira um `DistinctInputsCheckerException` .</span><span class="sxs-lookup"><span data-stu-id="54d5d-112">When you enable the distinct inputs checker, it detects such situations and throws a `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="54d5d-113">Para mais informações, consulte <xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.DistinctInputsCheckerException> na biblioteca da Q# API.</span><span class="sxs-lookup"><span data-stu-id="54d5d-113">For more information, see <xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.DistinctInputsCheckerException> in the Q# API library.</span></span>

## <a name="invoking-the-distinct-inputs-checker"></a><span data-ttu-id="54d5d-114">Invocando o verificador de entradas distintos</span><span class="sxs-lookup"><span data-stu-id="54d5d-114">Invoking the distinct inputs checker</span></span>

<span data-ttu-id="54d5d-115">Para executar o simulador de traços quânticos com o verificador de entradas distintos deve criar um <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> exemplo, definir a `UseDistinctInputsChecker` propriedade como **verdadeiro**, e, em seguida, criar um novo exemplo com como <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> o `QCTraceSimulatorConfiguration` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="54d5d-115">To run the quantum trace simulator with the distinct inputs checker you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseDistinctInputsChecker` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDistinctInputsChecker = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-distinct-inputs-checker-in-a-c-host-program"></a><span data-ttu-id="54d5d-116">Usando o verificador de entradas distinto num programa de anfitrião C#</span><span class="sxs-lookup"><span data-stu-id="54d5d-116">Using the distinct inputs checker in a C# host program</span></span>

<span data-ttu-id="54d5d-117">Segue-se um exemplo do programa de anfitrião C# que utiliza o simulador de traços quânticos com o verificador de entradas distinto ativado:</span><span class="sxs-lookup"><span data-stu-id="54d5d-117">The following is an example of C# host program that uses the quantum trace simulator with the distinct inputs checker enabled:</span></span>

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
            traceSimCfg.UseDistinctInputsChecker = true; //enables distinct inputs checker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="54d5d-118">Veja também</span><span class="sxs-lookup"><span data-stu-id="54d5d-118">See also</span></span>

- <span data-ttu-id="54d5d-119">A visão geral do [simulador de traços quânticos](xref:microsoft.quantum.machines.qc-trace-simulator.intro) do Kit de Desenvolvimento Quântico.</span><span class="sxs-lookup"><span data-stu-id="54d5d-119">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="54d5d-120">A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> referência da API.</span><span class="sxs-lookup"><span data-stu-id="54d5d-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="54d5d-121">A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> referência da API.</span><span class="sxs-lookup"><span data-stu-id="54d5d-121">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="54d5d-122">A <xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.DistinctInputsCheckerException> referência da API.</span><span class="sxs-lookup"><span data-stu-id="54d5d-122">The <xref:Microsoft.Quantum.Simulation.QCTraceSimulatorRuntime.DistinctInputsCheckerException> API reference.</span></span>
