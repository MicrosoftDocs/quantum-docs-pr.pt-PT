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
# <a name="partialrotationslayer-function"></a><span data-ttu-id="4beeb-102">Função ParcialRotationsLayer</span><span class="sxs-lookup"><span data-stu-id="4beeb-102">PartialRotationsLayer function</span></span>

<span data-ttu-id="4beeb-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="4beeb-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="4beeb-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="4beeb-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="4beeb-105">Devolve uma matriz de rotações de um único qubit ao longo de um determinado eixo, parametrizado por parâmetros de modelo distintos.</span><span class="sxs-lookup"><span data-stu-id="4beeb-105">Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.</span></span>

```qsharp
function PartialRotationsLayer (idxsQubits : Int[], axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="4beeb-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="4beeb-106">Input</span></span>

### <a name="idxsqubits--int"></a><span data-ttu-id="4beeb-107">idxsQubits : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="4beeb-107">idxsQubits : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="4beeb-108">Índices para que os qubits sejam utilizados como alvos para cada rotação.</span><span class="sxs-lookup"><span data-stu-id="4beeb-108">Indices for the qubits to be used as the targets for each rotation.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="4beeb-109">eixo : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="4beeb-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="4beeb-110">O eixo de rotação para cada rotação na camada dada.</span><span class="sxs-lookup"><span data-stu-id="4beeb-110">The rotation axis for each rotation in the given layer.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="4beeb-111">Saída : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="4beeb-111">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="4beeb-112">Uma matriz de rotações controladas sobre o eixo dado, uma em cada um dos `nQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="4beeb-112">An array of controlled rotations about the given axis, one on each of `nQubits` qubits.</span></span>