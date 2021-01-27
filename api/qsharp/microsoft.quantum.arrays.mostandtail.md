---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: Função MostAndTail
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: fd5569f1b71ac2fdf2b5c08ba7dde172e3a6744e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845595"
---
# <a name="mostandtail-function"></a>Função MostAndTail

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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