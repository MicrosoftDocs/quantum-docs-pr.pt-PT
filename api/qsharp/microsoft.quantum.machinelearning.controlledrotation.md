---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: Tipo definido pelo utilizador controlledRotation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: 231afe65da3640218cbc97b9d49eae21bf6e1786
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847400"
---
# <a name="controlledrotation-user-defined-type"></a>Tipo definido pelo utilizador controlledRotation

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Descreve uma rotação controlada em termos dos seus índices de alvo e controlo, eixo de rotação e índice num vetor de parâmetros de modelo.

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a>Itens nomeados

### <a name="targetindex--int"></a>TargetIndex : [Int](xref:microsoft.quantum.lang-ref.int)

Índice do qubit alvo para esta rotação controlada.
### <a name="controlindices--int"></a>ControlIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]

Uma matriz dos índices de qubit de controlo para esta rotação.
### <a name="axis--pauli"></a>Eixo : [Pauli](xref:microsoft.quantum.lang-ref.pauli)

O eixo para esta rotação.
### <a name="parameterindex--int"></a>ParâmetroIndex : [Int](xref:microsoft.quantum.lang-ref.int)

Um índice em um vetor de parâmetro modelo descrevendo o ângulo para esta rotação.

## <a name="example"></a>Exemplo

O seguinte representa uma rotação sobre o eixo $X$do primeiro qubit num registo, controlado no segundo qubit, e com um ângulo dado pelo quarto parâmetro num modelo sequencial:

```qsharp
let controlledRotation = ControlledRotation(
    (0, [1]),
    PauliX,
    3
)
```

## <a name="remarks"></a>Observações

Uma rotação descontrolada pode ser representada por `ControlIndices` uma matriz vazia de índices, `new Int[0]` .