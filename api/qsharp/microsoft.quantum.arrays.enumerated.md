---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Função enumerada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: adb13d8b25c9e4a6011ade119ffa3cb2783f60e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848134"
---
# <a name="enumerated-function"></a>Função enumerada

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>Exemplo

Os `for` seguintes ciclos são equivalentes:

```qsharp
for (idx in IndexRange(array)) {
    let element = array[idx];
    ...
}
for ((idx, element) in Enumerated(array)) { ... }
```