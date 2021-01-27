---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: Função UncurriedOp
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: d707b52bb17f4dea795fa4ff824c785e506b8b20
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851999"
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