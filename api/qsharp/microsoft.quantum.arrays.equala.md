---
uid: Microsoft.Quantum.Arrays.EqualA
title: Função EqualA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: 24fd76aaeb66081d6d8f1eaa3056117f54b5a5e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719290"
---
# <a name="equala-function"></a>Função EqualA

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


Tendo em conta duas matrizes do mesmo tipo e um predicado que é definido para pares de elementos das matrizes, verifica se as matrizes são iguais.

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a>Entrada

### <a name="equal--tt---bool"></a>igual: ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)

Uma função de tuple `('T, 'T)` para que é usada para verificar se dois `Bool` elementos de matrizes são iguais.


### <a name="array1--t"></a>array1 : 'T[]

A primeira matriz a ser comparada.


### <a name="array2--t"></a>array2 : 'T[]

A segunda matriz a ser comparada.



## <a name="output--bool"></a>Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)

O valor `true` se e só se e é `array1` `array2` igual.
Isto é, se ambas as matrizes tiverem o mesmo comprimento, e todos os elementos forem iguais como definido por `equal` .

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de elementos de cada matriz.

## <a name="remarks"></a>Observações

Esta função é definida para tipos genéricos; ou seja, sempre que temos duas matrizes `'T[]` e uma `equal: ('T, 'T) -> Bool` função, esta função devolve um valor `Bool` que indica se as matrizes são iguais.
Para que duas matrizes sejam consideradas iguais, têm de ter o mesmo comprimento e os elementos nas mesmas posições nas matrizes têm de ser iguais.