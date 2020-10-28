---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: Função LeftShiftedL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 17e5c845755f74e9703381bc82bfd63be836d038
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718631"
---
# <a name="leftshiftedl-function"></a><span data-ttu-id="fe8a3-102">Função LeftShiftedL</span><span class="sxs-lookup"><span data-stu-id="fe8a3-102">LeftShiftedL function</span></span>

<span data-ttu-id="fe8a3-103">Espaço de nome: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="fe8a3-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="fe8a3-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fe8a3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fe8a3-105">Muda a representação de um número deixado por um determinado número de bits.</span><span class="sxs-lookup"><span data-stu-id="fe8a3-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="fe8a3-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="fe8a3-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="fe8a3-107">valor : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="fe8a3-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="fe8a3-108">O número cuja representação bitwise deve ser deslocada para a esquerda (mais significativa).</span><span class="sxs-lookup"><span data-stu-id="fe8a3-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="fe8a3-109">quantidade : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fe8a3-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fe8a3-110">O número de bits pelos quais `value` deve ser deslocado para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="fe8a3-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="fe8a3-111">Saída : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="fe8a3-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="fe8a3-112">O valor `value` de, deslocado à esquerda por `amount` bocados.</span><span class="sxs-lookup"><span data-stu-id="fe8a3-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="fe8a3-113">Observações</span><span class="sxs-lookup"><span data-stu-id="fe8a3-113">Remarks</span></span>

<span data-ttu-id="fe8a3-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="fe8a3-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedL(a, b);
```