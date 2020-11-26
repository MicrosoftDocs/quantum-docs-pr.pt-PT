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
# <a name="cyclicentanglinglayer-function"></a><span data-ttu-id="e8ac4-102">Função CyclicEntanglingLayer</span><span class="sxs-lookup"><span data-stu-id="e8ac4-102">CyclicEntanglingLayer function</span></span>

<span data-ttu-id="e8ac4-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="e8ac4-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="e8ac4-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="e8ac4-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="e8ac4-105">Devolve uma série de rotações controladas ao longo de um determinado eixo, dispostas ciclicamente através de um registo de qubits, e parametrizadas por parâmetros de modelo distintos.</span><span class="sxs-lookup"><span data-stu-id="e8ac4-105">Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.</span></span>

```qsharp
function CyclicEntanglingLayer (nQubits : Int, axis : Pauli, stride : Int) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="e8ac4-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e8ac4-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="e8ac4-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e8ac4-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e8ac4-108">O número de qubits agidos pela camada dada.</span><span class="sxs-lookup"><span data-stu-id="e8ac4-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="e8ac4-109">eixo : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="e8ac4-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="e8ac4-110">O eixo de rotação para cada rotação na camada dada.</span><span class="sxs-lookup"><span data-stu-id="e8ac4-110">The rotation axis for each rotation in the given layer.</span></span>


### <a name="stride--int"></a><span data-ttu-id="e8ac4-111">passo : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e8ac4-111">stride : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e8ac4-112">A separação entre os índices de alvo e de controlo para cada rotação.</span><span class="sxs-lookup"><span data-stu-id="e8ac4-112">The separation between the target and control indices for each rotation.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="e8ac4-113">Saída : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="e8ac4-113">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="e8ac4-114">Uma matriz de rotações controladas de dois qubits estabelecidas cíclicas através de um registo de `nQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="e8ac4-114">An array of two-qubit controlled rotations laid out cyclically across a register of `nQubits` qubits.</span></span>