---
uid: Microsoft.Quantum.Arrays.All
title: Todas as funções
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: 345c3fb92babd4ae2e54803b6c3b79b3313ef417
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719482"
---
# <a name="all-function"></a>Todas as funções

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


Dada uma matriz e um predicado que é definido para os elementos da matriz, e verifica se todos os elementos da matriz satisfazem o predicado.

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>Entrada

### <a name="predicate--t---bool"></a>predicado: 'T-> [Bool](xref:microsoft.quantum.lang-ref.bool)

Uma função a partir `'T` do que é usada para verificar `Bool` elementos.


### <a name="array--t"></a>matriz : 'T[]

Uma série de elementos sobre `'T` .



## <a name="output--bool"></a>Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)

Um `Bool` valor da função E do predicado aplicado a todos os elementos.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de `array` elementos.

## <a name="remarks"></a>Observações

A função é definida para tipos genéricos, ou seja, sempre que temos uma matriz `'T[]` e uma função `predicate: 'T -> Bool` podemos produzir um valor que indique `Bool` se todos os elementos satisfazem `predicate` .