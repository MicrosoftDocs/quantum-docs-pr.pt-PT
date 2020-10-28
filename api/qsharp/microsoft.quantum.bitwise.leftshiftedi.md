---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: Função LeftShiftedI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: ce68311adf211169c2fb499bb189332370a6d6ac
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718666"
---
# <a name="leftshiftedi-function"></a><span data-ttu-id="817af-102">Função LeftShiftedI</span><span class="sxs-lookup"><span data-stu-id="817af-102">LeftShiftedI function</span></span>

<span data-ttu-id="817af-103">Espaço de nome: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="817af-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="817af-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="817af-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="817af-105">Muda a representação de um número deixado por um determinado número de bits.</span><span class="sxs-lookup"><span data-stu-id="817af-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="817af-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="817af-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="817af-107">valor : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="817af-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="817af-108">O número cuja representação bitwise deve ser deslocada para a esquerda (mais significativa).</span><span class="sxs-lookup"><span data-stu-id="817af-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="817af-109">quantidade : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="817af-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="817af-110">O número de bits pelos quais `value` deve ser deslocado para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="817af-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--int"></a><span data-ttu-id="817af-111">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="817af-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="817af-112">O valor `value` de, deslocado à esquerda por `amount` bocados.</span><span class="sxs-lookup"><span data-stu-id="817af-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="817af-113">Observações</span><span class="sxs-lookup"><span data-stu-id="817af-113">Remarks</span></span>

<span data-ttu-id="817af-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="817af-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedI(a, b);
```