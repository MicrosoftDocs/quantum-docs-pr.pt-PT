---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: Função RectangularArrayFact
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: b8ef7d52f7f815ca3e21ded1236e775a381646cb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220421"
---
# <a name="rectangulararrayfact-function"></a>Função RectangularArrayFact

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa uma condição de que uma matriz bidimensional tem uma forma retangular

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a>Description

Esta função afirma que cada linha de uma matriz tem o mesmo comprimento.

## <a name="input"></a>Entrada

### <a name="array--t"></a>matriz : 'T[][]

Uma matriz bidimensional de elementos


### <a name="message--string"></a>mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)

Uma mensagem a ser impressa se a matriz não for uma matriz retangular



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de cada elemento de `array` .

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Arrays.SquareArrayFact](xref:Microsoft.Quantum.Arrays.SquareArrayFact)