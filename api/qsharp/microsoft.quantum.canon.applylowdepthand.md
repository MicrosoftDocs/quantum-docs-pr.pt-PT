---
uid: Microsoft.Quantum.Canon.ApplyLowDepthAnd
title: AplicarDeptheoperação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyLowDepthAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.
ms.openlocfilehash: 7fa9d9bf2f1905bf1b59e783d7bceb8cb2e09fa4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841708"
---
# <a name="applylowdepthand-operation"></a><span data-ttu-id="f7ebc-102">AplicarDeptheoperação</span><span class="sxs-lookup"><span data-stu-id="f7ebc-102">ApplyLowDepthAnd operation</span></span>

<span data-ttu-id="f7ebc-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f7ebc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f7ebc-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f7ebc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f7ebc-105">Inverte um dado qubit de alvo se e somente se ambos os qubits de controlo estiverem no estado 1, com profundidade T 1, utilizando a medição para efetuar a operação adjacente.</span><span class="sxs-lookup"><span data-stu-id="f7ebc-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyLowDepthAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="f7ebc-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="f7ebc-106">Description</span></span>

<span data-ttu-id="f7ebc-107">Inverta `target` se e somente se ambos os controlos forem 1, mas assume que `target` está no estado 0.</span><span class="sxs-lookup"><span data-stu-id="f7ebc-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="f7ebc-108">A operação tem contagem T 4, profundidade T 1 e requer um qubit de ajudante, podendo, portanto, ser preferível a uma operação CCNOT, se `target` se sabe que é 0.</span><span class="sxs-lookup"><span data-stu-id="f7ebc-108">The operation has T-count 4, T-depth 1 and requires one helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="f7ebc-109">O adjacente desta operação é baseado em medição e não requer portões T, e nenhum qubit ajudante.</span><span class="sxs-lookup"><span data-stu-id="f7ebc-109">The adjoint of this operation is measurement based and requires no T gates, and no helper qubit.</span></span>

## <a name="input"></a><span data-ttu-id="f7ebc-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="f7ebc-110">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="f7ebc-111">controle1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f7ebc-111">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f7ebc-112">Primeiro qubit de controlo</span><span class="sxs-lookup"><span data-stu-id="f7ebc-112">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="f7ebc-113">controlo2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f7ebc-113">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f7ebc-114">Segundo qubit de controlo</span><span class="sxs-lookup"><span data-stu-id="f7ebc-114">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="f7ebc-115">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f7ebc-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f7ebc-116">Qubit auxiliar de destino; deve estar no estado 0</span><span class="sxs-lookup"><span data-stu-id="f7ebc-116">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="f7ebc-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f7ebc-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="f7ebc-118">Referências</span><span class="sxs-lookup"><span data-stu-id="f7ebc-118">References</span></span>

- <span data-ttu-id="f7ebc-119">Cody Jones: "Novas construções para o portão toffoli tolerante a falhas", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span><span class="sxs-lookup"><span data-stu-id="f7ebc-119">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="f7ebc-120">Peter Selinger: "Circuitos quânticos de profundidade T um", Phys. Rev. A 87, 042302, 2013 [arXiv:1210.0974](https://arxiv.org/abs/1210.0974) doi:10.1103/PhysRevA.87.042302</span><span class="sxs-lookup"><span data-stu-id="f7ebc-120">Peter Selinger: "Quantum circuits of T-depth one", Phys. Rev. A 87, 042302, 2013 [arXiv:1210.0974](https://arxiv.org/abs/1210.0974) doi:10.1103/PhysRevA.87.042302</span></span>