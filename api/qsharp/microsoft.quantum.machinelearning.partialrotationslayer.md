---
uid: Microsoft.Quantum.MachineLearning.PartialRotationsLayer
title: Função ParcialRotationsLayer
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: PartialRotationsLayer
qsharp.summary: Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.
ms.openlocfilehash: e230df9b28c59e1d532d5b36adf90efa01f0f33e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852927"
---
# <a name="partialrotationslayer-function"></a>Função ParcialRotationsLayer

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Devolve uma matriz de rotações de um único qubit ao longo de um determinado eixo, parametrizado por parâmetros de modelo distintos.

```qsharp
function PartialRotationsLayer (idxsQubits : Int[], axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Entrada

### <a name="idxsqubits--int"></a>idxsQubits : [Int](xref:microsoft.quantum.lang-ref.int)[]

Índices para que os qubits sejam utilizados como alvos para cada rotação.


### <a name="axis--pauli"></a>eixo : [Pauli](xref:microsoft.quantum.lang-ref.pauli)

O eixo de rotação para cada rotação na camada dada.



## <a name="output--controlledrotation"></a>Saída : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Uma matriz de rotações controladas sobre o eixo dado, uma em cada um dos `nQubits` qubits.