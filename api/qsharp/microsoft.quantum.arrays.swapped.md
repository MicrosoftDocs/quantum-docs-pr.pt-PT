---
uid: Microsoft.Quantum.Arrays.Swapped
title: Função trocada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: 173fb32b5a41ce054f19548a7fcca18c11c4c4cd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220132"
---
# <a name="swapped-function"></a>Função trocada

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma troca de dois elementos numa matriz.

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a>Entrada

### <a name="firstindex--int"></a>firstIndex : [Int](xref:microsoft.quantum.lang-ref.int)

Índice do primeiro elemento a ser trocado.


### <a name="secondindex--int"></a>secondIndex : [Int](xref:microsoft.quantum.lang-ref.int)

Índice do segundo elemento a ser trocado.


### <a name="arr--t"></a>arr : 'T]]

Matriz com elementos a serem trocados.



## <a name="output--t"></a>Saída : 'T].

A matriz com a troca de lugar aplicada.

## <a name="example"></a>Exemplo

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

