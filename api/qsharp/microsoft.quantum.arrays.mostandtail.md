---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: Função MostAndTail
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 8786250cf2f78ce2e9ff8baddc856d0bc07cb9a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718991"
---
# <a name="mostandtail-function"></a>Função MostAndTail

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


Devolve uma tuple de todos, menos um e o último elemento da matriz.

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a>Entrada

### <a name="array--a"></a>matriz : 'A].

Uma matriz com pelo menos um elemento.



## <a name="output--aa"></a>Saída : ('A],'A)

Uma tuple de todos, menos um e o último elemento da matriz.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="a"></a>'A

O tipo de elementos de matriz.