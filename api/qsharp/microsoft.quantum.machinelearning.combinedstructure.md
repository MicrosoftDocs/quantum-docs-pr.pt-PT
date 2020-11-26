---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: Função estruturação combinada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: 0a7d66be8b45d6a9df95b425e66b9b6bba241136
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211972"
---
# <a name="combinedstructure-function"></a><span data-ttu-id="a9ae7-102">Função estruturação combinada</span><span class="sxs-lookup"><span data-stu-id="a9ae7-102">CombinedStructure function</span></span>

<span data-ttu-id="a9ae7-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a9ae7-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="a9ae7-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a9ae7-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="a9ae7-105">Tendo em conta uma ou mais camadas de rotações controladas, devolve uma única camada com índice de parâmetros de modelo deslocado de modo a que camadas distintas sejam parametrizadas por parâmetros de modelo distintos.</span><span class="sxs-lookup"><span data-stu-id="a9ae7-105">Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.</span></span>

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="a9ae7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a9ae7-106">Input</span></span>

### <a name="layers--controlledrotation"></a><span data-ttu-id="a9ae7-107">camadas : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[][]</span><span class="sxs-lookup"><span data-stu-id="a9ae7-107">layers : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[][]</span></span>

<span data-ttu-id="a9ae7-108">As camadas a combinar.</span><span class="sxs-lookup"><span data-stu-id="a9ae7-108">The layers to be combined.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="a9ae7-109">Saída : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="a9ae7-109">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="a9ae7-110">Uma única camada de rotações controladas, representando a concatenação de todas as outras camadas.</span><span class="sxs-lookup"><span data-stu-id="a9ae7-110">A single layer of controlled rotations, representing the concatenation of all other layers.</span></span>