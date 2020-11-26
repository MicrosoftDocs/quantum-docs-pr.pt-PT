---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: Tipo definido pelo utilizador controlledRotation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: 1e664b470caeba656ea4a73f70bbc0ef5fe76f7e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196570"
---
# <a name="controlledrotation-user-defined-type"></a><span data-ttu-id="0fd6a-102">Tipo definido pelo utilizador controlledRotation</span><span class="sxs-lookup"><span data-stu-id="0fd6a-102">ControlledRotation user defined type</span></span>

<span data-ttu-id="0fd6a-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="0fd6a-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="0fd6a-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="0fd6a-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="0fd6a-105">Descreve uma rotação controlada em termos dos seus índices de alvo e controlo, eixo de rotação e índice num vetor de parâmetros de modelo.</span><span class="sxs-lookup"><span data-stu-id="0fd6a-105">Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.</span></span>

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a><span data-ttu-id="0fd6a-106">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="0fd6a-106">Named Items</span></span>

### <a name="targetindex--int"></a><span data-ttu-id="0fd6a-107">TargetIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0fd6a-107">TargetIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0fd6a-108">Índice do qubit alvo para esta rotação controlada.</span><span class="sxs-lookup"><span data-stu-id="0fd6a-108">Index of the target qubit for this controlled rotation.</span></span>
### <a name="controlindices--int"></a><span data-ttu-id="0fd6a-109">ControlIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0fd6a-109">ControlIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0fd6a-110">Uma matriz dos índices de qubit de controlo para esta rotação.</span><span class="sxs-lookup"><span data-stu-id="0fd6a-110">An array of the control qubit indices for this rotation.</span></span>
### <a name="axis--pauli"></a><span data-ttu-id="0fd6a-111">Eixo : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="0fd6a-111">Axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="0fd6a-112">O eixo para esta rotação.</span><span class="sxs-lookup"><span data-stu-id="0fd6a-112">The axis for this rotation.</span></span>
### <a name="parameterindex--int"></a><span data-ttu-id="0fd6a-113">ParâmetroIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0fd6a-113">ParameterIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0fd6a-114">Um índice em um vetor de parâmetro modelo descrevendo o ângulo para esta rotação.</span><span class="sxs-lookup"><span data-stu-id="0fd6a-114">An index into a model parameter vector describing the angle for this rotation.</span></span>

## <a name="remarks"></a><span data-ttu-id="0fd6a-115">Observações</span><span class="sxs-lookup"><span data-stu-id="0fd6a-115">Remarks</span></span>

<span data-ttu-id="0fd6a-116">Uma rotação descontrolada pode ser representada por `ControlIndices` uma matriz vazia de índices, `new Int[0]` .</span><span class="sxs-lookup"><span data-stu-id="0fd6a-116">An uncontrolled rotation can be represented by setting `ControlIndices` to an empty array of indexes, `new Int[0]`.</span></span>