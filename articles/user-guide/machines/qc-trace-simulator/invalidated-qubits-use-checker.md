---
title: Qubits invalidados usam verificador - Kit de Desenvolvimento Quântico
description: Saiba mais sobre os qubits invalidados do Microsoft QDK use o verificador, que utiliza o simulador de traços Quânticos para verificar se o seu Q# código existe para qubits potencialmente inválidos.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: c451747badba03801bd4ecd419420f131ac502d6
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868292"
---
# <a name="quantum-trace-simulator-invalidated-qubits-use-checker"></a>Simulador de vestígios quânticos: qubits invalidados usam verificador

O verificador de qubits invalidado faz parte do simulador de [traços quânticos](xref:microsoft.quantum.machines.qc-trace-simulator.intro)do Kit de Desenvolvimento Quântico. Pode usá-lo para detetar potenciais erros no código causados por qubits inválidos. 

## <a name="invalid-qubits"></a>Qubits inválidos

Considere o seguinte pedaço de Q# código para ilustrar as questões detetadas pelo verificador de utilização de qubits invalidados:

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

Quando aplica a `H` `q[0]` operação, aponta para um qubit já lançado, que pode causar um comportamento indefinido. Quando o Verificador de Utilização de Qubits invalidado está ativado, lança a exceção `InvalidatedQubitsUseCheckerException` se o programa aplicar uma operação a um qubit já lançado. Para obter mais informações, consulte <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>.

## <a name="invoking-the-invalidated-qubits-use-checker"></a>Invocando os qubits invalidados usam verificador

Para executar o simulador de traços quânticos com os qubits invalidados use o verificador deve criar uma <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instância, definir a `UseInvalidatedQubitsUseChecker` propriedade como **verdadeira**, e, em seguida, criar um novo exemplo com como <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> o `QCTraceSimulatorConfiguration` parâmetro. 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseInvalidatedQubitsUseChecker = true;
var sim = new QCTraceSimulator(config);
```


## <a name="using-the-invalidated-qubits-use-checker-in-a-c-host-program"></a>Utilizando os qubits invalidados, utilize o verificador num programa de anfitrião C#

Segue-se um exemplo de programas de anfitrião C# que utilizam o simulador de traços quânticos com o verificador de qubits invalidado ativado: 

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

## <a name="see-also"></a>Ver também

- A visão geral do [simulador de traços quânticos](xref:microsoft.quantum.machines.qc-trace-simulator.intro) do Kit de Desenvolvimento Quântico.
- A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> referência da API.
- A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> referência da API.
- A <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException> referência da API.