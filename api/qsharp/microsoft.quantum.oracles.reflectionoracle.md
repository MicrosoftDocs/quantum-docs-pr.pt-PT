---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: Tipo definido pelo utilizador Reflexoracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 7bb0626e7cca9ae0b640699ea57f2e114bda2d06
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226660"
---
# <a name="reflectionoracle-user-defined-type"></a>Tipo definido pelo utilizador Reflexoracle

Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa um oráculo de reflexão.

Um oráculo de reflexão, $O$, tem entradas:

- A fase $\phi$ para rodar o subespaço refletido.
- O registo de qubits para realizar a reflexão dada.

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a>Itens nomeados

### <a name="applyreflection--doublequbit--unit--is-adj--ctl"></a>ApplyReflection :[(Duplo,](xref:microsoft.quantum.lang-ref.double)[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = [> Unidade](xref:microsoft.quantum.lang-ref.unit) é Adj + Ctl



## <a name="remarks"></a>Observações

Este oráculo $O = \boldone - (1 - e^{i \phi}) \ket{\psi}\bra{\psi}$ realiza um reflexo parcial por uma fase $\phi$ sobre um único estado puro $\ket{\psi}$.