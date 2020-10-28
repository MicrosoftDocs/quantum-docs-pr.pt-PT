---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: Função RightShiftedI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: b0ca7d3cb84c58429e9b3a29893a6140a717006b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718582"
---
# <a name="rightshiftedi-function"></a><span data-ttu-id="bb5cb-102">Função RightShiftedI</span><span class="sxs-lookup"><span data-stu-id="bb5cb-102">RightShiftedI function</span></span>

<span data-ttu-id="bb5cb-103">Espaço de nome: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="bb5cb-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="bb5cb-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bb5cb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bb5cb-105">Muda a representação de um número direito por um determinado número de bits.</span><span class="sxs-lookup"><span data-stu-id="bb5cb-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="bb5cb-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="bb5cb-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="bb5cb-107">valor : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bb5cb-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bb5cb-108">O número cuja representação bitwise deve ser deslocada para a direita (menos significativa).</span><span class="sxs-lookup"><span data-stu-id="bb5cb-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="bb5cb-109">quantidade : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bb5cb-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bb5cb-110">O número de bits pelos quais `value` deve ser deslocado para a direita.</span><span class="sxs-lookup"><span data-stu-id="bb5cb-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--int"></a><span data-ttu-id="bb5cb-111">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bb5cb-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bb5cb-112">O valor `value` de. `amount`</span><span class="sxs-lookup"><span data-stu-id="bb5cb-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="bb5cb-113">Observações</span><span class="sxs-lookup"><span data-stu-id="bb5cb-113">Remarks</span></span>

<span data-ttu-id="bb5cb-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="bb5cb-114">The following are equivalent:</span></span>

```Q#
let c = a >>> b;
let c = RightShiftedI(a, b);
```