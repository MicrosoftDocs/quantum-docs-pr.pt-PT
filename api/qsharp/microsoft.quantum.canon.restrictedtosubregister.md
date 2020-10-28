---
uid: Microsoft.Quantum.Canon.RestrictedToSubregister
title: Função restrita DoubregistaToSubregister
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregister
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister.
ms.openlocfilehash: a8b599035de6fede10bdaf8cef17f2124a59f064
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715539"
---
# <a name="restrictedtosubregister-function"></a>Função restrita DoubregistaToSubregister

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Restringe uma operação a um conjunto de índices de um registo, isto é, um subrecretário.

```qsharp
function RestrictedToSubregister (op : (Qubit[] => Unit), idxs : Int[]) : (Qubit[] => Unit)
```


## <a name="input"></a>Entrada

### <a name="op--qubit--unit"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

Operação a restringir a um subregister.


### <a name="idxs--int"></a>idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]

Matriz de índices, indicando a que qubits a operação será restringida.



## <a name="output--qubit--unit"></a>Saída : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 



## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.RestrictedToSubregistera](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterA)
- [Microsoft.Quantum.Canon.RestrictedToSubregisterC](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterC)
- [Microsoft.Quantum.Canon.RestrictedToSubregisterCA](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterCA)