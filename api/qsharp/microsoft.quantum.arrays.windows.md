---
uid: Microsoft.Quantum.Arrays.Windows
title: Função do Windows
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 8f32a23aa4379744b84c3b8d9c8f565e61c3c64e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219894"
---
# <a name="windows-function"></a>Função do Windows

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve todos os subarrays consecutivos de comprimento `size` .

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a>Description

Esta função devolve todos os `n - size + 1` subarrays de comprimento `size` em ordem, onde `n` é o comprimento de `arr` .
Os primeiros subarrays são `arr[0..size - 1], arr[1..size], arr[2..size + 1]` até à última subarray. `arr[n - size..n - 1]`

Se `size <= 0` `size > n` ou, uma matriz vazia é devolvida.

## <a name="input"></a>Entrada

### <a name="size--int"></a>tamanho : [Int](xref:microsoft.quantum.lang-ref.int)

Comprimento dos subarrays.


### <a name="array--t"></a>matriz : 'T[]

Uma variedade de elementos.



## <a name="output--t"></a>Saída : 'T[][]



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de `array` elementos.