---
uid: Microsoft.Quantum.Arrays.Head
title: Função da cabeça
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 6dd181914b5ed3ef16a02b31cb6131daf2a34e19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848578"
---
# <a name="head-function"></a>Função da cabeça

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve o primeiro elemento da matriz.

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a>Entrada

### <a name="array--a"></a>matriz : 'A].

Matriz do qual o primeiro elemento é tomado. A matriz deve ter comprimento mínimo de 1.



## <a name="output--a"></a>Saída : 'A

O primeiro elemento da matriz.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="a"></a>'A

O tipo de elementos de matriz.