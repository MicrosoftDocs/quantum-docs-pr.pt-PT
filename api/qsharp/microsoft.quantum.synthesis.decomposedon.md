---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: Função decompostaOn
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: fb7aa5af8f3eb07399e0d2dd2d50723f4e6b169a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855517"
---
# <a name="decomposedon-function"></a><span data-ttu-id="1be41-102">Função decompostaOn</span><span class="sxs-lookup"><span data-stu-id="1be41-102">DecomposedOn function</span></span>

<span data-ttu-id="1be41-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="1be41-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="1be41-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1be41-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1be41-105">Decompõe-se uma permutação numa variável</span><span class="sxs-lookup"><span data-stu-id="1be41-105">Decomposes a permutation on a variable</span></span>

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a><span data-ttu-id="1be41-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="1be41-106">Description</span></span>

<span data-ttu-id="1be41-107">Dada uma permutação $\pi$ `perm` e um índice $i$ ( ), este método devolve três `index` permutações $(\pi_l, \pi_r), \pi')$ de tal forma que as imagens de $\pi_l$ e $\pi_r$ não mudam bits nos seus elementos em índices que não $i$ e imagens de $\pi'$ não mudam um pouco $i$ nos seus elementos.</span><span class="sxs-lookup"><span data-stu-id="1be41-107">Given a permutation $\pi$ (`perm`) and an index $i$ (`index`), this method returns three permutations $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>

## <a name="input"></a><span data-ttu-id="1be41-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="1be41-108">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="1be41-109">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="1be41-109">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="index--int"></a><span data-ttu-id="1be41-110">índice : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1be41-110">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--intintint"></a><span data-ttu-id="1be41-111">Saída :[(Int](xref:microsoft.quantum.lang-ref.int)[],[Int](xref:microsoft.quantum.lang-ref.int)[],[Int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="1be41-111">Output : (([Int](xref:microsoft.quantum.lang-ref.int)[],[Int](xref:microsoft.quantum.lang-ref.int)[]),[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>



## <a name="example"></a><span data-ttu-id="1be41-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="1be41-112">Example</span></span>

<span data-ttu-id="1be41-113">Suponha que a entrada é perm = [0, 2, 3, 5, 7, 1, 4, 6] e índice = 0, então esta função calcula três permutações com base na tabela seguinte, que lista a permutação `perm` na notação binária com elementos do grupo A e imagens do grupo D.  As colunas listam os índices de bits.</span><span class="sxs-lookup"><span data-stu-id="1be41-113">Assume that the input is perm = [0, 2, 3, 5, 7, 1, 4, 6] and index = 0, then this function computes three permutations based on the following table, which lists the permutation `perm` in binary notation with elements in group A and images in group D.  The columns list the bit indices.</span></span>

<span data-ttu-id="1be41-114">|   Um |   B |   C |   D |</span><span class="sxs-lookup"><span data-stu-id="1be41-114">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="1be41-115">2 1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-115">2 1 0</span></span> | <span data-ttu-id="1be41-116">2 1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-116">2 1 0</span></span> | <span data-ttu-id="1be41-117">2 1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-117">2 1 0</span></span> | <span data-ttu-id="1be41-118">2 1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-118">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="1be41-119">0 0 0</span><span class="sxs-lookup"><span data-stu-id="1be41-119">0 0 0</span></span> |       |       | <span data-ttu-id="1be41-120">0 0 0</span><span class="sxs-lookup"><span data-stu-id="1be41-120">0 0 0</span></span> | <span data-ttu-id="1be41-121">0</span><span class="sxs-lookup"><span data-stu-id="1be41-121">0</span></span>
| <span data-ttu-id="1be41-122">0 0 1</span><span class="sxs-lookup"><span data-stu-id="1be41-122">0 0 1</span></span> |       |       | <span data-ttu-id="1be41-123">0 1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-123">0 1 0</span></span> | <span data-ttu-id="1be41-124">2</span><span class="sxs-lookup"><span data-stu-id="1be41-124">2</span></span>
| <span data-ttu-id="1be41-125">0 1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-125">0 1 0</span></span> |       |       | <span data-ttu-id="1be41-126">0 1 1</span><span class="sxs-lookup"><span data-stu-id="1be41-126">0 1 1</span></span> | <span data-ttu-id="1be41-127">3</span><span class="sxs-lookup"><span data-stu-id="1be41-127">3</span></span>
| <span data-ttu-id="1be41-128">0 1 1</span><span class="sxs-lookup"><span data-stu-id="1be41-128">0 1 1</span></span> |       |       | <span data-ttu-id="1be41-129">1 0 1</span><span class="sxs-lookup"><span data-stu-id="1be41-129">1 0 1</span></span> | <span data-ttu-id="1be41-130">5</span><span class="sxs-lookup"><span data-stu-id="1be41-130">5</span></span>
| <span data-ttu-id="1be41-131">1 0 0</span><span class="sxs-lookup"><span data-stu-id="1be41-131">1 0 0</span></span> |       |       | <span data-ttu-id="1be41-132">1 1 1</span><span class="sxs-lookup"><span data-stu-id="1be41-132">1 1 1</span></span> | <span data-ttu-id="1be41-133">7</span><span class="sxs-lookup"><span data-stu-id="1be41-133">7</span></span>
| <span data-ttu-id="1be41-134">1 0 1</span><span class="sxs-lookup"><span data-stu-id="1be41-134">1 0 1</span></span> |       |       | <span data-ttu-id="1be41-135">0 0 1</span><span class="sxs-lookup"><span data-stu-id="1be41-135">0 0 1</span></span> | <span data-ttu-id="1be41-136">1</span><span class="sxs-lookup"><span data-stu-id="1be41-136">1</span></span>
| <span data-ttu-id="1be41-137">1 1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-137">1 1 0</span></span> |       |       | <span data-ttu-id="1be41-138">1 0 0</span><span class="sxs-lookup"><span data-stu-id="1be41-138">1 0 0</span></span> | <span data-ttu-id="1be41-139">4</span><span class="sxs-lookup"><span data-stu-id="1be41-139">4</span></span>
| <span data-ttu-id="1be41-140">1 1 1</span><span class="sxs-lookup"><span data-stu-id="1be41-140">1 1 1</span></span> |       |       | <span data-ttu-id="1be41-141">1 1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-141">1 1 0</span></span> | <span data-ttu-id="1be41-142">6</span><span class="sxs-lookup"><span data-stu-id="1be41-142">6</span></span>

<span data-ttu-id="1be41-143">Todos os valores para índices não iguais a 0 (= índice) são copiados de A a B e de D a C.</span><span class="sxs-lookup"><span data-stu-id="1be41-143">All values for indices not equal to 0 (= index) are copied from A to B and from D to C.</span></span>

<span data-ttu-id="1be41-144">|   Um |   B |   C |   D |</span><span class="sxs-lookup"><span data-stu-id="1be41-144">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="1be41-145">2 1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-145">2 1 0</span></span> | <span data-ttu-id="1be41-146">2 1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-146">2 1 0</span></span> | <span data-ttu-id="1be41-147">2 1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-147">2 1 0</span></span> | <span data-ttu-id="1be41-148">2 1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-148">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="1be41-149">0 0 0</span><span class="sxs-lookup"><span data-stu-id="1be41-149">0 0 0</span></span> | <span data-ttu-id="1be41-150">0 0</span><span class="sxs-lookup"><span data-stu-id="1be41-150">0 0</span></span>   | <span data-ttu-id="1be41-151">0 0</span><span class="sxs-lookup"><span data-stu-id="1be41-151">0 0</span></span>   | <span data-ttu-id="1be41-152">0 0 0</span><span class="sxs-lookup"><span data-stu-id="1be41-152">0 0 0</span></span> |
| <span data-ttu-id="1be41-153">0 0 1</span><span class="sxs-lookup"><span data-stu-id="1be41-153">0 0 1</span></span> | <span data-ttu-id="1be41-154">0 0</span><span class="sxs-lookup"><span data-stu-id="1be41-154">0 0</span></span>   | <span data-ttu-id="1be41-155">0 1</span><span class="sxs-lookup"><span data-stu-id="1be41-155">0 1</span></span>   | <span data-ttu-id="1be41-156">0 1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-156">0 1 0</span></span> |
| <span data-ttu-id="1be41-157">0 1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-157">0 1 0</span></span> | <span data-ttu-id="1be41-158">0 1</span><span class="sxs-lookup"><span data-stu-id="1be41-158">0 1</span></span>   | <span data-ttu-id="1be41-159">0 1</span><span class="sxs-lookup"><span data-stu-id="1be41-159">0 1</span></span>   | <span data-ttu-id="1be41-160">0 1 1</span><span class="sxs-lookup"><span data-stu-id="1be41-160">0 1 1</span></span> |
| <span data-ttu-id="1be41-161">0 1 1</span><span class="sxs-lookup"><span data-stu-id="1be41-161">0 1 1</span></span> | <span data-ttu-id="1be41-162">0 1</span><span class="sxs-lookup"><span data-stu-id="1be41-162">0 1</span></span>   | <span data-ttu-id="1be41-163">1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-163">1 0</span></span>   | <span data-ttu-id="1be41-164">1 0 1</span><span class="sxs-lookup"><span data-stu-id="1be41-164">1 0 1</span></span> |
| <span data-ttu-id="1be41-165">1 0 0</span><span class="sxs-lookup"><span data-stu-id="1be41-165">1 0 0</span></span> | <span data-ttu-id="1be41-166">1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-166">1 0</span></span>   | <span data-ttu-id="1be41-167">1 1</span><span class="sxs-lookup"><span data-stu-id="1be41-167">1 1</span></span>   | <span data-ttu-id="1be41-168">1 1 1</span><span class="sxs-lookup"><span data-stu-id="1be41-168">1 1 1</span></span> |
| <span data-ttu-id="1be41-169">1 0 1</span><span class="sxs-lookup"><span data-stu-id="1be41-169">1 0 1</span></span> | <span data-ttu-id="1be41-170">1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-170">1 0</span></span>   | <span data-ttu-id="1be41-171">0 0</span><span class="sxs-lookup"><span data-stu-id="1be41-171">0 0</span></span>   | <span data-ttu-id="1be41-172">0 0 1</span><span class="sxs-lookup"><span data-stu-id="1be41-172">0 0 1</span></span> |
| <span data-ttu-id="1be41-173">1 1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-173">1 1 0</span></span> | <span data-ttu-id="1be41-174">1 1</span><span class="sxs-lookup"><span data-stu-id="1be41-174">1 1</span></span>   | <span data-ttu-id="1be41-175">1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-175">1 0</span></span>   | <span data-ttu-id="1be41-176">1 0 0</span><span class="sxs-lookup"><span data-stu-id="1be41-176">1 0 0</span></span> |
| <span data-ttu-id="1be41-177">1 1 1</span><span class="sxs-lookup"><span data-stu-id="1be41-177">1 1 1</span></span> | <span data-ttu-id="1be41-178">1 1</span><span class="sxs-lookup"><span data-stu-id="1be41-178">1 1</span></span>   | <span data-ttu-id="1be41-179">1 1</span><span class="sxs-lookup"><span data-stu-id="1be41-179">1 1</span></span>   | <span data-ttu-id="1be41-180">1 1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-180">1 1 0</span></span> |

<span data-ttu-id="1be41-181">Em seguida, um 0 é colocado para o primeiro elemento com um índice vazio na coluna 0 no bloco B e, em seguida, um 1 é colocado em B onde o prefixo corresponde (no primeiro caso a outra linha com índices 0 0).</span><span class="sxs-lookup"><span data-stu-id="1be41-181">Next a 0 is placed for the first element with an empty index at column 0 in block B and then a 1 is placed in B where the prefix matches (in the first case the other row with indices 0 0).</span></span>
<span data-ttu-id="1be41-182">Em seguida, um 1 é adicionado na mesma linha no bloco C, e em seguida um 0 para o prefixo correspondente no bloco C.  Este processo é repetido, até que todos os índices tenham sido colocados na coluna 0 nos blocos B e C.</span><span class="sxs-lookup"><span data-stu-id="1be41-182">Afterwards, a 1 is added in the same row in block C, and then a 0 for the corresponding prefix in block C.  This process is repeated, until all indices have been placed in column 0 in blocks B and C.</span></span>

<span data-ttu-id="1be41-183">|   Um |   B |   C |   D |</span><span class="sxs-lookup"><span data-stu-id="1be41-183">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="1be41-184">2 1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-184">2 1 0</span></span> | <span data-ttu-id="1be41-185">2 1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-185">2 1 0</span></span> | <span data-ttu-id="1be41-186">2 1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-186">2 1 0</span></span> | <span data-ttu-id="1be41-187">2 1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-187">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="1be41-188">0 0 0</span><span class="sxs-lookup"><span data-stu-id="1be41-188">0 0 0</span></span> | <span data-ttu-id="1be41-189">0 0 0</span><span class="sxs-lookup"><span data-stu-id="1be41-189">0 0 0</span></span> | <span data-ttu-id="1be41-190">0 0 0</span><span class="sxs-lookup"><span data-stu-id="1be41-190">0 0 0</span></span> | <span data-ttu-id="1be41-191">0 0 0</span><span class="sxs-lookup"><span data-stu-id="1be41-191">0 0 0</span></span> |
| <span data-ttu-id="1be41-192">0 0 1</span><span class="sxs-lookup"><span data-stu-id="1be41-192">0 0 1</span></span> | <span data-ttu-id="1be41-193">0 0 1</span><span class="sxs-lookup"><span data-stu-id="1be41-193">0 0 1</span></span> | <span data-ttu-id="1be41-194">0 1 1</span><span class="sxs-lookup"><span data-stu-id="1be41-194">0 1 1</span></span> | <span data-ttu-id="1be41-195">0 1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-195">0 1 0</span></span> |
| <span data-ttu-id="1be41-196">0 1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-196">0 1 0</span></span> | <span data-ttu-id="1be41-197">0 1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-197">0 1 0</span></span> | <span data-ttu-id="1be41-198">0 1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-198">0 1 0</span></span> | <span data-ttu-id="1be41-199">0 1 1</span><span class="sxs-lookup"><span data-stu-id="1be41-199">0 1 1</span></span> |
| <span data-ttu-id="1be41-200">0 1 1</span><span class="sxs-lookup"><span data-stu-id="1be41-200">0 1 1</span></span> | <span data-ttu-id="1be41-201">0 1 1</span><span class="sxs-lookup"><span data-stu-id="1be41-201">0 1 1</span></span> | <span data-ttu-id="1be41-202">1 0 1</span><span class="sxs-lookup"><span data-stu-id="1be41-202">1 0 1</span></span> | <span data-ttu-id="1be41-203">1 0 1</span><span class="sxs-lookup"><span data-stu-id="1be41-203">1 0 1</span></span> |
| <span data-ttu-id="1be41-204">1 0 0</span><span class="sxs-lookup"><span data-stu-id="1be41-204">1 0 0</span></span> | <span data-ttu-id="1be41-205">1 0 0</span><span class="sxs-lookup"><span data-stu-id="1be41-205">1 0 0</span></span> | <span data-ttu-id="1be41-206">1 1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-206">1 1 0</span></span> | <span data-ttu-id="1be41-207">1 1 1</span><span class="sxs-lookup"><span data-stu-id="1be41-207">1 1 1</span></span> |
| <span data-ttu-id="1be41-208">1 0 1</span><span class="sxs-lookup"><span data-stu-id="1be41-208">1 0 1</span></span> | <span data-ttu-id="1be41-209">1 0 1</span><span class="sxs-lookup"><span data-stu-id="1be41-209">1 0 1</span></span> | <span data-ttu-id="1be41-210">0 0 1</span><span class="sxs-lookup"><span data-stu-id="1be41-210">0 0 1</span></span> | <span data-ttu-id="1be41-211">0 0 1</span><span class="sxs-lookup"><span data-stu-id="1be41-211">0 0 1</span></span> |
| <span data-ttu-id="1be41-212">1 1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-212">1 1 0</span></span> | <span data-ttu-id="1be41-213">1 1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-213">1 1 0</span></span> | <span data-ttu-id="1be41-214">1 0 0</span><span class="sxs-lookup"><span data-stu-id="1be41-214">1 0 0</span></span> | <span data-ttu-id="1be41-215">1 0 0</span><span class="sxs-lookup"><span data-stu-id="1be41-215">1 0 0</span></span> |
| <span data-ttu-id="1be41-216">1 1 1</span><span class="sxs-lookup"><span data-stu-id="1be41-216">1 1 1</span></span> | <span data-ttu-id="1be41-217">1 1 1</span><span class="sxs-lookup"><span data-stu-id="1be41-217">1 1 1</span></span> | <span data-ttu-id="1be41-218">1 1 1</span><span class="sxs-lookup"><span data-stu-id="1be41-218">1 1 1</span></span> | <span data-ttu-id="1be41-219">1 1 0</span><span class="sxs-lookup"><span data-stu-id="1be41-219">1 1 0</span></span> |

<span data-ttu-id="1be41-220">Podemos ler três novas permutações da mesa:</span><span class="sxs-lookup"><span data-stu-id="1be41-220">We can read three new permutations from the table:</span></span>

- <span data-ttu-id="1be41-221">$\pi_l$ com elementos em A, imagens em B (à esquerda)</span><span class="sxs-lookup"><span data-stu-id="1be41-221">$\pi_l$ with elements in A, images in B (left)</span></span>
- <span data-ttu-id="1be41-222">$\pi_r$ com elementos em D, imagens em C (à direita)</span><span class="sxs-lookup"><span data-stu-id="1be41-222">$\pi_r$ with elements in D, images in C (right)</span></span>
- <span data-ttu-id="1be41-223">$\pi'$ com elementos em B, imagens em C (restante)</span><span class="sxs-lookup"><span data-stu-id="1be41-223">$\pi'$  with elements in B, images in C (remainder)</span></span>

<span data-ttu-id="1be41-224">Note que por design os valores dos bits não mudam em $\pi_l$ e $\pi_r$ para os índices 1 e 2, e os valores de bit não mudam para $\pi_'$ para índice 0.</span><span class="sxs-lookup"><span data-stu-id="1be41-224">Note that by design bit values do not change in $\pi_l$ and $\pi_r$ for indices 1 and 2, and bit values do not change for in $\pi_'$ for index 0.</span></span>  <span data-ttu-id="1be41-225">Note também que $\pi_l$ e $\pi_r$ devem ser auto-inversos.</span><span class="sxs-lookup"><span data-stu-id="1be41-225">Also note that $\pi_l$ and $\pi_r$ must be self-inverse.</span></span>

<span data-ttu-id="1be41-226">As permutações derivadas e devolvidas são: esquerda = [0, 1, 2, 3, 4, 5, 6, 7] direita = [0, 1, 3, 2, 4, 5, 7, 6] restante = [0, 3, 2, 5, 6, 1, 4, 7]</span><span class="sxs-lookup"><span data-stu-id="1be41-226">The derived and returned permutations are: left      = [0, 1, 2, 3, 4, 5, 6, 7] right     = [0, 1, 3, 2, 4, 5, 7, 6] remainder = [0, 3, 2, 5, 6, 1, 4, 7]</span></span>