---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition
title: AplicaçãoPermutationSingDecomposition operação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecomposition
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 40b51807da155c57c3fa8d740eff28ceef0a0ffc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725315"
---
# <a name="applypermutationusingdecomposition-operation"></a><span data-ttu-id="93884-102">AplicaçãoPermutationSingDecomposition operação</span><span class="sxs-lookup"><span data-stu-id="93884-102">ApplyPermutationUsingDecomposition operation</span></span>

<span data-ttu-id="93884-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="93884-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="93884-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="93884-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="93884-105">Permuta as amplitudes num estado quântico dada uma permutação usando a síntese baseada na decomposição.</span><span class="sxs-lookup"><span data-stu-id="93884-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecomposition (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="93884-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="93884-106">Description</span></span>

<span data-ttu-id="93884-107">Este procedimento implementa a abordagem da síntese baseada na decomposição.</span><span class="sxs-lookup"><span data-stu-id="93884-107">This procedure implements the decomposition based synthesis approach.</span></span>  <span data-ttu-id="93884-108">A entrada é uma permutação $\pi$ acima de $2^n$ elementos $ \{ 0, \dots, 2^n-1 \} $, o que representa uma função booleana reversível reversível $n$-variável.</span><span class="sxs-lookup"><span data-stu-id="93884-108">The input is a permutation $\pi$ over $2^n$ elements $\{0, \dots, 2^n-1\}$, which represents an $n$-variable reversible Boolean function.</span></span>
<span data-ttu-id="93884-109">O algoritmo executa iterativamente os seguintes passos para cada índice variável $i$:</span><span class="sxs-lookup"><span data-stu-id="93884-109">The algorithm iteratively performs the following steps for each variable index $i$:</span></span>

1. <span data-ttu-id="93884-110">Computação $((\pi_l, \pi_r), \pi')$ de tal forma que as imagens de $\pi_l$ e $\pi_r$ não mudam bits nos seus elementos em índices que não $i$ e imagens de $\pi'$ não mudam um pouco $i$ nos seus elementos.</span><span class="sxs-lookup"><span data-stu-id="93884-110">Compute $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>
2. <span data-ttu-id="93884-111">Desacorra $\pi \leftarrow \pi'$, e obtém tabelas de verdade de $\pi_l$ e $\pi_r$ com base em elementos que não são pontos fixos.</span><span class="sxs-lookup"><span data-stu-id="93884-111">Set $\pi \leftarrow \pi'$, and derive truth tables from $\pi_l$ and $\pi_r$ based on elements that are not fixed-points.</span></span>

<span data-ttu-id="93884-112">Após a aplicação destes passos para todos os índices variáveis, a permutação restante $\pi$ será a identidade, e com base nas tabelas e índices de verdade recolhidos, pode-se aplicar operações controladas pela tabela da verdade @"microsoft.quantum.intrinsic.x" usando a @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" operação.</span><span class="sxs-lookup"><span data-stu-id="93884-112">After applying these steps for all variable indexes, the remaining permutation $\pi$ will be the identity, and based on the collected truth tables and indexes, one can apply truth-table controlled @"microsoft.quantum.intrinsic.x" operations using the @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" operation.</span></span>

<span data-ttu-id="93884-113">A ordem variável é $0, \pontos, n - 1$.</span><span class="sxs-lookup"><span data-stu-id="93884-113">The variable order is $0, \dots, n - 1$.</span></span>  <span data-ttu-id="93884-114">Uma ordem variável personalizada pode ser especificada na operação @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder" .</span><span class="sxs-lookup"><span data-stu-id="93884-114">A custom variable order can be specified in the operation @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder".</span></span>

## <a name="input"></a><span data-ttu-id="93884-115">Entrada</span><span class="sxs-lookup"><span data-stu-id="93884-115">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="93884-116">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="93884-116">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="93884-117">Uma permutação de elementos de $2^n$ a partir de 0.</span><span class="sxs-lookup"><span data-stu-id="93884-117">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="93884-118">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="93884-118">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="93884-119">Uma lista de $n$ qubits aos quais a permutação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="93884-119">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="93884-120">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="93884-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="93884-121">Referências</span><span class="sxs-lookup"><span data-stu-id="93884-121">References</span></span>

- [<span data-ttu-id="93884-122">*Alexis De Vos* , *Yvan Van Rentergem* , Adv. em Matemática.</span><span class="sxs-lookup"><span data-stu-id="93884-122">*Alexis De Vos* , *Yvan Van Rentergem* , Adv. in Math. of Comm. 2(2), 2008, pp. 183--200</span></span>](http://www.aimsciences.org/article/doi/10.3934/amc.2008.2.183)
- [<span data-ttu-id="93884-123">*Mathias Soeken* , *Laura Tague* , *Gerhard W. Dueck,* *Rolf Drechsler* , Journal of Symbolic Computation 73 (2016), pp. 1--26</span><span class="sxs-lookup"><span data-stu-id="93884-123">*Mathias Soeken* , *Laura Tague* , *Gerhard W. Dueck* , *Rolf Drechsler* , Journal of Symbolic Computation 73 (2016), pp. 1--26</span></span>](https://www.sciencedirect.com/science/article/pii/S0747717115000188?via%3Dihub)

## <a name="see-also"></a><span data-ttu-id="93884-124">Consulte também</span><span class="sxs-lookup"><span data-stu-id="93884-124">See Also</span></span>

- [<span data-ttu-id="93884-125">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder</span><span class="sxs-lookup"><span data-stu-id="93884-125">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder)
- [<span data-ttu-id="93884-126">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span><span class="sxs-lookup"><span data-stu-id="93884-126">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)