---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: Função Não curadaopCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 910d8a3006a2f217888b791e479e10f9f1a6965e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840047"
---
# <a name="uncurriedopca-function"></a>Função Não curadaopCA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada a função que devolve as operações, devolve uma nova operação que toma ambas as entradas como tuple.
O modificador `CA` indica que as operações são controláveis e adjacentes.

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a>Entrada

### <a name="curriedop--t---u--unit--is-adj--ctl"></a>curriedOp : 'T-> 'U = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl

Uma função que devolve as operações.



## <a name="output--tu--unit--is-adj--ctl"></a>Saída : ('T,'U) = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl

Uma nova operação `op` tal que `op(t, u)` equivale `(curriedOp(t))(u)` a.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo do primeiro argumento de uma função curada.
### <a name="u"></a>'U

O tipo do segundo argumento de uma função curada.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)