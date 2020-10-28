---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterC
title: Função restrita DoubregisterC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterC
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 2ca32cf8c85f33f498a30f71833b3dd69db6da6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715511"
---
# <a name="restrictedtosubregisterc-function"></a>Função restrita DoubregisterC

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Restringe uma operação a um conjunto de índices de um registo, isto é, um subrecretário.
O modificador `C` indica que a operação é controlável.

```qsharp
function RestrictedToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[]) : (Qubit[] => Unit is Ctl)
```


## <a name="input"></a>Entrada

### <a name="op--qubit--unit-ctl"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl

Operação a restringir a um subregister.


### <a name="idxs--int"></a>idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]

Matriz de índices, indicando a que qubits a operação será restringida.



## <a name="output--qubit--unit-ctl"></a>Saída : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl



## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.RestrictedToSubregister](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)