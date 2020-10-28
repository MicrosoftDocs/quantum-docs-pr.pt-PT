---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: Função estruturação combinada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: fbfd87761a40abe350e5f955fb53d8024eeb614e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720515"
---
# <a name="combinedstructure-function"></a>Função estruturação combinada

Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pacote: [](https://nuget.org/packages/)


Tendo em conta uma ou mais camadas de rotações controladas, devolve uma única camada com índice de parâmetros de modelo deslocado de modo a que camadas distintas sejam parametrizadas por parâmetros de modelo distintos.

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Entrada

### <a name="layers--controlledrotation"></a>camadas : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[][]

As camadas a combinar.



## <a name="output--controlledrotation"></a>Saída : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Uma única camada de rotações controladas, representando a concatenação de todas as outras camadas.