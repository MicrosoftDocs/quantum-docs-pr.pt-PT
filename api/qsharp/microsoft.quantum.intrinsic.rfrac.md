---
uid: Microsoft.Quantum.Intrinsic.RFrac
title: Operação RFrac
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: RFrac
qsharp.summary: >-
  Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.

  \begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r".
ms.openlocfilehash: 9fe6aee6c7bb9e52538eae5d2caa2a6025cb85d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723509"
---
# <a name="rfrac-operation"></a>Operação RFrac

Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)

Pacote: [](https://nuget.org/packages/)


Aplica uma rotação sobre o eixo Pauli dado por um ângulo especificado como uma fração diádica.

\start{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi \n \sigma_{\mu} / 2^k}, \end{align} onde $\mu \in \{ I, X, Y, Z \} $.

> [!WARNING]
> Esta operação utiliza a convenção de sinais **oposto** de @"microsoft.quantum.intrinsic.r" .

```qsharp
operation RFrac (pauli : Pauli, numerator : Int, power : Int, qubit : Qubit) : Unit
```


## <a name="input"></a>Entrada

### <a name="pauli--pauli"></a>pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Operador Pauli a ser exponencial para formar a rotação.


### <a name="numerator--int"></a>numerador : [Int](xref:microsoft.quantum.lang-ref.int)

Numerador na representação da fração dedódica do ângulo pelo qual o qubit deve ser rodado.


### <a name="power--int"></a>poder : [Int](xref:microsoft.quantum.lang-ref.int)

Potência de dois especificando o denominador do ângulo pelo qual o qubit deve ser rodado.


### <a name="qubit--qubit"></a>qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit ao qual o portão deve ser aplicado.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Equivalente a:

```qsharp
// PI() is a Q# function that returns an approximation of π.
R(pauli, -PI() * IntAsDouble(numerator) / IntAsDouble(2 ^ (power - 1)), qubit);
```