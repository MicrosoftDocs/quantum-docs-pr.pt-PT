---
uid: Microsoft.Quantum.Arrays.Transposed
title: Função transposta
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 913f1829ef53ec3eb6944be8b8e3eb37b431f27e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850938"
---
# <a name="transposed-function"></a>Função transposta

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve a transposição de uma matriz representada como uma matriz.

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a>Descrição

Insira como uma matriz de $r \vezes c$ com linhas de $r$ e colunas de $c$.  A matriz é baseada em linha, ou seja, `matrix[i][j]` acede ao elemento na linha $i$ e coluna $j$.

Esta função devolve a matriz de $c \vezes r$ que é a transposição da matriz de entrada.

## <a name="input"></a>Entrada

### <a name="matrix--t"></a>matriz : 'T[][]

$r baseada em linha \vezes c$ matriz



## <a name="output--t"></a>Saída : 'T[][]

Transposto $c \times r$ matriz

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de cada elemento de `matrix` .

## <a name="example"></a>Exemplo

```qsharp
// same as [[1, 4], [2, 5], [3, 6]]
let transposed = Transposed([[1, 2, 3], [4, 5, 6]]);
```