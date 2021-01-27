---
uid: Microsoft.Quantum.Arrays.Tail
title: Função da cauda
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 680562228a39263ef87ba053e6b7683412947e46
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845414"
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