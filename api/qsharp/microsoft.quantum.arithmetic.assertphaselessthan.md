---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: AssertPhaseLessThan
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: d003d83a84356ce52c5601135000813c7f119e4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721378"
---
# <a name="assertphaselessthan-operation"></a><span data-ttu-id="3a5e3-102">AssertPhaseLessThan</span><span class="sxs-lookup"><span data-stu-id="3a5e3-102">AssertPhaseLessThan operation</span></span>

<span data-ttu-id="3a5e3-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3a5e3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3a5e3-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3a5e3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3a5e3-105">Afirma que o `number` codificado na FaseLittleEndian é inferior `value` a .</span><span class="sxs-lookup"><span data-stu-id="3a5e3-105">Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.</span></span>

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="3a5e3-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3a5e3-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="3a5e3-107">valor : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3a5e3-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3a5e3-108">`number` deve ser menos do que isto.</span><span class="sxs-lookup"><span data-stu-id="3a5e3-108">`number` must be less than this.</span></span>


### <a name="number--phaselittleendian"></a><span data-ttu-id="3a5e3-109">número : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3a5e3-109">number : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="3a5e3-110">Inteiro não assinado que é comparado a `value` .</span><span class="sxs-lookup"><span data-stu-id="3a5e3-110">Unsigned integer which is compared to `value`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3a5e3-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3a5e3-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3a5e3-112">Observações</span><span class="sxs-lookup"><span data-stu-id="3a5e3-112">Remarks</span></span>

<span data-ttu-id="3a5e3-113">A versão controlada desta operação ignora os controlos.</span><span class="sxs-lookup"><span data-stu-id="3a5e3-113">The controlled version of this operation ignores controls.</span></span>