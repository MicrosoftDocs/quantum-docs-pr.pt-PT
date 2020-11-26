---
uid: Microsoft.Quantum.Measurement.MResetZ
title: Operação MResetZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 494f11c8129175ddd84c6539f5e9df1a758e8a82
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194139"
---
# <a name="mresetz-operation"></a>Operação MResetZ

Espaço de nome: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Mede um único qubit na base Z e repõe-o para um estado inicial fixo após a medição.

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a>Description

Executa uma medição de um único qubit na base de $Z$-base, e garante que o qubit é devolvido a $\ket {0} $ após a medição.

## <a name="input"></a>Entrada

### <a name="target--qubit"></a>alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Um único qubit a medir.



## <a name="output--__invalidresult__"></a>Saída: __<Result> inválida__

O resultado da medição `target` na base pauli $Z$.