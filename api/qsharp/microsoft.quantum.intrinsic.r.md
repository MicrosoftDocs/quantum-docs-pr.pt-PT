---
uid: Microsoft.Quantum.Intrinsic.R
title: R operação
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 89aa5b2867068d4352a0b9550e8d22aa77439111
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199034"
---
# <a name="r-operation"></a>R operação

Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Aplica uma rotação sobre o eixo Pauli dado.

\start{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} onde $\mu \in \{ I, X, Y, Z \} $.

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="pauli--pauli"></a>pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Operador Pauli ($\mu$) a ser exponencial para formar a rotação.


### <a name="theta--double"></a>theta : [Duplo](xref:microsoft.quantum.lang-ref.double)

Ângulo sobre o qual o qubit deve ser rodado.


### <a name="qubit--qubit"></a>qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit ao qual o portão deve ser aplicado.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Quando `pauli = PauliI` convocada, esta operação aplica uma *fase global.* Esta fase pode ser significativa quando usada com o `Controlled` functor.