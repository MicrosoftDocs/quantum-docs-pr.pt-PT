---
uid: Microsoft.Quantum.Arrays.SequenceI
title: Função Sequênciai
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5dc4377c696e14b505c63701c2f5ca0dadca672
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718895"
---
# <a name="sequencei-function"></a>Função Sequênciai

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


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