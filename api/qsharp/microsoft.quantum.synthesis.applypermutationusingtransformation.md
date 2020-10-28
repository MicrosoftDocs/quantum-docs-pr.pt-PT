---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation
title: AplicaçãoPermutationUsingTransformation operation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingTransformation
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.
ms.openlocfilehash: b7196c592690a00da49b17f52b30536ba97b6035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725287"
---
# <a name="applypermutationusingtransformation-operation"></a>AplicaçãoPermutationUsingTransformation operation

Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacote: [](https://nuget.org/packages/)


Permuta as amplitudes num estado quântico dada uma permutação usando a síntese baseada na transformação.

```qsharp
operation ApplyPermutationUsingTransformation (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Descrição

Este procedimento implementa a abordagem de síntese baseada na transformação unidirecional.  A entrada é uma permutação $\pi$ acima de $2^n$ elementos $ \{ 0, \dots, 2^n-1 \} $, o que representa uma função boolean reversível reversível $n$-variável.
O algoritmo executa iterativamente os seguintes passos:

1. Encontre o menor $x$ de tal forma que $x \ne \pi(x) = y$.
2. Encontre operações Toffoli com vários controlos, que se aplicam às saídas fazem $\pi(x) = x$ e não mudem $\pi(x')$ para todos os $x' < x$

## <a name="input"></a>Entrada

### <a name="perm--int"></a>perm : [Int](xref:microsoft.quantum.lang-ref.int)[]

Uma permutação de elementos de $2^n$ a partir de 0.


### <a name="qubits--littleendian"></a>qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Uma lista de $n$ qubits aos quais a permutação é aplicada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referências

- [*D. Michael Miller* , *Dmitri Maslov* , *Gerhard W. Dueck,* Proc. DAC 2003, IEEE, pp. 318-323, 2003](https://doi.org/10.1145/775832.775915)
- [*Mathias Soeken* , *Gerhard W. Dueck* , *D. Michael Miller* , Proc. RC 2016, Springer, pp. 307-321, 2016](https://doi.org/10.1007/978-3-319-40578-0_22)

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)