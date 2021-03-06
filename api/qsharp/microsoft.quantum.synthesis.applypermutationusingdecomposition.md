---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition
title: AplicaçãoPermutationSingDecomposition operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecomposition
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 765b6d301363021f5b57a22f90e2ada38c9c09ec
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857400"
---
# <a name="applypermutationusingdecomposition-operation"></a>AplicaçãoPermutationSingDecomposition operação

Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Permuta as amplitudes num estado quântico dada uma permutação usando a síntese baseada na decomposição.

```qsharp
operation ApplyPermutationUsingDecomposition (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Descrição

Este procedimento implementa a abordagem da síntese baseada na decomposição.  A entrada é uma permutação $\pi$ acima de $2^n$ elementos $ \{ 0, \dots, 2^n-1 \} $, o que representa uma função booleana reversível reversível $n$-variável.
O algoritmo executa iterativamente os seguintes passos para cada índice variável $i$:

1. Computação $((\pi_l, \pi_r), \pi')$ de tal forma que as imagens de $\pi_l$ e $\pi_r$ não mudam bits nos seus elementos em índices que não $i$ e imagens de $\pi'$ não mudam um pouco $i$ nos seus elementos.
2. Desacorra $\pi \leftarrow \pi'$, e obtém tabelas de verdade de $\pi_l$ e $\pi_r$ com base em elementos que não são pontos fixos.

Após a aplicação destes passos para todos os índices variáveis, a permutação restante $\pi$ será a identidade, e com base nas tabelas e índices de verdade recolhidos, pode-se aplicar operações controladas pela tabela da verdade @"microsoft.quantum.intrinsic.x" usando a @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" operação.

A ordem variável é $0, \pontos, n - 1$.  Uma ordem variável personalizada pode ser especificada na operação @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder" .

## <a name="input"></a>Entrada

### <a name="perm--int"></a>perm : [Int](xref:microsoft.quantum.lang-ref.int)[]

Uma permutação de elementos de $2^n$ a partir de 0.


### <a name="qubits--littleendian"></a>qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Uma lista de $n$ qubits aos quais a permutação é aplicada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Exemplo

Para sintetizar uma `SWAP` operação:

```qsharp
using (qubits = Qubit[2]) {
  ApplyPermutationUsingDecomposition([0, 2, 1, 3], LittleEndian(qubits));
}
```

## <a name="references"></a>Referências

- [*Alexis De Vos*, *Yvan Van Rentergem*, Adv. em Matemática.](http://www.aimsciences.org/article/doi/10.3934/amc.2008.2.183)
- [*Mathias Soeken*, *Laura Tague*, *Gerhard W. Dueck,* *Rolf Drechsler*, Journal of Symbolic Computation 73 (2016), pp. 1--26](https://www.sciencedirect.com/science/article/pii/S0747717115000188?via%3Dihub)

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder)
- [Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)