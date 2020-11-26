---
uid: Microsoft.Quantum.Canon.BoundA
title: Função BoundA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 3132bf198e98dd1a2b433f36b000060e7e721865
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216953"
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

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.Bound](xref:Microsoft.Quantum.Canon.Bound)