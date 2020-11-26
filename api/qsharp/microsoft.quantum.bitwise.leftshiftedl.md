---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: Função LeftShiftedL
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 00d4f9151c620e044074930933ea2912b52534ed
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219673"
---
# <a name="leftshiftedl-function"></a><span data-ttu-id="25cba-102">Função LeftShiftedL</span><span class="sxs-lookup"><span data-stu-id="25cba-102">LeftShiftedL function</span></span>

<span data-ttu-id="25cba-103">Espaço de nome: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="25cba-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="25cba-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="25cba-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="25cba-105">Muda a representação de um número deixado por um determinado número de bits.</span><span class="sxs-lookup"><span data-stu-id="25cba-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="25cba-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="25cba-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="25cba-107">valor : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="25cba-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="25cba-108">O número cuja representação bitwise deve ser deslocada para a esquerda (mais significativa).</span><span class="sxs-lookup"><span data-stu-id="25cba-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="25cba-109">quantidade : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="25cba-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="25cba-110">O número de bits pelos quais `value` deve ser deslocado para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="25cba-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="25cba-111">Saída : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="25cba-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="25cba-112">O valor `value` de, deslocado à esquerda por `amount` bocados.</span><span class="sxs-lookup"><span data-stu-id="25cba-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="25cba-113">Observações</span><span class="sxs-lookup"><span data-stu-id="25cba-113">Remarks</span></span>

<span data-ttu-id="25cba-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="25cba-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedL(a, b);
```