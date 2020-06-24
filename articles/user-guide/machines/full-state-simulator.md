---
title: Simulador de Estado Completo
description: Saiba como executar os seus programas Q# no Microsoft Quantum Development Kit Full State Simulator.
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: f73abbc4366b003e4b22366ed83ca9c897737307
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275643"
---
# <a name="quantum-development-kit-full-state-simulator"></a>Kit de desenvolvimento quântico full state simulator

O Quantum Development Kit fornece um simulador quântico de estado completo semelhante ao [LIQ$Ui/rangle$](http://stationq.github.io/Liquid/) da Microsoft Research.
Este simulador pode ser usado para executar e depurar algoritmos quânticos escritos em Q# no seu computador.

Este simulador quântico é exposto através da `QuantumSimulator` aula. Para utilizar o simulador, basta criar uma instância desta classe e passá-la para o `Run` método da operação quântica que pretende executar juntamente com o resto dos parâmetros:

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a>IDisposable

A `QuantumSimulator` classe <xref:System.IDisposable> implementa, portanto, o `Dispose` método deve ser chamado uma vez que a instância do simulador não é mais usada. A melhor maneira de o fazer é embrulhar o simulador dentro de uma `using` declaração, como no exemplo acima.

## <a name="seed"></a>Sementes

Usa `QuantumSimulator` um gerador de números aleatórios para simular aleatoriedade quântica. Para efeitos de teste, por vezes é útil ter resultados determinísticos. Isto pode ser conseguido fornecendo uma semente para o gerador de números aleatórios no `QuantumSimulator` construtor através do `randomNumberGeneratorSeed` parâmetro:

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a>Fios

Utiliza `QuantumSimulator` [OpenMP](http://www.openmp.org/) para paralelizar a álgebra linear necessária. Por predefinição, o OpenMP utiliza todos os threads de hardware disponíveis, o que significa que os programas com pequenos números de qubits serão normalmente executados lentamente, pois a coordenação necessária diminuirá o trabalho real. Isto pode ser corrigido definindo a variável ambiente `OMP_NUM_THREADS` para um número pequeno. Como regra geral muito superficial, um thread é bom para um máximo de quatro qubits e, em seguida, um thread adicional por qubit é bom, embora isto seja altamente dependente do algoritmo.

