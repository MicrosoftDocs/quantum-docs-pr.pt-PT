---
uid: Microsoft.Quantum.Arrays.ForEach
title: ForEach operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: 90dd6f94408d37d2b32d82e772a482b0e69c523f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848591"
---
# <a name="foreach-operation"></a>ForEach operação

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada uma matriz e uma operação que é definida para os elementos da matriz, devolve uma nova matriz que consiste nas imagens da matriz original no âmbito da operação.

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>Entrada

### <a name="action--t--u"></a>ação : 'T => 'U 

Uma operação `'T` `'U` a partir daí é aplicada a cada elemento.


### <a name="array--t"></a>matriz : 'T[]

Uma série de elementos sobre `'T` .



## <a name="output--u"></a>Saída : 'U].

Uma série `'U[]` de elementos que são mapeados pela `action` operação.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de `array` elementos.
### <a name="u"></a>'U

O tipo de resultado da `action` operação.

## <a name="remarks"></a>Observações

A operação é definida para tipos genéricos, ou seja, sempre que temos uma matriz `'T[]` e uma operação `action : 'T -> 'U` podemos mapear os elementos da matriz e produzir uma nova matriz de tipo `'U[]` .