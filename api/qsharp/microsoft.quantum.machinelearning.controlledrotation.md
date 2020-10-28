---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: Tipo definido pelo utilizador controlledRotation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: afc425c16ab550fd414e656484c9ff6f0f8f3ef4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711364"
---
# <a name="controlledrotation-user-defined-type"></a>Tipo definido pelo utilizador controlledRotation

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [](https://nuget.org/packages/)


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

## <a name="remarks"></a>Observações

Uma rotação descontrolada pode ser representada por `ControlIndices` uma matriz vazia de índices, `new Int[0]` .