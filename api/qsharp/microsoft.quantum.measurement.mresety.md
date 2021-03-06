---
uid: Microsoft.Quantum.Measurement.MResetY
title: Operação MResety
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 2e41e76a46b68178a8a22b39131d6ca2a8c50b64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854640"
---
# <a name="mresety-operation"></a>Operação MResety

Espaço de nome: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Mede um único qubit na base Y e repõe-o a um estado inicial fixo após a medição.

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a>Descrição

Executa uma medição de um único qubit na base de $Y$-base, e garante que o qubit é devolvido a $\ket {0} $ após a medição.

## <a name="input"></a>Entrada

### <a name="target--qubit"></a>alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Um único qubit a medir.



## <a name="output--__invalidresult__"></a>Saída: __<Result> inválida__

O resultado da medição `target` na base pauli $Y$.