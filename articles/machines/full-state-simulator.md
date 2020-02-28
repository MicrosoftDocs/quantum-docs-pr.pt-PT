---
title: Simulador de Estado Completo
description: Aprenda a executar os seus programas Q# no Microsoft Quantum Development Kit Full State Simulator.
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: f73abbc4366b003e4b22366ed83ca9c897737307
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906122"
---
# <a name="quantum-development-kit-full-state-simulator"></a>Simulador de Estado completo do kit de desenvolvimento quântico

O Kit de Desenvolvimento Quântico fornece um simulador quântico de estado completo semelhante ao [LIQ$Uirangle$ da](http://stationq.github.io/Liquid/) Microsoft Research.
Este simulador pode ser usado para executar e depurar algoritmos quânticos escritos em Q# no seu computador.

Este simulador quântico é exposto através da classe `QuantumSimulator`. Para utilizar o simulador, basta criar uma instância desta classe e passá-la para o método `Run` da operação quântica que pretende executar juntamente com o resto dos parâmetros:

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a>Descartável

A classe `QuantumSimulator` implementa <xref:System.IDisposable>, pelo que o método `Dispose` deve ser chamado assim que a instância do simulador já não for utilizada. A melhor maneira de o fazer é embrulhar o simulador numa declaração `using`, como no exemplo acima.

## <a name="seed"></a>semente

O `QuantumSimulator` usa um gerador de números aleatórios para simular a aleatoriedade quântica. Para efeitos de teste, às vezes é útil ter resultados determinísticos. Isto pode ser conseguido fornecendo uma semente para o gerador de números aleatórios no construtor do `QuantumSimulator`através do parâmetro `randomNumberGeneratorSeed`:

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a>Fios

O `QuantumSimulator` utiliza o [OpenMP](http://www.openmp.org/) para paralelor a álgebra linear necessária. Por predefinição, o OpenMP utiliza todos os threads de hardware disponíveis, o que significa que os programas com pequenos números de qubits serão normalmente executados lentamente, pois a coordenação necessária diminuirá o trabalho real. Isto pode ser corrigido definindo a variável ambiental `OMP_NUM_THREADS` para um número pequeno. Como regra geral muito superficial, um thread é bom para um máximo de quatro qubits e, em seguida, um thread adicional por qubit é bom, embora isto seja altamente dependente do algoritmo.

