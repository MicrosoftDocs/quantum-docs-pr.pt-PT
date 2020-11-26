---
uid: Microsoft.Quantum.Arrays.Transposed
title: Função transposta
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: f293399d8e3a2cb32b2929e8d1591ac5eaefd277
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219996"
---
# <a name="transposed-function"></a>Função transposta

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve a transposição de uma matriz representada como uma matriz.

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a>Description

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