---
uid: Microsoft.Quantum.Arrays.Tail
title: Função da cauda
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 7084cd8bc75f295024dce361153b58490074cdc5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220098"
---
# <a name="tail-function"></a>Função da cauda

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve o último elemento da matriz.

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a>Entrada

### <a name="array--a"></a>matriz : 'A].

Matriz do qual o último elemento é tomado. A matriz deve ter comprimento mínimo de 1.



## <a name="output--a"></a>Saída : 'A

O último elemento da matriz.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="a"></a>'A

O tipo de elementos de matriz.