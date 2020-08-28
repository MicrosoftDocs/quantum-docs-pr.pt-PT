---
title: Simulador quântico de estado completo - Kit de Desenvolvimento Quântico
description: Aprenda a executar os seus Q# programas no simulador completo do Microsoft Quantum Development Kit.
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: a27cece9858d62814b9d80c47e61c5d7d3b8c885
ms.sourcegitcommit: 11bd357baeb6ab53a402882979e75964d0869b57
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/27/2020
ms.locfileid: "88992228"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a>Kit de Desenvolvimento Quântico (QDK) simulador de estado completo

O QDK fornece um simulador de estado completo que simula uma máquina quântica no seu computador local. Você pode usar o simulador de estado completo para executar e depurar algoritmos quânticos escritos em Q# , usando até 30 qubits. O simulador de estado completo é semelhante ao simulador quântico usado na plataforma  [LIQ$Ui/rangle$](http://stationq.github.io/Liquid/) da Microsoft Research.

## <a name="invoking-and-running-the-full-state-simulator"></a>Invocando e executando o simulador de estado completo

Expões o simulador de estado completo através da `QuantumSimulator` aula. Para mais detalhes, consulte [Formas de executar um Q# programa](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-simulator-from-c"></a>Invocando o simulador de C #

Crie uma instância da `QuantumSimulator` classe e, em seguida, passe-a para o `Run` método de uma operação quântica, juntamente com quaisquer parâmetros adicionais.
```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

Como a `QuantumSimulator` classe implementa a <xref:System.IDisposable> interface, deve ligar para o método `Dispose` uma vez que já não precisa da instância do simulador. A melhor maneira de o fazer é embrulhar a declaração e as operações do simulador dentro de uma declaração [de utilização,](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) que automaticamente chama o `Dispose` método.

### <a name="invoking-the-simulator-from-python"></a>Invocando o simulador de Python

Utilizar o método [simulado da](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) Q# biblioteca Python com a operação importada: Q#

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a>Invocando o simulador da linha de comando

Ao executar um Q# programa a partir da linha de comando, o simulador de estado completo é a máquina alvo predefinido. Opcionalmente, pode utilizar o parâmetro **--simulador** (ou **atalho -s** para especificar a máquina-alvo desejada. Ambos os comandos seguintes executam um programa utilizando o simulador de estado completo. 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a>Invocando o simulador dos Cadernos Juptyer

Use o comando mágico I Q# [%simular](xref:microsoft.quantum.iqsharp.magic-ref.simulate) para executar a Q# operação.

```
%simulate myOperation
```
## <a name="seeding-the-simulator"></a>Semear o simulador

Por predefinição, o simulador de estado completo utiliza um gerador de números aleatórios para simular aleatoriedade quântica. Para efeitos de teste, por vezes é útil ter resultados determinísticos. Num programa C# pode fazê-lo fornecendo uma semente para o gerador de números aleatórios no `QuantumSimulator` construtor através do `randomNumberGeneratorSeed` parâmetro.

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="configuring-threads"></a>Fios de configuração

O simulador de estado completo utiliza [o OpenMP](http://www.openmp.org/) para paralelizar a álgebra linear necessária. Por padrão, o OpenMP utiliza todos os fios de hardware disponíveis, o que significa que os programas com um pequeno número de qubits muitas vezes funcionam lentamente porque a coordenação que é necessária anãs o trabalho real. Pode fixá-lo definindo a variável ambiente `OMP_NUM_THREADS` para um número pequeno. Como regra geral do polegar, configuure um fio para até quatro qubits, e, em seguida, um fio adicional por qubit. Pode ser necessário ajustar a variável dependendo do seu algoritmo.

## <a name="see-also"></a>Consulte também

- [Avaliador de recursos quânticos](xref:microsoft.quantum.machines.resources-estimator)
- [Simulador Toffoli quântico](xref:microsoft.quantum.machines.toffoli-simulator)
- [Simulador de vestígios quânticos](xref:microsoft.quantum.machines.qc-trace-simulator.intro)