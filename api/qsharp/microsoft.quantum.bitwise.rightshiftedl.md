---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: Função RightShiftedL
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 3d941e1a0bcd96fe54ab01019293d883f11547a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219520"
---
# <a name="rightshiftedl-function"></a><span data-ttu-id="a2346-102">Função RightShiftedL</span><span class="sxs-lookup"><span data-stu-id="a2346-102">RightShiftedL function</span></span>

<span data-ttu-id="a2346-103">Espaço de nome: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="a2346-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="a2346-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a2346-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a2346-105">Muda a representação de um número direito por um determinado número de bits.</span><span class="sxs-lookup"><span data-stu-id="a2346-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="a2346-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a2346-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="a2346-107">valor : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a2346-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a2346-108">O número cuja representação bitwise deve ser deslocada para a direita (menos significativa).</span><span class="sxs-lookup"><span data-stu-id="a2346-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="a2346-109">quantidade : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a2346-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a2346-110">O número de bits pelos quais `value` deve ser deslocado para a direita.</span><span class="sxs-lookup"><span data-stu-id="a2346-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="a2346-111">Saída : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a2346-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a2346-112">O valor `value` de. `amount`</span><span class="sxs-lookup"><span data-stu-id="a2346-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="a2346-113">Observações</span><span class="sxs-lookup"><span data-stu-id="a2346-113">Remarks</span></span>

<span data-ttu-id="a2346-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="a2346-114">The following are equivalent:</span></span>

```Q#
let c = a >>> b;
let c = RightShiftedL(a, b);
```