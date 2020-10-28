---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: Função RangeAsIntArray
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: bd3ac51d2925d7a4450b2bc5e6f7899fcab18f2c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713366"
---
# <a name="rangeasintarray-function"></a>Função RangeAsIntArray

Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)

Pacote: [](https://nuget.org/packages/)


Cria uma série `arr` de inteiros enumerados pelo início. passo. fim.

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a>Entrada

### <a name="range--range"></a>gama : [Gama](xref:microsoft.quantum.lang-ref.range)

A `Range` de valores `start..step..end` a converter para uma matriz.



## <a name="output--int"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int)[]

Uma nova gama de inteiros que corresponde aos valores iterados por `range` .