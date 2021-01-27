---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitCA
title: Aplicar operaçãoToFirstQubitCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitCA
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: ba82199cc7a548d771027141780873c05de71c57
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841435"
---
# <a name="applytofirstqubitca-operation"></a>Aplicar operaçãoToFirstQubitCA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica operação op ao primeiro qubit no registo.
O modificador `CA` indica que a operação é controlável e adjacente.

```qsharp
operation ApplyToFirstQubitCA (op : (Qubit => Unit is Adj + Ctl), register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="op--qubit--unit--is-adj--ctl"></a>op [](xref:microsoft.quantum.lang-ref.qubit) : => [Qubit Unit](xref:microsoft.quantum.lang-ref.unit) é Adj + Ctl

Uma operação a ser aplicada ao primeiro qubit


### <a name="register--qubit"></a>registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit array para o primeiro qubit de qual a operação é aplicada



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyToFirstQubit](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)