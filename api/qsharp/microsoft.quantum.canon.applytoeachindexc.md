---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexC
title: Aplicação Operação SeachIndexC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexC
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: c005f616d580438891fbcb9f3c727b8e961e138d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850815"
---
# <a name="applytoeachindexc-operation"></a>Aplicação Operação SeachIndexC

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma operação de um único qubit a cada elemento indexado num registo.
O modificador `C` indica que a operação de um único qubit é controlável.

```qsharp
operation ApplyToEachIndexC<'T> (singleElementOperation : ((Int, 'T) => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a>Entrada

### <a name="singleelementoperation--intt--unit--is-ctl"></a>singleElementOperation :[(Int](xref:microsoft.quantum.lang-ref.int),'T) = [> Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl

Operação a aplicar a cada qubit.


### <a name="register--t"></a>registo : 'T[]

Matriz de qubits para aplicar a operação dada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O alvo em que cada uma das operações atua.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyToEachIndex](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)