---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterA
title: Aplicação Operação Inscreva-se
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterA
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 7a5ae78edcda363f21cadaaed5cb273d35cb60cc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841230"
---
# <a name="applytosubregistera-operation"></a>Aplicação Operação Inscreva-se

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma operação a um subregister de um registo, com qubits especificados por um conjunto dos seus índices.
O modificador `A` indica que a operação é adjacente.

```qsharp
operation ApplyToSubregisterA (op : (Qubit[] => Unit is Adj), idxs : Int[], target : Qubit[]) : Unit is Adj
```


## <a name="input"></a>Entrada

### <a name="op--qubit--unit--is-adj"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj

Operação a aplicar ao subrecípida.


### <a name="idxs--int"></a>idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]

Matriz de índices, indicando a que qubits será aplicada a operação.


### <a name="target--qubit"></a>alvo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registe-se no qual a operação atua.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyToSubregister](xref:Microsoft.Quantum.Canon.ApplyToSubregister)