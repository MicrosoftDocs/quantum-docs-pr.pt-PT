---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: Permitir a operação DoMSTNQubits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: ddbed96df0d95cfd78730c091a6a81ee6e49c349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713058"
---
# <a name="allowatmostnqubits-operation"></a>Permitir a operação DoMSTNQubits

Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacote: [](https://nuget.org/packages/)


Entre uma chamada para esta operação e o seu adjacente, afirma que, no máximo, um determinado número de qubits adicionais são atribuídos com recurso a declarações.

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit
```


## <a name="input"></a>Entrada

### <a name="nqubits--int"></a>nQubits : [Int](xref:microsoft.quantum.lang-ref.int)

O número máximo de qubits que podem ser atribuídos.


### <a name="message--string"></a>mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)

Uma mensagem a ser exibida após o fracasso.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Esta operação pode ser substituída por um não-operatório sobre alvos que não a suportem.