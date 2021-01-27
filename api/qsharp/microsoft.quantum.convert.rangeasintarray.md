---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: Função RangeAsIntArray
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: 8c6b83d78e3b22ea1a17a48de66592950bf905a3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850108"
---
# <a name="rangeasintarray-function"></a>Função RangeAsIntArray

Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Cria uma série `arr` de inteiros enumerados pelo início. passo. fim.

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a>Entrada

### <a name="range--range"></a>gama : [Gama](xref:microsoft.quantum.lang-ref.range)

A `Range` de valores `start..step..end` a converter para uma matriz.



## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)[]

Uma nova gama de inteiros que corresponde aos valores iterados por `range` .

## <a name="example"></a>Exemplo

```qsharp
// The following returns [1,3,5,7];
let array = RangeAsIntArray(1..2..8);
```