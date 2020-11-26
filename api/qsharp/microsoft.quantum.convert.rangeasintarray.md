---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: Função RangeAsIntArray
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: f756e42aef7dc600e1fc6943a02513ac791f2320
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214012"
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