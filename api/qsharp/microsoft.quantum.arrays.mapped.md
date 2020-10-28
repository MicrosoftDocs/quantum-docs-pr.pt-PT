---
uid: Microsoft.Quantum.Arrays.Mapped
title: Função mapeada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 1abb9d6fb1a921b49554bef968442f4f2b346b71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719075"
---
# <a name="mapped-function"></a>Função mapeada

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


Dada uma matriz e uma função que é definida para os elementos da matriz, devolve uma nova matriz que consiste nas imagens da matriz original sob a função.

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>Entrada

### <a name="mapper--t---u"></a>mapper : 'T-> 'U

Uma função disso `'T` `'U` é usada para mapear elementos.


### <a name="array--t"></a>matriz : 'T[]

Uma série de elementos sobre `'T` .



## <a name="output--u"></a>Saída : 'U].

Uma matriz `'U[]` de elementos que são mapeados pela `mapper` função.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de `array` elementos.
### <a name="u"></a>'U

O tipo de resultado da `mapper` função.

## <a name="remarks"></a>Observações

A função é definida para tipos genéricos, ou seja, sempre que temos uma matriz `'T[]` e uma função `mapper: 'T -> 'U` podemos mapear os elementos da matriz e produzir uma nova matriz de tipo `'U[]` .