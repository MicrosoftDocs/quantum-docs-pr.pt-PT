---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: Função CyclicEntanglingLayer
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 5d0af0a60217b69dc7eb8ece8952f2a7f0c09280
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847389"
---
# <a name="cyclicentanglinglayer-function"></a><span data-ttu-id="31963-102">Função CyclicEntanglingLayer</span><span class="sxs-lookup"><span data-stu-id="31963-102">CyclicEntanglingLayer function</span></span>

<span data-ttu-id="31963-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="31963-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="31963-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="31963-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="31963-105">Devolve uma série de rotações controladas ao longo de um determinado eixo, dispostas ciclicamente através de um registo de qubits, e parametrizadas por parâmetros de modelo distintos.</span><span class="sxs-lookup"><span data-stu-id="31963-105">Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.</span></span>

```qsharp
function CyclicEntanglingLayer (nQubits : Int, axis : Pauli, stride : Int) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="31963-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="31963-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="31963-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="31963-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="31963-108">O número de qubits agidos pela camada dada.</span><span class="sxs-lookup"><span data-stu-id="31963-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="31963-109">eixo : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="31963-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="31963-110">O eixo de rotação para cada rotação na camada dada.</span><span class="sxs-lookup"><span data-stu-id="31963-110">The rotation axis for each rotation in the given layer.</span></span>


### <a name="stride--int"></a><span data-ttu-id="31963-111">passo : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="31963-111">stride : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="31963-112">A separação entre os índices de alvo e de controlo para cada rotação.</span><span class="sxs-lookup"><span data-stu-id="31963-112">The separation between the target and control indices for each rotation.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="31963-113">Saída : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="31963-113">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="31963-114">Uma matriz de rotações controladas de dois qubits estabelecidas cíclicas através de um registo de `nQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="31963-114">An array of two-qubit controlled rotations laid out cyclically across a register of `nQubits` qubits.</span></span>

## <a name="example"></a><span data-ttu-id="31963-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="31963-115">Example</span></span>

<span data-ttu-id="31963-116">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="31963-116">The following are equivalent:</span></span>

```qsharp
let layer = CyclicEntanglingLayer(3, PauliX, 2);
let layer = [
    ControlledRotation((0, [2]), PauliX, 0),
    ControlledRotation((1, [0]), PauliX, 1),
    ControlledRotation((2, [1]), PauliX, 2)
];
```