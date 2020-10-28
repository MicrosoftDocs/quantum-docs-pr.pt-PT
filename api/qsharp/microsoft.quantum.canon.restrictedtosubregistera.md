---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterA
title: Função RestritaToSubregisterA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterA
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: d45c43caed35df8fb89d9d38e540faf5a21ea064
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715536"
---
# <a name="restrictedtosubregistera-function"></a>Função RestritaToSubregisterA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Restringe uma operação a um conjunto de índices de um registo, isto é, um subrecretário.
O modificador `A` indica que a operação é adjacente.

```qsharp
function RestrictedToSubregisterA (op : (Qubit[] => Unit is Adj), idxs : Int[]) : (Qubit[] => Unit is Adj)
```


## <a name="input"></a>Entrada

### <a name="op--qubit--unit-adj"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj

Operação a restringir a um subregister.


### <a name="idxs--int"></a>idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]

Matriz de índices, indicando a que qubits a operação será restringida.



## <a name="output--qubit--unit-adj"></a>Saída : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj



## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.RestrictedToSubregister](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)