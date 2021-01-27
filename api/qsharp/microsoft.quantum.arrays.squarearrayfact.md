---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: Função SquareArrayFact
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: a154e5becba4dae762596a3fc1b268855520fa1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850972"
---
# <a name="squarearrayfact-function"></a>Função SquareArrayFact

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa uma condição de que uma matriz bidimensional tem uma forma quadrada

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a>Descrição

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

## <a name="example"></a>Exemplo

```qsharp
SquareArrayFact([[1, 2], [3, 4]], "Array is not a square");       // okay
SquareArrayFact([[1, 2, 3], [4, 5, 6]], "Array is not a square"); // will fail
SquareArrayFact([[1, 2], [3, 4, 5]], "Array is not a square");    // will fail
```

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Arrays.RectangularArrayFact](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)