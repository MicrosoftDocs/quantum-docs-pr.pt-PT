---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalI
title: Operação ComputeReciprocalI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalI
qsharp.summary: Computes the reciprocal 1/x for an unsigned integer x using integer division. The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.
ms.openlocfilehash: c28027f7a2533885102a54a028bec37eb608f2b4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846711"
---
# <a name="computereciprocali-operation"></a><span data-ttu-id="cae1b-102">Operação ComputeReciprocalI</span><span class="sxs-lookup"><span data-stu-id="cae1b-102">ComputeReciprocalI operation</span></span>

<span data-ttu-id="cae1b-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="cae1b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="cae1b-104">Pacote: [Microsoft.Quantum.Nummerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="cae1b-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="cae1b-105">Calcula o 1/x recíproco para um inteiro inteiro não assinado x usando a divisão inteiro.</span><span class="sxs-lookup"><span data-stu-id="cae1b-105">Computes the reciprocal 1/x for an unsigned integer x using integer division.</span></span> <span data-ttu-id="cae1b-106">O resultado, interpretado como um inteiro, `floor(2^(2*n-1) / x)` será.</span><span class="sxs-lookup"><span data-stu-id="cae1b-106">The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.</span></span>

```qsharp
operation ComputeReciprocalI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="cae1b-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="cae1b-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="cae1b-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="cae1b-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="cae1b-109">inteiro não assinado n-bit</span><span class="sxs-lookup"><span data-stu-id="cae1b-109">n-bit unsigned integer</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="cae1b-110">resultado : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="cae1b-110">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="cae1b-111">Saída de 2n bit, deve estar em $\ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="cae1b-111">2n-bit output, must be in $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cae1b-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cae1b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cae1b-113">Observações</span><span class="sxs-lookup"><span data-stu-id="cae1b-113">Remarks</span></span>

<span data-ttu-id="cae1b-114">Para a entrada x=0, a saída será só uma.</span><span class="sxs-lookup"><span data-stu-id="cae1b-114">For the input x=0, the output will be all-ones.</span></span>