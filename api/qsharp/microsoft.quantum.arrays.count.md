---
uid: Microsoft.Quantum.Arrays.Count
title: Função contagem
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 408a4a42dda6a4827db6d5865e2b4b8a8df5b37a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719399"
---
# <a name="count-function"></a>Função contagem

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


Dada uma matriz e um predicado que é definido para os elementos da matriz, devolve o número de elementos uma matriz que consiste nos elementos que satisfazem o predicado.

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a>Entrada

### <a name="predicate--t---bool"></a>predicado: 'T-> [Bool](xref:microsoft.quantum.lang-ref.bool)

Uma função de `'T` Boolean que é usada para filtrar elementos.


### <a name="array--t"></a>matriz : 'T[]

Uma série de elementos sobre `'T` .



## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)

O número de elementos `array` que satisfazem o predicado.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de `array` elementos.

## <a name="remarks"></a>Observações

A função é definida para tipos genéricos, ou seja, sempre que temos uma matriz `'T[]` e um predicado `'T -> Bool` podemos filtrar elementos.