---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: AssertPhaseLessThan
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: 7b7a4fea8973727da4dcab6f739c6db8da835a2f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843439"
---
# <a name="assertphaselessthan-operation"></a><span data-ttu-id="095ee-102">AssertPhaseLessThan</span><span class="sxs-lookup"><span data-stu-id="095ee-102">AssertPhaseLessThan operation</span></span>

<span data-ttu-id="095ee-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="095ee-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="095ee-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="095ee-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="095ee-105">Afirma que o `number` codificado na FaseLittleEndian é inferior `value` a .</span><span class="sxs-lookup"><span data-stu-id="095ee-105">Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.</span></span>

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="095ee-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="095ee-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="095ee-107">valor : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="095ee-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="095ee-108">`number` deve ser menos do que isto.</span><span class="sxs-lookup"><span data-stu-id="095ee-108">`number` must be less than this.</span></span>


### <a name="number--phaselittleendian"></a><span data-ttu-id="095ee-109">número : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="095ee-109">number : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="095ee-110">Inteiro não assinado que é comparado a `value` .</span><span class="sxs-lookup"><span data-stu-id="095ee-110">Unsigned integer which is compared to `value`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="095ee-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="095ee-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="095ee-112">Observações</span><span class="sxs-lookup"><span data-stu-id="095ee-112">Remarks</span></span>

<span data-ttu-id="095ee-113">A versão controlada desta operação ignora os controlos.</span><span class="sxs-lookup"><span data-stu-id="095ee-113">The controlled version of this operation ignores controls.</span></span>