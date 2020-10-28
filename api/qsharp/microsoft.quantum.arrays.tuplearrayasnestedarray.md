---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: TupleArrayAsNestedArray
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: 917f35db949790ab3ae6e7a2184bcfcf5ed50be6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718810"
---
# <a name="tuplearrayasnestedarray-function"></a>TupleArrayAsNestedArray

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


Transforma uma lista de 2 tuples numa matriz aninhada.

```qsharp
function TupleArrayAsNestedArray<'T> (tupleList : ('T, 'T)[]) : 'T[][]
```


## <a name="input"></a>Entrada

### <a name="tuplelist--tt"></a>tupleList : ('T,'T)[]

Lista de 2 tuples para ser transformado em uma matriz aninhada.



## <a name="output--t"></a>Saída : 'T[][]

Uma matriz aninhada com comprimento correspondente à tupleList.

## <a name="example"></a>Exemplo

```qsharp
// The following returns [[2, 3], [4, 5]]
TupleArrayAsNestedArray([(2, 3), (4, 5)]);
```

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

