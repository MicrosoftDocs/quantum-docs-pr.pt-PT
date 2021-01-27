---
uid: Microsoft.Quantum.Arrays.EqualA
title: Função EqualA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: fe22e208f67d2c289b0b2d99f19ff26fc5abc3d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848696"
---
# <a name="equala-function"></a>Função EqualA

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>Exemplo

O código que se segue verifica se os diferentes pares de matrizes são iguais:

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function EqualADemo() : Unit {
    let equalArrays = EqualA(EqualI, [2, 3, 4], [2, 3, 4]);
    let differentLength = EqualA(EqualD, [2.0, 3.0, 4.0], [2.0, 3.0]);
    let differentElements = EqualA(EqualR, [One, Zero], [One, One]);
    Message($"Equal arrays are {equalArrays ? "equal" | "not equal"}");
    Message($"Arrays of different length are {differentLength ? "equal" | "not equal"}");
    Message($"Arrays of the same length with different elements are {differentElements ? "equal" | "not equal"}");
}
```

## <a name="remarks"></a>Observações

Esta função é definida para tipos genéricos; ou seja, sempre que temos duas matrizes `'T[]` e uma `equal: ('T, 'T) -> Bool` função, esta função devolve um valor `Bool` que indica se as matrizes são iguais.
Para que duas matrizes sejam consideradas iguais, têm de ter o mesmo comprimento e os elementos nas mesmas posições nas matrizes têm de ser iguais.