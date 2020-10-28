---
uid: Microsoft.Quantum.Canon.OperationPowA
title: Função OperationPowA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 66df354c6de7e48624712276882759043b78466c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715718"
---
# <a name="operationpowa-function"></a>Função OperationPowA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Eleva uma operação a uma potência.
O modificador `A` indica que a operação é adjacente.

Ou seja, dada uma operação que representa um portão $U$, devolve uma nova operação $U^m$ por uma potência $m$.

```qsharp
function OperationPowA<'T> (op : ('T => Unit is Adj), power : Int) : ('T => Unit is Adj)
```


## <a name="input"></a>Entrada

### <a name="op--t--unit-adj"></a>op : 'T = [Unit](xref:microsoft.quantum.lang-ref.unit) unidade> Adj

Uma operação $U$ representando o portão a ser repetido.


### <a name="power--int"></a>poder : [Int](xref:microsoft.quantum.lang-ref.int)

O número de vezes que $U$ deve ser repetido.



## <a name="output--t--unit-adj"></a>Saída : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit)> Adj

Uma nova operação que representa $U^m$, onde $m = \texttt{power}$.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de operação a ser alimentada.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.OperationPow](xref:Microsoft.Quantum.Canon.OperationPow)