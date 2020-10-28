---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: Operação MultiplyByModularInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: 6deced7862ab4cb74315219eaaab97380cdf0f92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719794"
---
# <a name="multiplybymodularinteger-operation"></a>Operação MultiplyByModularInteger

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [](https://nuget.org/packages/)


Executa a multiplicação modular por uma constante de número inteiro num registo qubit.

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Descrição

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