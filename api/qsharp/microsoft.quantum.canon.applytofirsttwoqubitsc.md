---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC
title: Aplicar operação FirstTwoQubitsC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsC
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: f71209a806b0d1d712a3c776eb45e62d1cd5d5f7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841342"
---
# <a name="applytofirsttwoqubitsc-operation"></a>Aplicar operação FirstTwoQubitsC

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma operação aos dois primeiros qubits no registo.
O modificador `C` indica que a operação é controlável.

```qsharp
operation ApplyToFirstTwoQubitsC (op : ((Qubit, Qubit) => Unit is Ctl), register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a>Entrada

### <a name="op--qubitqubit--unit--is-ctl"></a>op :[(Qubit,](xref:microsoft.quantum.lang-ref.qubit)[Qubit)](xref:microsoft.quantum.lang-ref.qubit)= [> Unit](xref:microsoft.quantum.lang-ref.unit) is Ctl

Uma operação a ser aplicada aos dois primeiros qubits


### <a name="register--qubit"></a>registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit array para os dois primeiros qubits dos quais a operação é aplicada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Isto equivale a:

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyToFirstTwoQubits](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)