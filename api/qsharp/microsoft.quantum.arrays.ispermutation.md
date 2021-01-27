---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Função IsPermutation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 7e563650f33b0292e1e41f629829a2d3b9e5fd28
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848103"
---
# <a name="ispermutation-function"></a><span data-ttu-id="a5243-102">Função IsPermutation</span><span class="sxs-lookup"><span data-stu-id="a5243-102">IsPermutation function</span></span>

<span data-ttu-id="a5243-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a5243-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a5243-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a5243-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a5243-105">Saídas verdadeiras se e somente se uma determinada matriz representar uma permutação.</span><span class="sxs-lookup"><span data-stu-id="a5243-105">Outputs true if and only if a given array represents a permutation.</span></span>

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a><span data-ttu-id="a5243-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="a5243-106">Description</span></span>

<span data-ttu-id="a5243-107">Dada uma matriz `array` de `n` comprimento, retorna verdadeira se e somente se cada inteiro de `0` aparecer `n - 1` exatamente uma vez dentro , tal que `array` pode ser interpretado como uma `array` permutação em `n` elementos.</span><span class="sxs-lookup"><span data-stu-id="a5243-107">Given an array `array` of length `n`, returns true if and only if each integer from `0` to `n - 1` appears exactly once in `array`, such that `array` can be interpreted as a permutation on `n` elements.</span></span>

## <a name="input"></a><span data-ttu-id="a5243-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="a5243-108">Input</span></span>

### <a name="permuation--int"></a><span data-ttu-id="a5243-109">permutação : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a5243-109">permuation : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a5243-110">Uma matriz que pode ou não representar uma permutação.</span><span class="sxs-lookup"><span data-stu-id="a5243-110">An array that may or may not represent a permutation.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a5243-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a5243-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="example"></a><span data-ttu-id="a5243-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a5243-112">Example</span></span>

<span data-ttu-id="a5243-113">O seguinte código Q# imprime a mensagem "Todos os diagnósticos concluídos com sucesso":</span><span class="sxs-lookup"><span data-stu-id="a5243-113">The following Q# code prints the message "All diagnostics completed successfully":</span></span>

```qsharp
Fact(IsPermutation([2, 0, 1], "");
Contradiction(IsPermutation([5, 0, 1], "[5, 0, 1] isn't a permutation");
Message("All diagnostics completed successfully.");
```

## <a name="remarks"></a><span data-ttu-id="a5243-114">Observações</span><span class="sxs-lookup"><span data-stu-id="a5243-114">Remarks</span></span>

<span data-ttu-id="a5243-115">Uma matriz de comprimento zero é trivialmente uma permutação.</span><span class="sxs-lookup"><span data-stu-id="a5243-115">An array of length zero is trivially a permutation.</span></span>