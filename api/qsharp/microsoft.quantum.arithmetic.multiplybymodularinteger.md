---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: Operação MultiplyByModularInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: 080414d208a2a0c114857db8e93efb4cd74a4d8d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222580"
---
# <a name="multiplybymodularinteger-operation"></a>Operação MultiplyByModularInteger

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Executa a multiplicação modular por uma constante de número inteiro num registo qubit.

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Vamos `modulus` denotar $N$ e `constMultiplier` por $a$.
Em seguida, esta operação implementa uma operação unitária definida pelo seguinte mapa na base computacional: $$ \start{align} \ket{y} \mapsto \ket{(a\cdot y) \operatorname{mod} N} \end{align} $$ por todas as $y$ entre $0$ e $N - 1$.

## <a name="input"></a>Entrada

### <a name="constmultiplier--int"></a>constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)

Constante pela qual multiplicador está a ser multiplicado. Deve ser co-prime para modulus.


### <a name="modulus--int"></a>módulo : [Int](xref:microsoft.quantum.lang-ref.int)

A operação de multiplicação é realizada `modulus` modulo.


### <a name="multiplier--littleendian"></a>multiplicador : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

O número a ser multiplicado por uma constante.
Esta é uma variedade de qubits codificando um inteiro em formato pouco endiano.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

- Para o diagrama do circuito e explicação consulte a figura 7 na [página 8 do arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)
- Esta operação corresponde a Uₐ em [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)