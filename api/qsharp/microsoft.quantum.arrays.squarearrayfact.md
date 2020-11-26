---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: Função SquareArrayFact
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: 3529718f0c903266d21fd593c11c0149dae0fa2c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220200"
---
# <a name="squarearrayfact-function"></a>Função SquareArrayFact

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa uma condição de que uma matriz bidimensional tem uma forma quadrada

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a>Description

Esta função afirma que cada linha de uma matriz tem tantos elementos como existem linhas (elementos) na matriz.

## <a name="input"></a>Entrada

### <a name="array--t"></a>matriz : 'T[][]

Uma matriz bidimensional de elementos


### <a name="message--string"></a>mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)

Uma mensagem a ser impressa se a matriz não é uma matriz quadrada



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de cada elemento de `array` .

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Arrays.RectangularArrayFact](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)