---
uid: Microsoft.Quantum.Canon.ApplyLowDepthAnd
title: AplicarDeptheoperação
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyLowDepthAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.
ms.openlocfilehash: 4c5e381227bf82415121add38d0c0d2959fb529d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209320"
---
# <a name="applylowdepthand-operation"></a><span data-ttu-id="175fe-102">AplicarDeptheoperação</span><span class="sxs-lookup"><span data-stu-id="175fe-102">ApplyLowDepthAnd operation</span></span>

<span data-ttu-id="175fe-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="175fe-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="175fe-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="175fe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="175fe-105">Inverte um dado qubit de alvo se e somente se ambos os qubits de controlo estiverem no estado 1, com profundidade T 1, utilizando a medição para efetuar a operação adjacente.</span><span class="sxs-lookup"><span data-stu-id="175fe-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyLowDepthAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="175fe-106">Description</span><span class="sxs-lookup"><span data-stu-id="175fe-106">Description</span></span>

<span data-ttu-id="175fe-107">Inverta `target` se e somente se ambos os controlos forem 1, mas assume que `target` está no estado 0.</span><span class="sxs-lookup"><span data-stu-id="175fe-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="175fe-108">A operação tem contagem T 4, profundidade T 1 e requer um qubit de ajudante, podendo, portanto, ser preferível a uma operação CCNOT, se `target` se sabe que é 0.</span><span class="sxs-lookup"><span data-stu-id="175fe-108">The operation has T-count 4, T-depth 1 and requires one helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="175fe-109">O adjacente desta operação é baseado em medição e não requer portões T, e nenhum qubit ajudante.</span><span class="sxs-lookup"><span data-stu-id="175fe-109">The adjoint of this operation is measurement based and requires no T gates, and no helper qubit.</span></span>

## <a name="input"></a><span data-ttu-id="175fe-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="175fe-110">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="175fe-111">controle1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="175fe-111">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="175fe-112">Primeiro qubit de controlo</span><span class="sxs-lookup"><span data-stu-id="175fe-112">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="175fe-113">controlo2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="175fe-113">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="175fe-114">Segundo qubit de controlo</span><span class="sxs-lookup"><span data-stu-id="175fe-114">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="175fe-115">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="175fe-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="175fe-116">Qubit auxiliar de destino; deve estar no estado 0</span><span class="sxs-lookup"><span data-stu-id="175fe-116">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="175fe-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="175fe-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="175fe-118">Referências</span><span class="sxs-lookup"><span data-stu-id="175fe-118">References</span></span>

- <span data-ttu-id="175fe-119">Cody Jones: "Novas construções para o portão toffoli tolerante a falhas", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span><span class="sxs-lookup"><span data-stu-id="175fe-119">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="175fe-120">Peter Selinger: "Circuitos quânticos de profundidade T um", Phys. Rev. A 87, 042302, 2013 [arXiv:1210.0974](https://arxiv.org/abs/1210.0974) doi:10.1103/PhysRevA.87.042302</span><span class="sxs-lookup"><span data-stu-id="175fe-120">Peter Selinger: "Quantum circuits of T-depth one", Phys. Rev. A 87, 042302, 2013 [arXiv:1210.0974](https://arxiv.org/abs/1210.0974) doi:10.1103/PhysRevA.87.042302</span></span>