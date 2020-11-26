---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: Operação SetToBasisState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: 2612bfe488c830abd835be89b2f8ea6795abf675
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194156"
---
# <a name="settobasisstate-operation"></a>Operação SetToBasisState

Espaço de nome: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Define um qubit a um dado estado de base computacional medindo o qubit e aplicando um pouco de flip, se necessário.

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a>Entrada

### <a name="desired--__invalidresult__"></a>desejado : __<Result> inválido__

A base diz que o qubit deve ser definido para.


### <a name="target--qubit"></a>alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

O qubit cujo estado deve ser definido.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Como invariante desta operação, a chamada `M(q)` imediatamente a seguir `SetToBasisState(result, q)` `result` regressará.