---
title: Simulador de rastreio do computador quântico | Microsoft Docs
description: Descrição geral do simulador de rastreio do computador quântico
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: 7fd9d1fa4fb3c5dd216d846038abd40454ece2e8
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035124"
---
# <a name="quantum-trace-simulator"></a>Simulador de Rastreio Quântico

O simulador de rastreio do computador quântico da Microsoft executa um programa quântico sem simular verdadeiramente o estado de um computador quântico.  Por esse motivo, o simulador de rastreio pode executar programas quânticos que utilizam milhares de qubits.  É útil para duas finalidades principais: 

* Depuração de código clássico que faz parte de um programa quântico. 
* Estimativa dos recursos necessários para executar uma determinada instância de um programa quântico num computador quântico.

O simulador de rastreio recorre a informações adicionais fornecidas pelo utilizador quando têm de ser executadas medições. Veja a secção [Fornecer a probabilidade de resultados de medição](#providing-the-probability-of-measurement-outcomes) para obter mais detalhes. 

## <a name="providing-the-probability-of-measurement-outcomes"></a>Fornecer a Probabilidade de Resultados de Medição

Existem dois tipos de medições que aparecem em algoritmos quânticos. O primeiro tipo desempenha uma função auxiliar, na qual o utilizador costuma saber a probabilidade dos resultados. Neste caso, o utilizador pode escrever <xref:microsoft.quantum.primitive.assertprob> no espaço de nomes <xref:microsoft.quantum.primitive> para expressar esse mesmo conhecimento. O exemplo seguinte ilustra isso mesmo:

```qsharp
operation Teleportation (source : Qubit, target : Qubit) : Unit {

    using (ancilla = Qubit()) {

        H(ancilla);
        CNOT(ancilla, target);

        CNOT(source, ancilla);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [ancilla], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(ancilla) == One) { X(target); X(ancilla); }
    }
}
```

Quando o simulador de rastreio executar `AssertProb`, vai registar que a medição de `PauliZ` em `source` e `ancilla` deve receber um resultado de `Zero` com uma probabilidade de 0,5. Quando o simulador executar `M` mais tarde, detetará que os valores registados das probabilidades de resultado e `M` devolverão `Zero` ou `One` com uma probabilidade de 0,5. Quando o mesmo código for executado num simulador que monitoriza o estado quântico, esse simulador verificará se as probabilidades fornecidas em `AssertProb` estão corretas.

## <a name="running-your-program-with-the-quantum-computer-trace-simulator"></a>Executar o Programa com o Simulador de Rastreio do Computador Quântico 

O simulador de rastreio do computador quântico pode ser visualizado tal como outro computador de destino. O programa do controlador C# para o utilizar é muito semelhante ao de qualquer outro Simulador quântico: 

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
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

Note que, se houver pelo menos uma medição não anotada com `AssertProb`, o simulador lançará `UnconstrainedMeasurementException` a partir do espaço de nomes `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators`. Veja a documentação da API em [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException) para obter mais detalhes.

Além de executar programas quânticos, o simulador de rastreio inclui cinco componentes para detetar erros em programas e executar estimativas de recursos de programas quânticos: 

* [Verificador de Entradas Distintas](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)
* [Verificador de Utilização de Qubits Invalidados](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)
* [Contador de Operações Primitivas](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)
* [Contador de Profundidade de Circuitos](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)
* [Contador de Largura de Circuitos](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)

Cada um destes componentes pode ser ativado ao definir os sinalizadores adequados em `QCTraceSimulatorConfiguration`. Mais detalhes sobre como utilizar cada um desses componentes são fornecidos nos ficheiros de referência correspondentes. Veja a documentação da API sobre [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) para obter detalhes específicos.

## <a name="see-also"></a>Consulte também
Referência C# do [simulador de rastreio](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) do computador quântico 

