---
uid: Microsoft.Quantum.Canon.BoundC
title: Função BoundC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 6b640c0dab14778336f42098e699e7e68cc726df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841034"
---
# <a name="boundc-function"></a>Função BoundC

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dado um conjunto de operações agindo numa única entrada, produz uma nova operação que executa cada operação em sequência.
O modificador `C` indica que todas as operações na matriz são controláveis.

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a>Entrada

### <a name="operations--t--unit--is-ctl"></a>operações : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é CTL[]

Uma sequência de operações a realizar numa dada entrada.



## <a name="output--t--unit--is-ctl"></a>Saída : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é CTL

Uma nova operação que executa cada operação em sequência na sua entrada.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O alvo em que cada uma das operações na matriz atuam.

## <a name="example"></a>Exemplo

Os seguintes são equivalentes:

```qsharp
let bound = BoundC([U, V]);
bound(x);
```

e

```qsharp
U(x); V(x);
```

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.Bound](xref:Microsoft.Quantum.Canon.Bound)