---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: Função IntAsBoolArray
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 9783a49a77bdc39ffe8c7725196eb620f4cd0100
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713453"
---
# <a name="intasboolarray-function"></a>Função IntAsBoolArray

Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)

Pacote: [](https://nuget.org/packages/)


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