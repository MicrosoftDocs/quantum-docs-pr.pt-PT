---
uid: Microsoft.Quantum.Chemistry.JordanWigner._JordanWignerClusterOperatorFunction
title: função _JordanWignerClusterOperatorFunction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _JordanWignerClusterOperatorFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.
ms.openlocfilehash: 58b0c7ad2216b1f58b9ea2765494b85fab4e1ff9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714657"
---
# <a name="_jordanwignerclusteroperatorfunction-function"></a>função _JordanWignerClusterOperatorFunction

Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Pacote: [](https://nuget.org/packages/)


Representa um gerador dinâmico como um conjunto de portões simulados e uma expansão na base JordanWigner.

```qsharp
function _JordanWignerClusterOperatorFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a>Entrada

### <a name="generatorindex--generatorindex"></a>generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Um índice gerador a ser representado como evolução unitária no JordanWigner.



## <a name="output--evolutionunitary"></a>Saída : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)

Uma `EvolutionUnitary` evolução temporal representando o termo referenciado em 'generatorIndex.