---
uid: Microsoft.Quantum.Arrays.Head
title: Função da cabeça
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 834cbe2384122463be6a0efcb6e09785aae9c092
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221118"
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