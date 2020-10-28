---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: Função Não curadaopCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 6a0f2e1b345d0ba3ac5c779c5dc2bfffaf659a0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715203"
---
# <a name="uncurriedopca-function"></a>Função Não curadaopCA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Dada a função que devolve as operações, devolve uma nova operação que toma ambas as entradas como tuple.
O modificador `CA` indica que as operações são controláveis e adjacentes.

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a>Entrada

### <a name="curriedop--t---u--unit-ctl--adj"></a>curriedOp : 'T-> 'U = [unidade](xref:microsoft.quantum.lang-ref.unit)> Ctl + Adj

Uma função que devolve as operações.



## <a name="output--tu--unit-ctl--adj"></a>Saída : ('T,'U) => [Unidade](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj

Uma nova operação `op` tal que `op(t, u)` equivale `(curriedOp(t))(u)` a.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo do primeiro argumento de uma função curada.
### <a name="u"></a>'U

O tipo do segundo argumento de uma função curada.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)