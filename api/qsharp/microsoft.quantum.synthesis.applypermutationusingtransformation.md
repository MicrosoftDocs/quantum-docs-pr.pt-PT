---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation
title: AplicaçãoPermutationUsingTransformation operation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingTransformation
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.
ms.openlocfilehash: a05b433eae2612bbf5c87522c4ef251976184aa8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192065"
---
# <a name="applypermutationusingtransformation-operation"></a><span data-ttu-id="8b983-102">AplicaçãoPermutationUsingTransformation operation</span><span class="sxs-lookup"><span data-stu-id="8b983-102">ApplyPermutationUsingTransformation operation</span></span>

<span data-ttu-id="8b983-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="8b983-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="8b983-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8b983-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8b983-105">Permuta as amplitudes num estado quântico dada uma permutação usando a síntese baseada na transformação.</span><span class="sxs-lookup"><span data-stu-id="8b983-105">Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingTransformation (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="8b983-106">Description</span><span class="sxs-lookup"><span data-stu-id="8b983-106">Description</span></span>

<span data-ttu-id="8b983-107">Este procedimento implementa a abordagem de síntese baseada na transformação unidirecional.</span><span class="sxs-lookup"><span data-stu-id="8b983-107">This procedure implements the unidirectional transformation based synthesis approach.</span></span>  <span data-ttu-id="8b983-108">A entrada é uma permutação $\pi$ acima de $2^n$ elementos $ \{ 0, \dots, 2^n-1 \} $, o que representa uma função boolean reversível reversível $n$-variável.</span><span class="sxs-lookup"><span data-stu-id="8b983-108">Input is a permutation $\pi$ over $2^n$ elements $\{0, \dots, 2^n-1\}$, which represents an $n$-variable reversible Boolean function.</span></span>
<span data-ttu-id="8b983-109">O algoritmo executa iterativamente os seguintes passos:</span><span class="sxs-lookup"><span data-stu-id="8b983-109">The algorithm performs iteratively the following steps:</span></span>

1. <span data-ttu-id="8b983-110">Encontre o menor $x$ de tal forma que $x \ne \pi(x) = y$.</span><span class="sxs-lookup"><span data-stu-id="8b983-110">Find smallest $x$ such that $x \ne \pi(x) = y$.</span></span>
2. <span data-ttu-id="8b983-111">Encontre operações Toffoli com vários controlos, que se aplicam às saídas fazem $\pi(x) = x$ e não mudem $\pi(x')$ para todos os $x' < x$</span><span class="sxs-lookup"><span data-stu-id="8b983-111">Find multiple-controlled Toffoli operations, which applied to the outputs make $\pi(x) = x$ and do not change $\pi(x')$ for all $x' < x$</span></span>

## <a name="input"></a><span data-ttu-id="8b983-112">Entrada</span><span class="sxs-lookup"><span data-stu-id="8b983-112">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="8b983-113">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8b983-113">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="8b983-114">Uma permutação de elementos de $2^n$ a partir de 0.</span><span class="sxs-lookup"><span data-stu-id="8b983-114">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="8b983-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8b983-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="8b983-116">Uma lista de $n$ qubits aos quais a permutação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="8b983-116">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8b983-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8b983-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="8b983-118">Referências</span><span class="sxs-lookup"><span data-stu-id="8b983-118">References</span></span>

- [<span data-ttu-id="8b983-119">*D. Michael Miller*, *Dmitri Maslov*, *Gerhard W. Dueck,* Proc. DAC 2003, IEEE, pp. 318-323, 2003</span><span class="sxs-lookup"><span data-stu-id="8b983-119">*D. Michael Miller*, *Dmitri Maslov*, *Gerhard W. Dueck*, Proc. DAC 2003, IEEE, pp. 318-323, 2003</span></span>](https://doi.org/10.1145/775832.775915)
- [<span data-ttu-id="8b983-120">*Mathias Soeken*, *Gerhard W. Dueck*, *D. Michael Miller*, Proc. RC 2016, Springer, pp. 307-321, 2016</span><span class="sxs-lookup"><span data-stu-id="8b983-120">*Mathias Soeken*, *Gerhard W. Dueck*, *D. Michael Miller*, Proc. RC 2016, Springer, pp. 307-321, 2016</span></span>](https://doi.org/10.1007/978-3-319-40578-0_22)

## <a name="see-also"></a><span data-ttu-id="8b983-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8b983-121">See Also</span></span>

- [<span data-ttu-id="8b983-122">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span><span class="sxs-lookup"><span data-stu-id="8b983-122">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)