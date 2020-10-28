---
uid: Microsoft.Quantum.Intrinsic.R1Frac
title: Operação R1Frac
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1Frac
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.

  \begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}). \end{align}

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r", and does not include the > factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".
ms.openlocfilehash: bfa6cd60eebd05feec8cfa2bf71e09dc0d02843a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720899"
---
# <a name="r1frac-operation"></a><span data-ttu-id="e470d-102">Operação R1Frac</span><span class="sxs-lookup"><span data-stu-id="e470d-102">R1Frac operation</span></span>

<span data-ttu-id="e470d-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="e470d-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="e470d-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e470d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e470d-105">Aplica uma rotação sobre o estado $\ket {1} $ por um ângulo especificado como uma fração dedídica.</span><span class="sxs-lookup"><span data-stu-id="e470d-105">Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.</span></span>

<span data-ttu-id="e470d-106">\start{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}).</span><span class="sxs-lookup"><span data-stu-id="e470d-106">\begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}).</span></span>
<span data-ttu-id="e470d-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="e470d-107">\end{align}</span></span>

> [!WARNING]
> <span data-ttu-id="e470d-108">Esta operação utiliza a convenção de sinais **oposto** de @"microsoft.quantum.intrinsic.r" , e não inclui o fator de $1/ 2$ incluído por @"microsoft.quantum.intrinsic.r1" .</span><span class="sxs-lookup"><span data-stu-id="e470d-108">This operation uses the **opposite** sign convention from @"microsoft.quantum.intrinsic.r", and does not include the factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".</span></span>

```qsharp
operation R1Frac (numerator : Int, power : Int, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="e470d-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="e470d-109">Input</span></span>

### <a name="numerator--int"></a><span data-ttu-id="e470d-110">numerador : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e470d-110">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e470d-111">Numerador na representação da fração dedódica do ângulo pelo qual o qubit deve ser rodado.</span><span class="sxs-lookup"><span data-stu-id="e470d-111">Numerator in the dyadic fraction representation of the angle by which the qubit is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="e470d-112">poder : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e470d-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e470d-113">Potência de dois especificando o denominador do ângulo pelo qual o qubit deve ser rodado.</span><span class="sxs-lookup"><span data-stu-id="e470d-113">Power of two specifying the denominator of the angle by which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="e470d-114">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e470d-114">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e470d-115">Qubit ao qual o portão deve ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="e470d-115">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e470d-116">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e470d-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e470d-117">Observações</span><span class="sxs-lookup"><span data-stu-id="e470d-117">Remarks</span></span>

<span data-ttu-id="e470d-118">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="e470d-118">Equivalent to:</span></span>

```qsharp
RFrac(PauliZ, -numerator, denominator + 1, qubit);
RFrac(PauliI, numerator, denominator + 1, qubit);
```