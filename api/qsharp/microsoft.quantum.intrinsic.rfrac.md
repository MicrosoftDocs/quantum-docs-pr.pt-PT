---
uid: Microsoft.Quantum.Intrinsic.RFrac
title: Operação RFrac
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: RFrac
qsharp.summary: >-
  Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.

  \begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r".
ms.openlocfilehash: bd182ea50d747e07bb0f8051c5dbc128b7ff7674
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198644"
---
# <a name="rfrac-operation"></a><span data-ttu-id="addc0-102">Operação RFrac</span><span class="sxs-lookup"><span data-stu-id="addc0-102">RFrac operation</span></span>

<span data-ttu-id="addc0-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="addc0-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="addc0-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="addc0-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="addc0-105">Aplica uma rotação sobre o eixo Pauli dado por um ângulo especificado como uma fração diádica.</span><span class="sxs-lookup"><span data-stu-id="addc0-105">Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.</span></span>

<span data-ttu-id="addc0-106">\start{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi \n \sigma_{\mu} / 2^k}, \end{align} onde $\mu \in \{ I, X, Y, Z \} $.</span><span class="sxs-lookup"><span data-stu-id="addc0-106">\begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

> [!WARNING]
> <span data-ttu-id="addc0-107">Esta operação utiliza a convenção de sinais **oposto** de @"microsoft.quantum.intrinsic.r" .</span><span class="sxs-lookup"><span data-stu-id="addc0-107">This operation uses the **opposite** sign convention from @"microsoft.quantum.intrinsic.r".</span></span>

```qsharp
operation RFrac (pauli : Pauli, numerator : Int, power : Int, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="addc0-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="addc0-108">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="addc0-109">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="addc0-109">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="addc0-110">Operador Pauli a ser exponencial para formar a rotação.</span><span class="sxs-lookup"><span data-stu-id="addc0-110">Pauli operator to be exponentiated to form the rotation.</span></span>


### <a name="numerator--int"></a><span data-ttu-id="addc0-111">numerador : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="addc0-111">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="addc0-112">Numerador na representação da fração dedódica do ângulo pelo qual o qubit deve ser rodado.</span><span class="sxs-lookup"><span data-stu-id="addc0-112">Numerator in the dyadic fraction representation of the angle by which the qubit is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="addc0-113">poder : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="addc0-113">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="addc0-114">Potência de dois especificando o denominador do ângulo pelo qual o qubit deve ser rodado.</span><span class="sxs-lookup"><span data-stu-id="addc0-114">Power of two specifying the denominator of the angle by which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="addc0-115">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="addc0-115">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="addc0-116">Qubit ao qual o portão deve ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="addc0-116">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="addc0-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="addc0-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="addc0-118">Observações</span><span class="sxs-lookup"><span data-stu-id="addc0-118">Remarks</span></span>

<span data-ttu-id="addc0-119">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="addc0-119">Equivalent to:</span></span>

```qsharp
// PI() is a Q# function that returns an approximation of π.
R(pauli, -PI() * IntAsDouble(numerator) / IntAsDouble(2 ^ (power - 1)), qubit);
```