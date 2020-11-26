---
uid: Microsoft.Quantum.Canon.BoundC
title: Função BoundC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 02e9b6a9676cdd1996d3a2413b2a6383e3a4e90e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207586"
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

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.Bound](xref:Microsoft.Quantum.Canon.Bound)