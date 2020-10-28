---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Função SequenceL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5ce63575e703341fce42c0be393765c342bbd89
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718882"
---
# <a name="sequencel-function"></a>Função SequenceL

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


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