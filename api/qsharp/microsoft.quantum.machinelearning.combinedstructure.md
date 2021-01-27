---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: Função estruturação combinada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: b8ec007202c8e63dc2e98d0c752f6ba1a453e236
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847422"
---
# <a name="combinedstructure-function"></a>Função estruturação combinada

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Tendo em conta uma ou mais camadas de rotações controladas, devolve uma única camada com índice de parâmetros de modelo deslocado de modo a que camadas distintas sejam parametrizadas por parâmetros de modelo distintos.

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Entrada

### <a name="layers--controlledrotation"></a>camadas : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[][]

As camadas a combinar.



## <a name="output--controlledrotation"></a>Saída : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Uma única camada de rotações controladas, representando a concatenação de todas as outras camadas.

## <a name="example"></a>Exemplo

Os seguintes são equivalentes:

```qsharp
let structure = CombinedStructure([
    LocalRotationLayer(2, PauliY),
    CyclicEntanglingLayer(3, PauliX, 2)
]);
let structure = [
    ControlledRotation((0, new Int[0]), PauliY, 0),
    ControlledRotation((1, new Int[0]), PauliY, 1),
    ControlledRotation((0, [2]), PauliX, 2),
    ControlledRotation((1, [0]), PauliX, 3),
    ControlledRotation((2, [1]), PauliX, 4)
];
```