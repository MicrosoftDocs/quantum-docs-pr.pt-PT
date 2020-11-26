---
uid: Microsoft.Quantum.Canon.OperationPow
title: Função OperationPow
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 808001200d276ca21cc5a70140d5d84d96da3496
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205818"
---
# <a name="operationpow-function"></a>Função OperationPow

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Eleva uma operação a uma potência.

Ou seja, dada uma operação que representa um portão $U$, devolve uma nova operação $U^m$ por uma potência $m$.

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a>Entrada

### <a name="op--t--unit"></a>op : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

Uma operação $U$ representando o portão a ser repetido.


### <a name="power--int"></a>poder : [Int](xref:microsoft.quantum.lang-ref.int)

O número de vezes que $U$ deve ser repetido.



## <a name="output--t--unit"></a>Saída : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

Uma nova operação que representa $U^m$, onde $m = \texttt{power}$.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de operação a ser alimentada.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.OperationPowC](xref:Microsoft.Quantum.Canon.OperationPowC)
- [Microsoft.Quantum.Canon.OperationPowa](xref:Microsoft.Quantum.Canon.OperationPowA)
- [Microsoft.Quantum.Canon.OperationPowCA](xref:Microsoft.Quantum.Canon.OperationPowCA)