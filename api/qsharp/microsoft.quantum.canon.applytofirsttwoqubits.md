---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubits
title: Aplicação OperaçãoToFirstTwoQubits
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubits
qsharp.summary: Applies an operation to the first two qubits in the register.
ms.openlocfilehash: c89ea89c055a950a9aee533653d40c84d8e179da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841373"
---
# <a name="applytofirsttwoqubits-operation"></a>Aplicação OperaçãoToFirstTwoQubits

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma operação aos dois primeiros qubits no registo.

```qsharp
operation ApplyToFirstTwoQubits (op : ((Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="op--qubitqubit--unit"></a>op :[(Qubit,](xref:microsoft.quantum.lang-ref.qubit)[Qubit)](xref:microsoft.quantum.lang-ref.qubit)= [unidade](xref:microsoft.quantum.lang-ref.unit)> 

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

- [Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA)
- [Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC)
- [Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA)