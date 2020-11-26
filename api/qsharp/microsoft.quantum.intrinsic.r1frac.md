---
uid: Microsoft.Quantum.Intrinsic.R1Frac
title: Operação R1Frac
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1Frac
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.

  \begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}). \end{align}

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r", and does not include the > factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".
ms.openlocfilehash: eb2dd8750ed5ad9fc75ca24bb4c8ef36298f69f4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198780"
---
# <a name="r1frac-operation"></a>Operação R1Frac

Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Aplica uma rotação sobre o estado $\ket {1} $ por um ângulo especificado como uma fração dedídica.

\start{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}).
\end{align}

> [!WARNING]
> Esta operação utiliza a convenção de sinais **oposto** de @"microsoft.quantum.intrinsic.r" , e não inclui o fator de $1/ 2$ incluído por @"microsoft.quantum.intrinsic.r1" .

```qsharp
operation R1Frac (numerator : Int, power : Int, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

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
RFrac(PauliZ, -numerator, denominator + 1, qubit);
RFrac(PauliI, numerator, denominator + 1, qubit);
```