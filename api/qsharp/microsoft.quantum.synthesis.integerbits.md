---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: Função InteiroBits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: ab459cd841cdac116cf0e98c094834f628b6a2d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719843"
---
# <a name="integerbits-function"></a><span data-ttu-id="5dab2-102">Função InteiroBits</span><span class="sxs-lookup"><span data-stu-id="5dab2-102">IntegerBits function</span></span>

<span data-ttu-id="5dab2-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="5dab2-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="5dab2-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5dab2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5dab2-105">Devolve todas as posições em que os pedaços de um inteiro são definidos.</span><span class="sxs-lookup"><span data-stu-id="5dab2-105">Returns all positions in which bits of an integer are set.</span></span>

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="5dab2-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5dab2-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="5dab2-107">valor : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5dab2-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5dab2-108">Um número não-inggativo.</span><span class="sxs-lookup"><span data-stu-id="5dab2-108">A nonnegative number.</span></span>


### <a name="length--int"></a><span data-ttu-id="5dab2-109">comprimento : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5dab2-109">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5dab2-110">O número de bits na expansão binária de `value` .</span><span class="sxs-lookup"><span data-stu-id="5dab2-110">The number of bits in the binary expansion of `value`.</span></span>



## <a name="output--int"></a><span data-ttu-id="5dab2-111">Saída : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5dab2-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5dab2-112">Uma matriz que contém todas as posições de bits (a partir de 0) que são 1 na expansão binária de `value` considerar todos os bits até à posição `length - 1` .</span><span class="sxs-lookup"><span data-stu-id="5dab2-112">An array containing all bit positions (starting from 0) that are 1 in the binary expansion of `value` considering all bits up to position `length - 1`.</span></span>  <span data-ttu-id="5dab2-113">Todas as posições são ordenadas na matriz por posição numa ordem crescente.</span><span class="sxs-lookup"><span data-stu-id="5dab2-113">All positions are ordered in the array by position in an increasing order.</span></span>