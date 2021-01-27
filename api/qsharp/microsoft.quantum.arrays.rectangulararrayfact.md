---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: Função RectangularArrayFact
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: 8cf6b85da6e8fee7fc255a173753a6468d8134b9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845492"
---
# <a name="rectangulararrayfact-function"></a>Função RectangularArrayFact

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa uma condição de que uma matriz bidimensional tem uma forma retangular

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a>Descrição

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

## <a name="example"></a>Exemplo

```qsharp
RectangularArrayFact([[1, 2], [3, 4]], "Array is not rectangular");       // okay
RectangularArrayFact([[1, 2, 3], [4, 5, 6]], "Array is not rectangular"); // okay
RectangularArrayFact([[1, 2], [3, 4, 5]], "Array is not rectangular");    // will fail
```

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Arrays.SquareArrayFact](xref:Microsoft.Quantum.Arrays.SquareArrayFact)