---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: Função IntAsBoolArray
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 9783a49a77bdc39ffe8c7725196eb620f4cd0100
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713453"
---
# <a name="intasboolarray-function"></a><span data-ttu-id="87670-102">Função IntAsBoolArray</span><span class="sxs-lookup"><span data-stu-id="87670-102">IntAsBoolArray function</span></span>

<span data-ttu-id="87670-103">Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="87670-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="87670-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="87670-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="87670-105">Produz uma representação binária de um inteiro positivo, usando a representação pouco-endiana para a matriz devolvida.</span><span class="sxs-lookup"><span data-stu-id="87670-105">Produces a binary representation of a positive integer, using the little-endian representation for the returned array.</span></span>

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="87670-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="87670-106">Input</span></span>

### <a name="number--int"></a><span data-ttu-id="87670-107">número : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="87670-107">number : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="87670-108">Um número inteiro positivo a ser convertido para uma variedade de valores booleanos.</span><span class="sxs-lookup"><span data-stu-id="87670-108">A positive integer to be converted to an array of boolean values.</span></span>


### <a name="bits--int"></a><span data-ttu-id="87670-109">bits : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="87670-109">bits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="87670-110">O número de bits na representação binária de `number` .</span><span class="sxs-lookup"><span data-stu-id="87670-110">The number of bits in the binary representation of `number`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="87670-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="87670-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="87670-112">Uma série de valores booleano representando `number` .</span><span class="sxs-lookup"><span data-stu-id="87670-112">An array of boolean values representing `number`.</span></span>

## <a name="remarks"></a><span data-ttu-id="87670-113">Observações</span><span class="sxs-lookup"><span data-stu-id="87670-113">Remarks</span></span>

<span data-ttu-id="87670-114">A entrada `bits` deve estar entre 0 e 63.</span><span class="sxs-lookup"><span data-stu-id="87670-114">The input `bits` must be between 0 and 63.</span></span>
<span data-ttu-id="87670-115">A entrada `number` deve estar entre 0 e 2^{\texttt{bits}} - 1$.</span><span class="sxs-lookup"><span data-stu-id="87670-115">The input `number` must be between 0 and $2^{\texttt{bits}} - 1$.</span></span>