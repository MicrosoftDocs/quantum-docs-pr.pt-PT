---
uid: Microsoft.Quantum.Arrays.IndexRange
title: Função IndexRange
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 043b56a1ac3cbe5cd59cdd45d3725f301d81a6ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845786"
---
# <a name="indexrange-function"></a>Função IndexRange

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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

## <a name="example"></a>Exemplo

Os `for` seguintes ciclos são equivalentes:

```qsharp
for (idx in IndexRange(array)) { ... }
for (idx in IndexRange(array)) { ... }
```