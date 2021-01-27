---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: Função IntAsBoolArray
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 8b3d230605cc756a5da01e45e47f91c5b8e9f541
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833312"
---
# <a name="intasboolarray-function"></a>Função IntAsBoolArray

Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Produz uma representação binária de um número inteiro não negativo, usando a representação pouco-endiana para a matriz devolvida.

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a>Entrada

### <a name="number--int"></a>número : [Int](xref:microsoft.quantum.lang-ref.int)

Um número inteiro não negativo para ser convertido para uma matriz de valores booleanos.


### <a name="bits--int"></a>bits : [Int](xref:microsoft.quantum.lang-ref.int)

O número de bits na representação binária de `number` .



## <a name="output--bool"></a>Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)[]

Uma série de valores booleano representando `number` .

## <a name="remarks"></a>Observações

A entrada `bits` deve estar entre 0 e 63.
A entrada `number` deve estar entre 0 e 2^{\texttt{bits}} - 1$.