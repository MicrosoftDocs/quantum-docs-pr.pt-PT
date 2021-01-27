---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA
title: Aplicar operação FirstThreeQubitsA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsA
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 7c464b1decb5a30a996dfc1df9f1f1921613c73e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841422"
---
# <a name="applytofirstthreequbitsa-operation"></a>Aplicar operação FirstThreeQubitsA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma operação aos três primeiros qubits no registo.
O modificador `A` indica que a operação é adjacente.

```qsharp
operation ApplyToFirstThreeQubitsA (op : ((Qubit, Qubit, Qubit) => Unit is Adj), register : Qubit[]) : Unit is Adj
```


## <a name="input"></a>Entrada

### <a name="op--qubitqubitqubit--unit--is-adj"></a>op :[(Qubit,](xref:microsoft.quantum.lang-ref.qubit)[Qubit,](xref:microsoft.quantum.lang-ref.qubit)[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) é Adj

Uma operação a ser aplicada aos três primeiros qubits


### <a name="register--qubit"></a>registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit array para os primeiros três qubits dos quais a operação é aplicada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Isto equivale a:

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyToFirstThreeQubits](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)