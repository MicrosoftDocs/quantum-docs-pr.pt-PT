---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: Função ColumnAt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 32dc814de9b04563c2798a768f121723a1a8252c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846263"
---
# <a name="columnat-function"></a>Função ColumnAt

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Extrai uma coluna de uma matriz.

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>Descrição

Esta função extrai uma coluna numa matriz em ordem de linha.
Extrair uma linha de corrsponds para o acesso do elemento do primeiro índice e, portanto, não requer mais tratamento.

## <a name="input"></a>Entrada

### <a name="column--int"></a>coluna : [Int](xref:microsoft.quantum.lang-ref.int)

Coluna da matriz


### <a name="matrix--t"></a>matriz : 'T[][]

Matriz 2-dimensional em ordem em linha



## <a name="output--t"></a>Saída : 'T].



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de cada elemento de `matrix` .

## <a name="example"></a>Exemplo

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let column = ColumnAt(0, matrix);
// same as: column = [1, 4, 7]
```

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Arrays.Transposto](xref:Microsoft.Quantum.Arrays.Transposed)
- [Microsoft.Quantum.Arrays.Diagonal](xref:Microsoft.Quantum.Arrays.Diagonal)