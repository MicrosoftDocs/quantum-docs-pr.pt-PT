---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: Função CyclicEntanglingLayer
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 5421765e36ef3e8e744e118206dafcb2bb582cc2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211938"
---
# <a name="cyclicentanglinglayer-function"></a>Função CyclicEntanglingLayer

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Devolve uma série de rotações controladas ao longo de um determinado eixo, dispostas ciclicamente através de um registo de qubits, e parametrizadas por parâmetros de modelo distintos.

```qsharp
function CyclicEntanglingLayer (nQubits : Int, axis : Pauli, stride : Int) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Entrada

### <a name="nqubits--int"></a>nQubits : [Int](xref:microsoft.quantum.lang-ref.int)

O número de qubits agidos pela camada dada.


### <a name="axis--pauli"></a>eixo : [Pauli](xref:microsoft.quantum.lang-ref.pauli)

O eixo de rotação para cada rotação na camada dada.


### <a name="stride--int"></a>passo : [Int](xref:microsoft.quantum.lang-ref.int)

A separação entre os índices de alvo e de controlo para cada rotação.



## <a name="output--controlledrotation"></a>Saída : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Uma matriz de rotações controladas de dois qubits estabelecidas cíclicas através de um registo de `nQubits` qubits.