---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: Função CyclicEntanglingLayer
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 6e0f5057b35baefe2677126ba70ee4fddde7d4db
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720514"
---
# <a name="cyclicentanglinglayer-function"></a>Função CyclicEntanglingLayer

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [](https://nuget.org/packages/)


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