---
uid: Microsoft.Quantum.Intrinsic.R1Frac
title: Operação R1Frac
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1Frac
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.

  \begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}). \end{align}

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r", and does not include the > factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".
ms.openlocfilehash: bfae01d11524f64ceebd53aa8544d7ea48c40f31
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818695"
---
# <a name="r1frac-operation"></a><span data-ttu-id="2633f-102">Operação R1Frac</span><span class="sxs-lookup"><span data-stu-id="2633f-102">R1Frac operation</span></span>

<span data-ttu-id="2633f-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="2633f-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="2633f-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="2633f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="2633f-105">Aplica uma rotação sobre o estado $\ket {1} $ por um ângulo especificado como uma fração dedídica.</span><span class="sxs-lookup"><span data-stu-id="2633f-105">Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.</span></span>

<span data-ttu-id="2633f-106">\start{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}).</span><span class="sxs-lookup"><span data-stu-id="2633f-106">\begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}).</span></span>
<span data-ttu-id="2633f-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="2633f-107">\end{align}</span></span>

> [!WARNING]
> <span data-ttu-id="2633f-108">Esta operação utiliza a convenção de sinais **oposto** de @"microsoft.quantum.intrinsic.r" , e não inclui o fator de $1/ 2$ incluído por @"microsoft.quantum.intrinsic.r1" .</span><span class="sxs-lookup"><span data-stu-id="2633f-108">This operation uses the **opposite** sign convention from @"microsoft.quantum.intrinsic.r", and does not include the factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".</span></span>

```qsharp
operation R1Frac (numerator : Int, power : Int, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2633f-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="2633f-109">Input</span></span>

### <a name="numerator--int"></a><span data-ttu-id="2633f-110">numerador : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2633f-110">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2633f-111">Numerador na representação da fração dedódica do ângulo pelo qual o qubit deve ser rodado.</span><span class="sxs-lookup"><span data-stu-id="2633f-111">Numerator in the dyadic fraction representation of the angle by which the qubit is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="2633f-112">poder : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2633f-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2633f-113">Potência de dois especificando o denominador do ângulo pelo qual o qubit deve ser rodado.</span><span class="sxs-lookup"><span data-stu-id="2633f-113">Power of two specifying the denominator of the angle by which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="2633f-114">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2633f-114">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2633f-115">Qubit ao qual o portão deve ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="2633f-115">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2633f-116">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2633f-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2633f-117">Observações</span><span class="sxs-lookup"><span data-stu-id="2633f-117">Remarks</span></span>

<span data-ttu-id="2633f-118">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="2633f-118">Equivalent to:</span></span>

```qsharp
RFrac(PauliZ, -numerator, denominator + 1, qubit);
RFrac(PauliI, numerator, denominator + 1, qubit);
```