---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: Função OperationPowCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 753063452616747309e3e228ce8a702f4378c61f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715676"
---
# <a name="operationpowca-function"></a>Função OperationPowCA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Eleva uma operação a uma potência.
O modificador `A` indica que a operação é controlável e adjacente.

Ou seja, dada uma operação que representa um portão $U$, devolve uma nova operação $U^m$ por uma potência $m$.

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a>Entrada

### <a name="op--t--unit-ctl--adj"></a>op : 'T = unidade> [Ctl](xref:microsoft.quantum.lang-ref.unit) + Adj

Uma operação $U$ representando o portão a ser repetido.


### <a name="power--int"></a>poder : [Int](xref:microsoft.quantum.lang-ref.int)

O número de vezes que $U$ deve ser repetido.



## <a name="output--t--unit-ctl--adj"></a>Saída : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit)> Ctl + Adj

Uma nova operação que representa $U^m$, onde $m = \texttt{power}$.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de operação a ser alimentada.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.OperationPow](xref:Microsoft.Quantum.Canon.OperationPow)