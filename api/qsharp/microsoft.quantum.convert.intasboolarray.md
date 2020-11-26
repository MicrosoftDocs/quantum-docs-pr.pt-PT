---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: Função IntAsBoolArray
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: f89cb3d7ca29d7deaaf49573b2670534166caded
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224348"
---
# <a name="intasboolarray-function"></a>Função IntAsBoolArray

Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Produz uma representação binária de um inteiro positivo, usando a representação pouco-endiana para a matriz devolvida.

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a>Entrada

### <a name="number--int"></a>número : [Int](xref:microsoft.quantum.lang-ref.int)

Um número inteiro positivo a ser convertido para uma variedade de valores booleanos.


### <a name="bits--int"></a>bits : [Int](xref:microsoft.quantum.lang-ref.int)

O número de bits na representação binária de `number` .



## <a name="output--bool"></a>Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)[]

Uma série de valores booleano representando `number` .

## <a name="remarks"></a>Observações

A entrada `bits` deve estar entre 0 e 63.
A entrada `number` deve estar entre 0 e 2^{\texttt{bits}} - 1$.