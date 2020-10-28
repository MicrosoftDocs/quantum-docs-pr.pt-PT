---
uid: Microsoft.Quantum.Measurement.MResetY
title: Operação MResety
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 48aba7317d0e48d089ec6c4814efdee51bb8e2ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725007"
---
# <a name="mresety-operation"></a>Operação MResety

Espaço de nome: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)

Pacote: [](https://nuget.org/packages/)


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