---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: Função RightShiftedI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 5c3106eb73178554184cbfb37333c027805c69f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845262"
---
# <a name="rightshiftedi-function"></a><span data-ttu-id="3a0b5-102">Função RightShiftedI</span><span class="sxs-lookup"><span data-stu-id="3a0b5-102">RightShiftedI function</span></span>

<span data-ttu-id="3a0b5-103">Espaço de nome: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="3a0b5-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="3a0b5-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3a0b5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3a0b5-105">Muda a representação de um número direito por um determinado número de bits.</span><span class="sxs-lookup"><span data-stu-id="3a0b5-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="3a0b5-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3a0b5-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="3a0b5-107">valor : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3a0b5-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3a0b5-108">O número cuja representação bitwise deve ser deslocada para a direita (menos significativa).</span><span class="sxs-lookup"><span data-stu-id="3a0b5-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="3a0b5-109">quantidade : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3a0b5-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3a0b5-110">O número de bits pelos quais `value` deve ser deslocado para a direita.</span><span class="sxs-lookup"><span data-stu-id="3a0b5-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--int"></a><span data-ttu-id="3a0b5-111">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3a0b5-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3a0b5-112">O valor `value` de. `amount`</span><span class="sxs-lookup"><span data-stu-id="3a0b5-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="3a0b5-113">Observações</span><span class="sxs-lookup"><span data-stu-id="3a0b5-113">Remarks</span></span>

<span data-ttu-id="3a0b5-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="3a0b5-114">The following are equivalent:</span></span>

```qsharp
let c = a >>> b;
let c = RightShiftedI(a, b);
```