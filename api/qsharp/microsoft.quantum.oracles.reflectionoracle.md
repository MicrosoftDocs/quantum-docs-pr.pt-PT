---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: Tipo definido pelo utilizador Reflexoracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 8e35e7e508ea7e0c30ea2a70633f71a6c87d4be1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724209"
---
# <a name="reflectionoracle-user-defined-type"></a>Tipo definido pelo utilizador Reflexoracle

Espaço de nome: [Microsoft.Quantum.Oráculos](xref:Microsoft.Quantum.Oracles)

Pacote: [](https://nuget.org/packages/)


Representa um oráculo de reflexão.

Um oráculo de reflexão, $O$, tem entradas:

- A fase $\phi$ para rodar o subespaço refletido.
- O registo de qubits para realizar a reflexão dada.

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a>Itens nomeados

### <a name="applyreflection--doublequbit--unit-adj--ctl"></a>ApplyReflection :[(Duplo,](xref:microsoft.quantum.lang-ref.double)[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl



## <a name="remarks"></a>Observações

Este oráculo $O = \boldone - (1 - e^{i \phi}) \ket{\psi}\bra{\psi}$ realiza um reflexo parcial por uma fase $\phi$ sobre um único estado puro $\ket{\psi}$.