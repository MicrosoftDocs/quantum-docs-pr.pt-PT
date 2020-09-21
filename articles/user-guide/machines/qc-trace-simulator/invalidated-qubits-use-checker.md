---
title: Qubits invalidados usam verificador - Kit de Desenvolvimento Quântico
description: Saiba mais sobre os qubits invalidados do Microsoft QDK use o verificador, que utiliza o simulador de traços Quânticos para verificar se o seu Q# código existe para qubits potencialmente inválidos.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: 18371b3798d0eaa12d4e7107f58f44379594619f
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90836000"
---
# <a name="quantum-trace-simulator-invalidated-qubits-use-checker"></a><span data-ttu-id="6de6e-103">Simulador de vestígios quânticos: qubits invalidados usam verificador</span><span class="sxs-lookup"><span data-stu-id="6de6e-103">Quantum trace simulator: invalidated qubits use checker</span></span>

<span data-ttu-id="6de6e-104">O verificador de qubits invalidado faz parte do simulador de [traços quânticos](xref:microsoft.quantum.machines.qc-trace-simulator.intro)do Kit de Desenvolvimento Quântico.</span><span class="sxs-lookup"><span data-stu-id="6de6e-104">The invalidated qubits use checker is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="6de6e-105">Pode usá-lo para detetar potenciais erros no código causados por qubits inválidos.</span><span class="sxs-lookup"><span data-stu-id="6de6e-105">You can use it to detect potential bugs in the code caused by invalid qubits.</span></span> 

## <a name="invalid-qubits"></a><span data-ttu-id="6de6e-106">Qubits inválidos</span><span class="sxs-lookup"><span data-stu-id="6de6e-106">Invalid qubits</span></span>

<span data-ttu-id="6de6e-107">Considere o seguinte pedaço de Q# código para ilustrar as questões detetadas pelo verificador de utilização de qubits invalidados:</span><span class="sxs-lookup"><span data-stu-id="6de6e-107">Consider the following piece of Q# code to illustrate the issues detected by the invalidated qubits use checker:</span></span>

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="6de6e-108">Quando aplica a `H` `q[0]` operação, aponta para um qubit já lançado, que pode causar um comportamento indefinido.</span><span class="sxs-lookup"><span data-stu-id="6de6e-108">When you apply the `H` operation to `q[0]`, it points to an already released qubit, which can cause undefined behavior.</span></span> <span data-ttu-id="6de6e-109">Quando o Verificador de Utilização de Qubits invalidado está ativado, lança a exceção `InvalidatedQubitsUseCheckerException` se o programa aplicar uma operação a um qubit já lançado.</span><span class="sxs-lookup"><span data-stu-id="6de6e-109">When the Invalidated Qubits Use Checker is enabled, it throws the exception `InvalidatedQubitsUseCheckerException` if the program applies an operation to an already released qubit.</span></span> <span data-ttu-id="6de6e-110">Para obter mais informações, consulte <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>.</span><span class="sxs-lookup"><span data-stu-id="6de6e-110">For more information, see <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>.</span></span>

## <a name="invoking-the-invalidated-qubits-use-checker"></a><span data-ttu-id="6de6e-111">Invocando os qubits invalidados usam verificador</span><span class="sxs-lookup"><span data-stu-id="6de6e-111">Invoking the invalidated qubits use checker</span></span>

<span data-ttu-id="6de6e-112">Para executar o simulador de traços quânticos com os qubits invalidados use o verificador deve criar uma <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instância, definir a `UseInvalidatedQubitsUseChecker` propriedade como **verdadeira**, e, em seguida, criar um novo exemplo com como <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> o `QCTraceSimulatorConfiguration` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="6de6e-112">To run the quantum trace simulator with the invalidated qubits use checker you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseInvalidatedQubitsUseChecker` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseInvalidatedQubitsUseChecker = true;
var sim = new QCTraceSimulator(config);
```


## <a name="using-the-invalidated-qubits-use-checker-in-a-c-host-program"></a><span data-ttu-id="6de6e-113">Utilizando os qubits invalidados, utilize o verificador num programa de anfitrião C#</span><span class="sxs-lookup"><span data-stu-id="6de6e-113">Using the invalidated qubits use checker in a C# host program</span></span>

<span data-ttu-id="6de6e-114">Segue-se um exemplo de programas de anfitrião C# que utilizam o simulador de traços quânticos com o verificador de qubits invalidado ativado:</span><span class="sxs-lookup"><span data-stu-id="6de6e-114">The following is an example of C# host programs that uses the quantum trace simulator with the invalidated qubits use checker enabled:</span></span> 

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
            traceSimCfg.UseInvalidatedQubitsUseChecker = true; // enables UseInvalidatedQubitsUseChecker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="6de6e-115">Ver também</span><span class="sxs-lookup"><span data-stu-id="6de6e-115">See also</span></span>

- <span data-ttu-id="6de6e-116">A visão geral do [simulador de traços quânticos](xref:microsoft.quantum.machines.qc-trace-simulator.intro) do Kit de Desenvolvimento Quântico.</span><span class="sxs-lookup"><span data-stu-id="6de6e-116">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="6de6e-117">A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> referência da API.</span><span class="sxs-lookup"><span data-stu-id="6de6e-117">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="6de6e-118">A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> referência da API.</span><span class="sxs-lookup"><span data-stu-id="6de6e-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="6de6e-119">A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException> referência da API.</span><span class="sxs-lookup"><span data-stu-id="6de6e-119">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException> API reference.</span></span>