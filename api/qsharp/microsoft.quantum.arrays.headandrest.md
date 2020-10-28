---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: Função HeadAndRest
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 9af4ba48a21d3cdf932b2f702051a70a6108db1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719182"
---
# <a name="headandrest-function"></a>Função HeadAndRest

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


Devolve uma tuple de primeiro e todos os elementos restantes da matriz.

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a>Entrada

### <a name="array--a"></a>matriz : 'A].

Uma matriz com pelo menos um elemento.



## <a name="output--aa"></a>Saída : ('A,'A])

Um tuple de primeiro e todos os elementos restantes da matriz.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="a"></a>'A

O tipo de elementos de matriz.