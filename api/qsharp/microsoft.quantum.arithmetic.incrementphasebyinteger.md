---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: Operação IncrementPhaseByInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 54b83b3d4460c05478543c51f8f9c0b0e7f5b1fa
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222920"
---
# <a name="incrementphasebyinteger-operation"></a>Operação IncrementPhaseByInteger

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Incrementa um registo quântico não assinado por um inteiro clássico, usando rotações de fase.

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Suponha que `target` codifica um inteiro não assinado $x$ em uma codificação pouco endiana e isso é igual a `increment` $a$.
Em seguida, esta operação implementa o unitário $\ket{x} \mapsto \ket{x + a}$, onde a adição é realizada modulo $2^n$, onde $n = \texttt{Comprimento (alvo!)} $.

## <a name="input"></a>Entrada

### <a name="increment--int"></a>incremento : [Int](xref:microsoft.quantum.lang-ref.int)

O inteiro pelo qual o `target` é incrementado por.


### <a name="target--phaselittleendian"></a>alvo : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

Um registo quântico que codifica um número inteiro não assinado utilizando a codificação pouco endiana na base dual (QFT).



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Note que simplificamos o circuito porque o incremento é uma constante clássica, não um registo quântico.

Consulte a figura na [ página 6 do arXiv:quant-ph/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) para o diagrama do circuito e explicação.

## <a name="references"></a>Referências

- [*Thomas G. Draper,* arXiv:quant-ph/0008033](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Aithmetic.IncrementByInteger](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)