---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: Função Não funcional daOpA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: 21df20354ad2388891f32b1bf1c7781287904983
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715217"
---
# <a name="uncurriedopa-function"></a>Função Não funcional daOpA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Dada a função que devolve as operações, devolve uma nova operação que toma ambas as entradas como tuple.
O modificador `A` indica que as operações são adjacentes.

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a>Entrada

### <a name="curriedop--t---u--unit-adj"></a>curriedOp : 'T-> 'U = [unidade](xref:microsoft.quantum.lang-ref.unit)> Adj

Uma função que devolve as operações.



## <a name="output--tu--unit-adj"></a>Saída : ('T,'U) => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj

Uma nova operação `op` tal que `op(t, u)` equivale `(curriedOp(t))(u)` a.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo do primeiro argumento de uma função curada.
### <a name="u"></a>'U

O tipo do segundo argumento de uma função curada.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)