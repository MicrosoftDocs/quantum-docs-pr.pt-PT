---
uid: Microsoft.Quantum.Arrays.IndexRange
title: Função IndexRange
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 7f9779acd4a781c50388217aa780710bd0b99ff3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719147"
---
# <a name="indexrange-function"></a>Função IndexRange

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


Dada uma matriz, devolve um intervalo sobre os índices dessa matriz, adequado para ser utilizado em loop.

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a>Entrada

### <a name="array--telement"></a>matriz : 'TElement[]

Uma matriz para a qual uma série de índices deve ser devolvida.



## <a name="output--range"></a>Saída : [Gama](xref:microsoft.quantum.lang-ref.range)

Um alcance sobre todos os índices da matriz.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="telement"></a>'TElement

O tipo de elementos da matriz.