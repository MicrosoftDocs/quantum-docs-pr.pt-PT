---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedFermionEvolutionFunction
title: Função JWOptimizedFermionEvolution Function
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedFermionEvolutionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.
ms.openlocfilehash: 40a4bccc6cf74a63c354bfd628baa45768916fe2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229924"
---
# <a name="jwoptimizedfermionevolutionfunction-function"></a>Função JWOptimizedFermionEvolution Function

Espaço de nome: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)

Pacote: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)


Representa um gerador dinâmico como um conjunto de portões simulados e uma expansão na base JWOptimizada.

```qsharp
function JWOptimizedFermionEvolutionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, parityQubit : Qubit) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a>Entrada

### <a name="generatorindex--generatorindex"></a>generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Um índice gerador a ser representado como evolução unitária na base JWOptimizada.


### <a name="parityqubit--qubit"></a>parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit que determina o sinal da evolução do tempo.



## <a name="output--evolutionunitary"></a>Saída : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)

Uma `EvolutionUnitary` evolução temporal representando o termo referenciado em 'generatorIndex.