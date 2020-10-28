---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: Função IdentidadeGeneratorIndex
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: d2af2dafaf75a68546cb3f16c04cf4c7ee50c6ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724542"
---
# <a name="identitygeneratorindex-function"></a>Função IdentidadeGeneratorIndex

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [](https://nuget.org/packages/)


Devolve um índice gerador consistente com o Hamiltonian zero, `H = 0` que corresponde à operação de evolução da identidade.

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Entrada

### <a name="idxterm--int"></a>idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)

Esta entrada é ignorada e definida para a consistência com o tipo definido pelo <xref:microsoft.quantum.simulation.generatorsystem> utilizador.



## <a name="output--generatorindex"></a>Saída : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Um índice gerador que representa a evolução sob o $H Hamiltonian = 0$.