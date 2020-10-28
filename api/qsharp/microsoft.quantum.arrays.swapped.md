---
uid: Microsoft.Quantum.Arrays.Swapped
title: Função trocada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: fa5b37b4caf5d8f19ed05075ddd7bc4217036bfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718823"
---
# <a name="swapped-function"></a>Função trocada

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


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

