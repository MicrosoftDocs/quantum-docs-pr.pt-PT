---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Função enumerada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 0a591025a4eef79e08b47527c0bdb556f5645334
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719303"
---
# <a name="enumerated-function"></a>Função enumerada

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


Dada uma matriz, devolve uma nova matriz contendo elementos da matriz original juntamente com os índices de cada elemento.

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a>Entrada

### <a name="array--telement"></a>matriz : 'TElement[]

Uma matriz cujos elementos devem ser enumerados.



## <a name="output--inttelement"></a>Saída :[(Int](xref:microsoft.quantum.lang-ref.int)'TElement)[]

Uma nova matriz contendo elementos da matriz original juntamente com os seus índices.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="telement"></a>'TElement

O tipo de elementos da matriz.