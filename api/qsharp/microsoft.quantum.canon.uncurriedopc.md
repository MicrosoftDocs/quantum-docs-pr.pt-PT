---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: Função DeOpC nãocurried
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: f3e5ecf3f7df0393dfbb948f064c27505f04cfcf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715214"
---
# <a name="uncurriedopc-function"></a>Função DeOpC nãocurried

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Dada a função que devolve as operações, devolve uma nova operação que toma ambas as entradas como tuple.
O modificador `C` indica que as operações são controláveis.

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a>Entrada

### <a name="curriedop--t---u--unit-ctl"></a>curriedOp : 'T-> 'U = [unidade](xref:microsoft.quantum.lang-ref.unit)> Ctl

Uma função que devolve as operações.



## <a name="output--tu--unit-ctl"></a>Saída : ('T,'U) => [Unidade](xref:microsoft.quantum.lang-ref.unit) CTL

Uma nova operação `op` tal que `op(t, u)` equivale `(curriedOp(t))(u)` a.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo do primeiro argumento de uma função curada.
### <a name="u"></a>'U

O tipo do segundo argumento de uma função curada.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)