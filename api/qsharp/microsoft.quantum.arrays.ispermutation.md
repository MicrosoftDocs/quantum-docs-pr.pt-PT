---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Função IsPermutation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 361bb21bedc725c25a1f3dfc811e9cfda4cb45ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719110"
---
# <a name="ispermutation-function"></a><span data-ttu-id="e20be-102">Função IsPermutation</span><span class="sxs-lookup"><span data-stu-id="e20be-102">IsPermutation function</span></span>

<span data-ttu-id="e20be-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e20be-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e20be-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e20be-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e20be-105">Saídas verdadeiras se e somente se uma determinada matriz representar uma permutação.</span><span class="sxs-lookup"><span data-stu-id="e20be-105">Outputs true if and only if a given array represents a permutation.</span></span>

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a><span data-ttu-id="e20be-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="e20be-106">Description</span></span>

<span data-ttu-id="e20be-107">Dada uma matriz `array` de `n` comprimento, retorna verdadeira se e somente se cada inteiro de `0` aparecer `n - 1` exatamente uma vez dentro , tal que `array` pode ser interpretado como uma `array` permutação em `n` elementos.</span><span class="sxs-lookup"><span data-stu-id="e20be-107">Given an array `array` of length `n`, returns true if and only if each integer from `0` to `n - 1` appears exactly once in `array`, such that `array` can be interpreted as a permutation on `n` elements.</span></span>

## <a name="input"></a><span data-ttu-id="e20be-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="e20be-108">Input</span></span>

### <a name="permuation--int"></a><span data-ttu-id="e20be-109">permutação : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e20be-109">permuation : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e20be-110">Uma matriz que pode ou não representar uma permutação.</span><span class="sxs-lookup"><span data-stu-id="e20be-110">An array that may or may not represent a permutation.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e20be-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e20be-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="remarks"></a><span data-ttu-id="e20be-112">Observações</span><span class="sxs-lookup"><span data-stu-id="e20be-112">Remarks</span></span>

<span data-ttu-id="e20be-113">Uma matriz de comprimento zero é trivialmente uma permutação.</span><span class="sxs-lookup"><span data-stu-id="e20be-113">An array of length zero is trivially a permutation.</span></span>