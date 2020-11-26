---
uid: Microsoft.Quantum.Simulation.PauliEvolutionFunction
title: Função PauliEvolutionFunction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.
ms.openlocfilehash: e581cd4d0a3caf96bece9979a1d850aad7842727
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230366"
---
# <a name="paulievolutionfunction-function"></a>Função PauliEvolutionFunction

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa um gerador dinâmico como um conjunto de portões simulados e uma expansão na base Pauli.

```qsharp
function PauliEvolutionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a>Entrada

### <a name="generatorindex--generatorindex"></a>generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Um índice gerador a ser representado como evolução unitária na base Pauli.



## <a name="output--evolutionunitary"></a>Saída : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)

Uma `EvolutionUnitary` evolução temporal representando o termo referenciado em 'generatorIndex.