---
uid: Microsoft.Quantum.Arrays.Windows
title: Função do Windows
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 6071d1c3e5981855c57abd0e741b1de0201c30a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718750"
---
# <a name="windows-function"></a>Função do Windows

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


Devolve todos os subarrays consecutivos de comprimento `size` .

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a>Descrição

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