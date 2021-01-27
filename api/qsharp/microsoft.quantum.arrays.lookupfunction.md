---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: Função de procuraçãoFunction
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: 22b56bb7e9f03ebc5b2225efb2e6450d56022664
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845706"
---
# <a name="lookupfunction-function"></a>Função de procuraçãoFunction

Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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