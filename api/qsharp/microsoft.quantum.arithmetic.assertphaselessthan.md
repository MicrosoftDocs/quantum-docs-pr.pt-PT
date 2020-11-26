---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: AssertPhaseLessThan
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: 8a943ff937593801bd308ab4224c7051ff8a10cb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223753"
---
# <a name="assertphaselessthan-operation"></a><span data-ttu-id="f5bd0-102">AssertPhaseLessThan</span><span class="sxs-lookup"><span data-stu-id="f5bd0-102">AssertPhaseLessThan operation</span></span>

<span data-ttu-id="f5bd0-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f5bd0-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f5bd0-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f5bd0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f5bd0-105">Afirma que o `number` codificado na FaseLittleEndian é inferior `value` a .</span><span class="sxs-lookup"><span data-stu-id="f5bd0-105">Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.</span></span>

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f5bd0-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f5bd0-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="f5bd0-107">valor : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f5bd0-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f5bd0-108">`number` deve ser menos do que isto.</span><span class="sxs-lookup"><span data-stu-id="f5bd0-108">`number` must be less than this.</span></span>


### <a name="number--phaselittleendian"></a><span data-ttu-id="f5bd0-109">número : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f5bd0-109">number : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="f5bd0-110">Inteiro não assinado que é comparado a `value` .</span><span class="sxs-lookup"><span data-stu-id="f5bd0-110">Unsigned integer which is compared to `value`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f5bd0-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f5bd0-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f5bd0-112">Observações</span><span class="sxs-lookup"><span data-stu-id="f5bd0-112">Remarks</span></span>

<span data-ttu-id="f5bd0-113">A versão controlada desta operação ignora os controlos.</span><span class="sxs-lookup"><span data-stu-id="f5bd0-113">The controlled version of this operation ignores controls.</span></span>