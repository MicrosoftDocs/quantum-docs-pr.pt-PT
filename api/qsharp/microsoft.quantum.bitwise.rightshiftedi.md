---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: Função RightShiftedI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: b20a4a8c281a470af9a4828f8a5ca905a7918723
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209779"
---
# <a name="rightshiftedi-function"></a><span data-ttu-id="96bf1-102">Função RightShiftedI</span><span class="sxs-lookup"><span data-stu-id="96bf1-102">RightShiftedI function</span></span>

<span data-ttu-id="96bf1-103">Espaço de nome: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="96bf1-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="96bf1-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="96bf1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="96bf1-105">Muda a representação de um número direito por um determinado número de bits.</span><span class="sxs-lookup"><span data-stu-id="96bf1-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="96bf1-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="96bf1-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="96bf1-107">valor : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="96bf1-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="96bf1-108">O número cuja representação bitwise deve ser deslocada para a direita (menos significativa).</span><span class="sxs-lookup"><span data-stu-id="96bf1-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="96bf1-109">quantidade : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="96bf1-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="96bf1-110">O número de bits pelos quais `value` deve ser deslocado para a direita.</span><span class="sxs-lookup"><span data-stu-id="96bf1-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--int"></a><span data-ttu-id="96bf1-111">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="96bf1-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="96bf1-112">O valor `value` de. `amount`</span><span class="sxs-lookup"><span data-stu-id="96bf1-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="96bf1-113">Observações</span><span class="sxs-lookup"><span data-stu-id="96bf1-113">Remarks</span></span>

<span data-ttu-id="96bf1-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="96bf1-114">The following are equivalent:</span></span>

```Q#
let c = a >>> b;
let c = RightShiftedI(a, b);
```