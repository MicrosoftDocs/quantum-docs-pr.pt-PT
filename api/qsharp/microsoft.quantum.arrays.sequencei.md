---
uid: Microsoft.Quantum.Arrays.SequenceI
title: Função Sequênciai
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 3cf09e48cce1aeb1aac837465ee3a5e06adf5169
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850996"
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

## <a name="example"></a>Exemplo

```qsharp
let arr1 = SequenceI(0, 3); // [0, 1, 2, 3]
let arr2 = SequenceI(23, 29); // [23, 24, 25, 26, 27, 28, 29]
let arr3 = SequenceI(-5, -2); // [-5, -4, -3, -2]

let numbers = SequenceI(0, _); // function to create sequence from 0 to `to`
let naturals = SequenceI(1, _); // function to create sequence from 1 to `to`
```