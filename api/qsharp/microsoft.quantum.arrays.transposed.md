---
uid: Microsoft.Quantum.Arrays.Transposed
title: Função transposta
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 54071c461cf9f9411c332763b81e3bc448fb6c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718811"
---
# <a name="transposed-function"></a>Função transposta

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


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