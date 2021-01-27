---
uid: Microsoft.Quantum.Canon.BoundA
title: Função BoundA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 3d0a5ba5d3d9c76289ed29e59a9c226358b83797
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844550"
---
# <a name="bounda-function"></a>Função BoundA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dado um conjunto de operações agindo numa única entrada, produz uma nova operação que executa cada operação em sequência.
O modificador `A` indica que todas as operações na matriz são adjacentes.

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a>Entrada

### <a name="operations--t--unit--is-adj"></a>operações : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj[]

Uma sequência de operações a realizar numa dada entrada.



## <a name="output--t--unit--is-adj"></a>Saída : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj

Uma nova operação que executa cada operação em sequência na sua entrada.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O alvo em que cada uma das operações na matriz atuam.

## <a name="example"></a>Exemplo

Os seguintes são equivalentes:

```qsharp
let bound = BoundA([U, V]);
bound(x);
```

e

```qsharp
U(x); V(x);
```

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.Bound](xref:Microsoft.Quantum.Canon.Bound)