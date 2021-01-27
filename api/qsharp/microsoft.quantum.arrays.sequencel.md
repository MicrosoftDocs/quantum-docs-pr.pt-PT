---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Função SequenceL
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 7e3c5c31428f9be152e28afbe478a3d15eb0a56c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850988"
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

## <a name="example"></a>Exemplo

```qsharp
let arr1 = SequenceL(0L, 3L); // [0L, 1L, 2L, 3L]
let arr2 = SequenceL(23L, 29L); // [23L, 24L, 25L, 26L, 27L, 28L, 29L]
let arr3 = SequenceL(-5L, -2L); // [-5L, -4L, -3L, -2L]
```

## <a name="remarks"></a>Observações

A diferença entre `from` e deve caber num `to` `Int` valor.