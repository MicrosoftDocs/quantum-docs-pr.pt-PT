---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerFermionEvolutionSet
title: Função JordanWignerFermionEvolutionSet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerFermionEvolutionSet
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.
ms.openlocfilehash: a43f9c27eb1e60fb072d5962c37816577a7b2879
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714038"
---
# <a name="jordanwignerfermionevolutionset-function"></a>Função JordanWignerFermionEvolutionSet

Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Pacote: [](https://nuget.org/packages/)


Representa um gerador dinâmico como um conjunto de portões simulados e uma expansão na base JordanWigner.

```qsharp
function JordanWignerFermionEvolutionSet () : Microsoft.Quantum.Simulation.EvolutionSet
```


## <a name="output--evolutionset"></a>Saída : [EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)

Um `EvolutionSet` que mapeia uma `GeneratorIndex` base JordanWigner para um "EvolutionUnitary".