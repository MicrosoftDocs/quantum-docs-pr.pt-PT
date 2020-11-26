---
uid: Microsoft.Quantum.Arrays.SequenceI
title: Função Sequênciai
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 5f03e5f2baff8077c1fa3fb5f1f079528ef0e215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220302"
---
# <a name="sequencei-function"></a>Função Sequênciai

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Obtenha uma série de inteiros num dado intervalo.

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a>Entrada

### <a name="from--int"></a>de : [Int](xref:microsoft.quantum.lang-ref.int)

Um índice de início inclusivo do intervalo.


### <a name="to--int"></a>a : [Int](xref:microsoft.quantum.lang-ref.int)

Um índice final inclusivo do intervalo que não é menor que `from` .



## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)[]

Uma matriz contendo a sequência de `from` `from + 1` números, ... ..., `to` .