---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: Função ColumnAt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: ad09ada1a2253a54e70dddd6dba8aa243d2cd5a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719458"
---
# <a name="columnat-function"></a>Função ColumnAt

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


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

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Arrays.Transposto](xref:Microsoft.Quantum.Arrays.Transposed)
- [Microsoft.Quantum.Arrays.Diagonal](xref:Microsoft.Quantum.Arrays.Diagonal)