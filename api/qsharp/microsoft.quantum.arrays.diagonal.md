---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Função diagonal
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 180b7185c94d712fa02100cb97abfbb6c464d12a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719386"
---
# <a name="diagonal-function"></a>Função diagonal

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


Devolve uma matriz de elementos diagonais de uma matriz bidimensional

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>Descrição

Se a matriz bidimensional não tiver uma forma quadrada, a diagonal sobre o mínimo sobre o número de linhas e colunas será devolvida.

## <a name="input"></a>Entrada

### <a name="matrix--t"></a>matriz : 'T[][]

Matriz 2-dimensional em ordem em linha



## <a name="output--t"></a>Saída : 'T].



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de cada elemento de `matrix` .

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Arrays.Transposto](xref:Microsoft.Quantum.Arrays.Transposed)