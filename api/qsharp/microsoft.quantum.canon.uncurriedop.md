---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: Função UncurriedOp
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: cad508f166d4af805cb98cd21a0260d9babb6a4c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204645"
---
# <a name="uncurriedop-function"></a>Função UncurriedOp

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada a função que devolve as operações, devolve uma nova operação que toma ambas as entradas como tuple.

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a>Entrada

### <a name="curriedop--t---u--unit"></a>curriedOp : 'T-> 'U = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

Uma função que devolve as operações.



## <a name="output--tu--unit"></a>Saída : ('T,'U) = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

Uma nova operação `op` tal que `op(t, u)` equivale `(curriedOp(t))(u)` a.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de primeira entrada para uma operação com cura.
### <a name="u"></a>'U

O tipo da segunda entrada para uma operação com cura.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.UncurriedOpC](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [Microsoft.Quantum.Canon.UncurriedOpA](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [Microsoft.Quantum.Canon.UncurriedOpCA](xref:Microsoft.Quantum.Canon.UncurriedOpCA)