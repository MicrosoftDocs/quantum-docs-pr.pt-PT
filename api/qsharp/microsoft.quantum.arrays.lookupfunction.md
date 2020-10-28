---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: Função de procuraçãoFunction
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: c929054b96ee499db896cacf0e3ae4da6f6c4b98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719074"
---
# <a name="lookupfunction-function"></a>Função de procuraçãoFunction

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [](https://nuget.org/packages/)


Dada uma matriz, devolve uma função que devolve elementos dessa matriz.

```qsharp
function LookupFunction<'T> (array : 'T[]) : (Int -> 'T)
```


## <a name="input"></a>Entrada

### <a name="array--t"></a>matriz : 'T[]

A matriz a ser representada como uma função de procuração.



## <a name="output--int---t"></a>Saída : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T

Uma função `f` de tal forma `f(idx) == f[idx]` que.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de elementos da matriz sendo representados como uma função de procuração.

## <a name="remarks"></a>Observações

Esta função é principalmente útil para a interoperação com funções e operações que assumem `Int -> 'T` funções como seus argumentos. Isto é comum, por exemplo, na biblioteca de representação do gerador, onde as funções são usadas para evitar a necessidade de registar um conjunto inteiro na memória.