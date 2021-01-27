---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: AplicarPermutationUsingDecompositionWithVariableOrder operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: f33d2980ff1775b1ae8d2e2e7a4fa1e5cbe7d5ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858865"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a>AplicarPermutationUsingDecompositionWithVariableOrder operação

Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Permuta as amplitudes num estado quântico dada uma permutação usando a síntese baseada na decomposição.

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Descrição

Esta operação é uma versão mais geral da @"microsoft.quantum.synthesis.applypermutationusingdecomposition" qual a ordem variável pode ser especificada. Uma ordem variável diferente altera a sequência de decomposição e as tabelas de verdade usadas para os @"microsoft.quantum.intrinsic.x" portões controlados.  Portanto, a alteração da ordem variável altera o número de portões globais utilizados para realizar a permutação.

## <a name="input"></a>Entrada

### <a name="perm--int"></a>perm : [Int](xref:microsoft.quantum.lang-ref.int)[]

Uma permutação de elementos de $2^n$ a partir de 0.


### <a name="variableorder--int"></a>variávelOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]

Uma permutação de elementos de $n$ a partir de 0.


### <a name="qubits--littleendian"></a>qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Uma lista de $n$ qubits aos quais a permutação é aplicada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Exemplo

Para sintetizar uma `SWAP` operação:

```qsharp
using (qubits = Qubit[2]) {
  ApplyPermutationUsingDecompositionWithVariableOrder([0, 2, 1, 3], [1, 0], LittleEndian(qubits));
}
```

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)
- [Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)