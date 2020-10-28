---
uid: Microsoft.Quantum.Measurement.MResetZ
title: Operação MResetZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 9f084b03504deea9fcf25e4c797c4bde3c97a995
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711056"
---
# <a name="mresetz-operation"></a>Operação MResetZ

Espaço de nome: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)

Pacote: [](https://nuget.org/packages/)


Mede um único qubit na base Z e repõe-o para um estado inicial fixo após a medição.

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a>Descrição

Executa uma medição de um único qubit na base de $Z$-base, e garante que o qubit é devolvido a $\ket {0} $ após a medição.

## <a name="input"></a>Entrada

### <a name="target--qubit"></a>alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Um único qubit a medir.



## <a name="output--__invalidresult__"></a>Saída: __<Result> inválida__

O resultado da medição `target` na base pauli $Z$.