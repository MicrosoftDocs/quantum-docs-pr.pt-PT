---
title: Simulador de rastreio quântico - Quantum Development kit
description: Aprenda a utilizar o simulador de rastreio de computador quântico da Microsoft para depurar código clássico e para calcular os requisitos de recursos de um programa Q#.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5d5efef037ff236bd040dfd88e94f7f3dd331aef
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868224"
---
# <a name="microsoft-quantum-development-kit-qdk-quantum-trace-simulator"></a>Simulador de rastreio quântico do Microsoft Quantum Development kit (QDK)

A classe <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> do QDK executa um programa quântico sem, na realidade, simular o estado de um computador quântico. Por esse motivo, o simulador de rastreio quântico pode executar programas quânticos que utilizam milhares de qubits.  É útil para duas finalidades principais: 

* Depuração de código clássico que faz parte de um programa quântico. 
* Estimativa dos recursos necessários para executar uma determinada instância de um programa quântico num computador quântico. Na verdade, o [Avaliador de recursos](xref:microsoft.quantum.machines.resources-estimator), que oferece um conjunto de métricas mais limitado, foi concebido com base no simulador de rastreio.

## <a name="invoking-the-quantum-trace-simulator"></a>Invocar o simulador de rastreio quântico

Pode utilizar o simulador de rastreio quântico para executar qualquer operação Q#.

Tal como sucede com outros computadores de destino, vai criar primeiro uma instância da classe `QCTraceSimulator` e, depois, transmiti-la como o primeiro parâmetro do método `Run` de uma operação.

Tenha em conta que, ao contrário da classe `QuantumSimulator`, a classe `QCTraceSimulator` não implementa a interface <xref:System.IDisposable>, pelo que não precisa de a incluir dentro de uma instrução `using`.

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
            QCTraceSimulator sim = new QCTraceSimulator();
            var res = MyQuantumProgram.Run(sim).Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="providing-the-probability-of-measurement-outcomes"></a>Fornecer a probabilidade de resultados de medições

Uma vez que o simulador de rastreio quântico não simula o estado quântico em si, não pode calcular a probabilidade de resultados de medições numa operação. 

Consequentemente, se uma operação incluir medições, tem de fornecer explicitamente essas probabilidades com a operação <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> a partir do espaço de nomes <xref:microsoft.quantum.diagnostics>. O exemplo seguinte ilustra isso mesmo:

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertMeasurementProbability([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertMeasurementProbability([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

Quando o simulador de rastreio quântico encontrar `AssertMeasurementProbability`, regista que a medição `PauliZ` em `source` e em `q` deverá produzir o resultado `Zero`, com a probabilidade de **0,5**. Quando executa a operação `M` mais tarde, localiza os valores registados das probabilidades dos resultados e `M` devolve `Zero` ou `One`, com a probabilidade de **0,5**. Quando o mesmo código for executado num simulador que rastreia o estado quântico, esse simulador verificará se as probabilidades fornecidas em `AssertMeasurementProbability` estão corretas.

Note que, se houver pelo menos uma operação de medição não anotada com `AssertMeasurementProbability`, o simulador emitirá [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception).

## <a name="quantum-trace-simulator-tools"></a>Ferramentas do simulador de rastreio quântico

O QDK inclui cinco ferramentas que pode utilizar com o simulador de rastreio quântico para detetar erros nos seus programas e realizar estimativas de recursos dos programas quânticos: 

|Ferramenta | Descrição |
|-----| -----|
|[Verificador de entradas distintas](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) |Verifica potenciais conflitos com qubits partilhados |
|[Verificador de utilização de qubits invalidados](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)  |Verifica se o programa aplica uma operação a um qubit que já foi lançado |
|[Contador de operações primitivas](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)  | Conta o número de execuções primitivas que todas as operações invocadas num programa quântico utilizaram  |
|[Contador de profundidade](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)  |Recolhe contagens que representam o limite inferior da profundidade de todas as operações invocadas num programa quântico   |
|[Contador de largura](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)  |Conta o número de qubits alocados e emprestados por cada operação num programa quântico |

Para ativar cada uma destas ferramentas, defina os sinalizadores correspondentes em `QCTraceSimulatorConfiguration` e transmita a configuração para a declaração `QCTraceSimulator`. Para obter informações sobre a utilização de cada uma das ferramentas, veja as ligações na lista anterior. Para obter mais informações sobre a configuração de `QCTraceSimulator`, veja [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).

## <a name="qctracesimulator-methods"></a>Métodos QCTraceSimulator

O `QCTraceSimulator` tem diversos métodos incorporados para obter os valores das métricas rastreadas durante uma operação quântica. Podem ser encontrados exemplos dos métodos [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) e [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) nos artigos [Contador de operações primitivas](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), [Contador de profundidade](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) e [Contador de largura](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter). Para obter informações relativas a todos os métodos disponíveis, veja [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) na referência da API de Q#.  

## <a name="see-also"></a>Consulte também

- [Avaliador de recursos quânticos](xref:microsoft.quantum.machines.resources-estimator)
- [Simulador Toffoli quântico](xref:microsoft.quantum.machines.toffoli-simulator)
- [Simulador de estado completo quântico](xref:microsoft.quantum.machines.full-state-simulator) 