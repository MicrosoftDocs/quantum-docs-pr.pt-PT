---
uid: Microsoft.Quantum.MachineLearning.LocalRotationsLayer
title: Função LocalRotationsLayer
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LocalRotationsLayer
qsharp.summary: Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.
ms.openlocfilehash: 1549f24427f19bacbadf72e00c1c0181b64bcb73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211734"
---
# <a name="localrotationslayer-function"></a><span data-ttu-id="12f67-102">Função LocalRotationsLayer</span><span class="sxs-lookup"><span data-stu-id="12f67-102">LocalRotationsLayer function</span></span>

<span data-ttu-id="12f67-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="12f67-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="12f67-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="12f67-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="12f67-105">Devolve uma matriz de rotações descontroladas (single-qubit) ao longo de um determinado eixo, com uma rotação para cada qubit num registo, parametrizada por parâmetros de modelo distintos.</span><span class="sxs-lookup"><span data-stu-id="12f67-105">Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.</span></span>

```qsharp
function LocalRotationsLayer (nQubits : Int, axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="12f67-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="12f67-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="12f67-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="12f67-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="12f67-108">O número de qubits agidos pela camada dada.</span><span class="sxs-lookup"><span data-stu-id="12f67-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="12f67-109">eixo : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="12f67-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="12f67-110">O eixo de rotação para cada rotação na camada dada.</span><span class="sxs-lookup"><span data-stu-id="12f67-110">The rotation axis for each rotation in the given layer.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="12f67-111">Saída : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="12f67-111">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="12f67-112">Uma matriz de rotações controladas sobre o eixo dado, uma em cada um dos `nQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="12f67-112">An array of controlled rotations about the given axis, one on each of `nQubits` qubits.</span></span>