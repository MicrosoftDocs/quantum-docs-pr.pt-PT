---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: Aplicação OperaçãoToachC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: b8b51e1c8d52c140c3ca1e5a54d0bd4cf4873046
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850841"
---
# <a name="applytoeachc-operation"></a>Aplicação OperaçãoToachC

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma operação de um único qubit a cada elemento num registo.
O modificador `C` indica que a operação de um único qubit é controlável.

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a>Entrada

### <a name="singleelementoperation--t--unit--is-ctl"></a>singleElementOperação : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Ctl

Operação a aplicar a cada qubit.


### <a name="register--t"></a>registo : 'T[]

Matriz de qubits para aplicar a operação dada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O alvo no qual a operação atua.

## <a name="example"></a>Exemplo

Prepare um estado de três qubits $\ket{+}$ estado:

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyToEach](xref:Microsoft.Quantum.Canon.ApplyToEach)