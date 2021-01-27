---
uid: Microsoft.Quantum.Arrays.EmptyArray
title: Função EmptyArray
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EmptyArray
qsharp.summary: Returns the empty array of a given type.
ms.openlocfilehash: cf15e61862bb64fb3408db2318fafb56d532b365
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846181"
---
# <a name="emptyarray-function"></a>Função EmptyArray

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Devolve a matriz vazia de um determinado tipo.

```qsharp
function EmptyArray<'TElement> () : 'TElement[]
```


## <a name="output--telement"></a>Saída : 'TElement[]

A matriz vazia.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="telement"></a>'TElement

O tipo de elementos da matriz.

## <a name="example"></a>Exemplo

```qsharp
let empty = EmptyArray<Int>();
```