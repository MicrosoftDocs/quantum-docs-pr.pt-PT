---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterCA
title: Função RestritaToSubregisterCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterCA
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: e81193a85451b72a69a595fa81a9fb07f3038c22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715525"
---
# <a name="restrictedtosubregisterca-function"></a>Função RestritaToSubregisterCA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Restringe uma operação a um conjunto de índices de um registo, isto é, um subrecretário.
O modificador `CA` indica que a operação é controlável e adjacente.

```qsharp
function RestrictedToSubregisterCA (op : (Qubit[] => Unit is Adj + Ctl), idxs : Int[]) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrada

### <a name="op--qubit--unit-adj--ctl"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl

Operação a restringir a um subregister.


### <a name="idxs--int"></a>idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]

Matriz de índices, indicando a que qubits a operação será restringida.



## <a name="output--qubit--unit-adj--ctl"></a>Saída : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit)> Adj + Ctl



## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.RestrictedToSubregister](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)