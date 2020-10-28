---
uid: Microsoft.Quantum.Canon.ApplyAnd
title: Aplicar E operar
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.
ms.openlocfilehash: 5a4e18cb0361708e1fc00e8d62c0a6c2415d6bed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718462"
---
# <a name="applyand-operation"></a><span data-ttu-id="3730e-102">Aplicar E operar</span><span class="sxs-lookup"><span data-stu-id="3730e-102">ApplyAnd operation</span></span>

<span data-ttu-id="3730e-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3730e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3730e-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3730e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3730e-105">Inverte um determinado qubit de alvo se e somente se ambos os qubits de controlo estiverem no estado 1, utilizando a medição para efetuar a operação adjacente.</span><span class="sxs-lookup"><span data-stu-id="3730e-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="3730e-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="3730e-106">Description</span></span>

<span data-ttu-id="3730e-107">Inverta `target` se e somente se ambos os controlos forem 1, mas assume que `target` está no estado 0.</span><span class="sxs-lookup"><span data-stu-id="3730e-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="3730e-108">A operação tem a contagem T 4, a profundidade T 2 e não requer nenhum qubit de ajudante, podendo, portanto, ser preferível a uma operação CCNOT, se `target` se sabe que é 0.</span><span class="sxs-lookup"><span data-stu-id="3730e-108">The operation has T-count 4, T-depth 2 and requires no helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="3730e-109">O adjacente desta operação é baseado em medição e não requer portões T.</span><span class="sxs-lookup"><span data-stu-id="3730e-109">The adjoint of this operation is measurement based and requires no T gates.</span></span>

<span data-ttu-id="3730e-110">A aplicação controlada desta operação não requer qubit, `2^c` `Rz` portões e não está otimizado para profundidade, onde `c` está o número de qubits de controlo geral, incluindo os dois controlos da `ApplyAnd` operação.</span><span class="sxs-lookup"><span data-stu-id="3730e-110">The controlled application of this operation requires no helper qubit, `2^c` `Rz` gates and is not optimized for depth, where `c` is the number of overall control qubits including the two controls from the `ApplyAnd` operation.</span></span>  <span data-ttu-id="3730e-111">A aplicação controlada adjacente requer `2^c - 1` `Rz` portões (com um ângulo duas vezes maior do que a operação não adjacente), nenhum qubit de ajudante e não está otimizado para profundidade.</span><span class="sxs-lookup"><span data-stu-id="3730e-111">The adjoint controlled application requires `2^c - 1` `Rz` gates (with an angle twice the size of the non-adjoint operation), no helper qubit and is not optimized for depth.</span></span>

## <a name="input"></a><span data-ttu-id="3730e-112">Entrada</span><span class="sxs-lookup"><span data-stu-id="3730e-112">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="3730e-113">controle1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3730e-113">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3730e-114">Primeiro qubit de controlo</span><span class="sxs-lookup"><span data-stu-id="3730e-114">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="3730e-115">controlo2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3730e-115">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3730e-116">Segundo qubit de controlo</span><span class="sxs-lookup"><span data-stu-id="3730e-116">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="3730e-117">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3730e-117">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3730e-118">Qubit auxiliar de destino; deve estar no estado 0</span><span class="sxs-lookup"><span data-stu-id="3730e-118">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="3730e-119">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3730e-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="3730e-120">Referências</span><span class="sxs-lookup"><span data-stu-id="3730e-120">References</span></span>

- <span data-ttu-id="3730e-121">Cody Jones: "Novas construções para o portão toffoli tolerante a falhas", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span><span class="sxs-lookup"><span data-stu-id="3730e-121">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="3730e-122">Craig Gidney: "Reduzir para metade o custo da adição quântica", Quantum 2, página 74, 2018 [arXiv:1709.06648](https://arxiv.org/abs/1709.06648) doi:10.1103/PhysRevA.85.044302</span><span class="sxs-lookup"><span data-stu-id="3730e-122">Craig Gidney: "Halving the cost of quantum addition", Quantum 2, page 74, 2018 [arXiv:1709.06648](https://arxiv.org/abs/1709.06648) doi:10.1103/PhysRevA.85.044302</span></span>
- <span data-ttu-id="3730e-123">Mathias Soeken: "Circuitos Quânticos do Oráculo e o Padrão da Árvore de Natal", [artigo de blog de 19 de dezembro de 2019](https://msoeken.github.io/blog_qac.html) (nota: explica a construção múltipla controlada)</span><span class="sxs-lookup"><span data-stu-id="3730e-123">Mathias Soeken: "Quantum Oracle Circuits and the Christmas Tree Pattern", [Blog article from December 19, 2019](https://msoeken.github.io/blog_qac.html) (note: explains the multiple controlled construction)</span></span>