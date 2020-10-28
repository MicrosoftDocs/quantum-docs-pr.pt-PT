---
uid: Microsoft.Quantum.MachineLearning.PartialRotationsLayer
title: Função ParcialRotationsLayer
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: PartialRotationsLayer
qsharp.summary: Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.
ms.openlocfilehash: ab964d2c43a13a5daf64aefdeccd1c26cd371ff4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722431"
---
# <a name="partialrotationslayer-function"></a><span data-ttu-id="01046-102">Função ParcialRotationsLayer</span><span class="sxs-lookup"><span data-stu-id="01046-102">PartialRotationsLayer function</span></span>

<span data-ttu-id="01046-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="01046-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="01046-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="01046-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="01046-105">Devolve uma matriz de rotações de um único qubit ao longo de um determinado eixo, parametrizado por parâmetros de modelo distintos.</span><span class="sxs-lookup"><span data-stu-id="01046-105">Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.</span></span>

```qsharp
function PartialRotationsLayer (idxsQubits : Int[], axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="01046-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="01046-106">Input</span></span>

### <a name="idxsqubits--int"></a><span data-ttu-id="01046-107">idxsQubits : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="01046-107">idxsQubits : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="01046-108">Índices para que os qubits sejam utilizados como alvos para cada rotação.</span><span class="sxs-lookup"><span data-stu-id="01046-108">Indices for the qubits to be used as the targets for each rotation.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="01046-109">eixo : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="01046-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="01046-110">O eixo de rotação para cada rotação na camada dada.</span><span class="sxs-lookup"><span data-stu-id="01046-110">The rotation axis for each rotation in the given layer.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="01046-111">Saída : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="01046-111">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="01046-112">Uma matriz de rotações controladas sobre o eixo dado, uma em cada um dos `nQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="01046-112">An array of controlled rotations about the given axis, one on each of `nQubits` qubits.</span></span>