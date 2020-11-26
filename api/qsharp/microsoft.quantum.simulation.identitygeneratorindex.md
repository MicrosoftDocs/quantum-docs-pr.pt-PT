---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: Função IdentidadeGeneratorIndex
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: 2dd3c705b0496df1719dc677e4defea5e435b839
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229295"
---
# <a name="identitygeneratorindex-function"></a>Função IdentidadeGeneratorIndex

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve um índice gerador consistente com o Hamiltonian zero, `H = 0` que corresponde à operação de evolução da identidade.

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Entrada

### <a name="idxterm--int"></a>idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)

Esta entrada é ignorada e definida para a consistência com o tipo definido pelo <xref:microsoft.quantum.simulation.generatorsystem> utilizador.



## <a name="output--generatorindex"></a>Saída : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Um índice gerador que representa a evolução sob o $H Hamiltonian = 0$.