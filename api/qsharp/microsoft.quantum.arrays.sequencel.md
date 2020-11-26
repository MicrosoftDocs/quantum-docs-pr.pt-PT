---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Função SequenceL
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 3e5c7f64825f09d82792d3e46fe3f53f5814510b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220268"
---
# <a name="sequencel-function"></a>Função SequenceL

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Obtenha uma série de inteiros num dado intervalo.

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a>Entrada

### <a name="from--bigint"></a>de : [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Um índice de início inclusivo do intervalo.


### <a name="to--bigint"></a>a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Um índice final inclusivo do intervalo que não é menor que `from` .



## <a name="output--bigint"></a>Saída : [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]

Uma matriz contendo a sequência de `from` `from + 1` números, ... ..., `to` .

## <a name="remarks"></a>Observações

A diferença entre `from` e deve caber num `to` `Int` valor.