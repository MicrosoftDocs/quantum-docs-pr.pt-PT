---
uid: Microsoft.Quantum.Canon.OperationPowC
title: Função OperationPowC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: f3c51410fb7c091385b64a1c4c99b3972d5055b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715690"
---
# <a name="operationpowc-function"></a>Função OperationPowC

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Eleva uma operação a uma potência.
O modificador `C` indica que a operação é controlável.

Ou seja, dada uma operação que representa um portão $U$, devolve uma nova operação $U^m$ por uma potência $m$.

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a>Entrada

### <a name="op--t--unit-ctl"></a>op : 'T => [Unidade](xref:microsoft.quantum.lang-ref.unit) Ctl

Uma operação $U$ representando o portão a ser repetido.


### <a name="power--int"></a>poder : [Int](xref:microsoft.quantum.lang-ref.int)

O número de vezes que $U$ deve ser repetido.



## <a name="output--t--unit-ctl"></a>Saída : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit)> Ctl

Uma nova operação que representa $U^m$, onde $m = \texttt{power}$.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de operação a ser alimentada.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.OperationPow](xref:Microsoft.Quantum.Canon.OperationPow)