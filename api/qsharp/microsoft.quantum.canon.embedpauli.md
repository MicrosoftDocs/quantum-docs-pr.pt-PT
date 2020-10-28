---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: Função EmbedPauli
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: c78406aa4557834ac2bb40cf1847696d075e5135
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716197"
---
# <a name="embedpauli-function"></a>Função EmbedPauli

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Dado um operador pauli de um único qubit e o índice de um qubit, devolve um operador Pauli multi-qubit com o operador de um único qubit dado nesse índice e `PauliI` em todos os outros índices.

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a>Entrada

### <a name="pauli--pauli"></a>pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Um operador pauli de um único qubit a ser colocado no local dado.


### <a name="location--int"></a>localização : [Int](xref:microsoft.quantum.lang-ref.int)

Um índice tal `output[location] == pauli` que, onde `output` está a saída desta função.


### <a name="n--int"></a>n : [Int](xref:microsoft.quantum.lang-ref.int)

Comprimento da matriz a ser devolvido.



## <a name="output--pauli"></a>Saída : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

