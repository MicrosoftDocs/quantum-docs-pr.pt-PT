---
uid: Microsoft.Quantum.Arrays.Swapped
title: Função trocada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: 575d6b76e52f198d91ab5557ada8032df491cfa3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850959"
---
# <a name="swapped-function"></a>Função trocada

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma troca de dois elementos numa matriz.

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a>Entrada

### <a name="firstindex--int"></a>firstIndex : [Int](xref:microsoft.quantum.lang-ref.int)

Índice do primeiro elemento a ser trocado.


### <a name="secondindex--int"></a>secondIndex : [Int](xref:microsoft.quantum.lang-ref.int)

Índice do segundo elemento a ser trocado.


### <a name="arr--t"></a>arr : 'T]]

Matriz com elementos a serem trocados.



## <a name="output--t"></a>Saída : 'T].

A matriz com a troca de lugar aplicada.

## <a name="example"></a>Exemplo

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

