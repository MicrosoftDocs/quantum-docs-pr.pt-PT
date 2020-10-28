---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: Função RightShiftedL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 2929ba58b636847257391930e1019769fd2c2580
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718571"
---
# <a name="rightshiftedl-function"></a><span data-ttu-id="6c80d-102">Função RightShiftedL</span><span class="sxs-lookup"><span data-stu-id="6c80d-102">RightShiftedL function</span></span>

<span data-ttu-id="6c80d-103">Espaço de nome: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="6c80d-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="6c80d-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6c80d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6c80d-105">Muda a representação de um número direito por um determinado número de bits.</span><span class="sxs-lookup"><span data-stu-id="6c80d-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="6c80d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6c80d-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="6c80d-107">valor : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="6c80d-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="6c80d-108">O número cuja representação bitwise deve ser deslocada para a direita (menos significativa).</span><span class="sxs-lookup"><span data-stu-id="6c80d-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="6c80d-109">quantidade : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6c80d-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6c80d-110">O número de bits pelos quais `value` deve ser deslocado para a direita.</span><span class="sxs-lookup"><span data-stu-id="6c80d-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="6c80d-111">Saída : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="6c80d-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="6c80d-112">O valor `value` de. `amount`</span><span class="sxs-lookup"><span data-stu-id="6c80d-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="6c80d-113">Observações</span><span class="sxs-lookup"><span data-stu-id="6c80d-113">Remarks</span></span>

<span data-ttu-id="6c80d-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="6c80d-114">The following are equivalent:</span></span>

```Q#
let c = a >>> b;
let c = RightShiftedL(a, b);
```