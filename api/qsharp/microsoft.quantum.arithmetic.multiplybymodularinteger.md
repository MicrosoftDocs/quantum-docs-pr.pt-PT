---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: Operação MultiplyByModularInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: 6deced7862ab4cb74315219eaaab97380cdf0f92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719794"
---
# <a name="multiplybymodularinteger-operation"></a><span data-ttu-id="cbd63-102">Operação MultiplyByModularInteger</span><span class="sxs-lookup"><span data-stu-id="cbd63-102">MultiplyByModularInteger operation</span></span>

<span data-ttu-id="cbd63-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="cbd63-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="cbd63-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cbd63-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cbd63-105">Executa a multiplicação modular por uma constante de número inteiro num registo qubit.</span><span class="sxs-lookup"><span data-stu-id="cbd63-105">Performs modular multiplication by an integer constant on a qubit register.</span></span>

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="cbd63-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="cbd63-106">Description</span></span>

<span data-ttu-id="cbd63-107">Vamos `modulus` denotar $N$ e `constMultiplier` por $a$.</span><span class="sxs-lookup"><span data-stu-id="cbd63-107">Let us denote `modulus` by $N$ and `constMultiplier` by $a$.</span></span>
<span data-ttu-id="cbd63-108">Em seguida, esta operação implementa uma operação unitária definida pelo seguinte mapa na base computacional: $$ \start{align} \ket{y} \mapsto \ket{(a\cdot y) \operatorname{mod} N} \end{align} $$ por todas as $y$ entre $0$ e $N - 1$.</span><span class="sxs-lookup"><span data-stu-id="cbd63-108">Then this operation implements a unitary operation defined by the following map on the computational basis: $$ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $$ for all $y$ between $0$ and $N - 1$.</span></span>

## <a name="input"></a><span data-ttu-id="cbd63-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="cbd63-109">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="cbd63-110">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cbd63-110">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cbd63-111">Constante pela qual multiplicador está a ser multiplicado.</span><span class="sxs-lookup"><span data-stu-id="cbd63-111">Constant by which multiplier is being multiplied.</span></span> <span data-ttu-id="cbd63-112">Deve ser co-prime para modulus.</span><span class="sxs-lookup"><span data-stu-id="cbd63-112">Must be co-prime to modulus.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="cbd63-113">módulo : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cbd63-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cbd63-114">A operação de multiplicação é realizada `modulus` modulo.</span><span class="sxs-lookup"><span data-stu-id="cbd63-114">The multiplication operation is performed modulo `modulus`.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="cbd63-115">multiplicador : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="cbd63-115">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="cbd63-116">O número a ser multiplicado por uma constante.</span><span class="sxs-lookup"><span data-stu-id="cbd63-116">The number being multiplied by a constant.</span></span>
<span data-ttu-id="cbd63-117">Esta é uma variedade de qubits codificando um inteiro em formato pouco endiano.</span><span class="sxs-lookup"><span data-stu-id="cbd63-117">This is an array of qubits encoding an integer in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cbd63-118">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cbd63-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cbd63-119">Observações</span><span class="sxs-lookup"><span data-stu-id="cbd63-119">Remarks</span></span>

- <span data-ttu-id="cbd63-120">Para o diagrama do circuito e explicação consulte a figura 7 na [página 8 do arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span><span class="sxs-lookup"><span data-stu-id="cbd63-120">For the circuit diagram and explanation see Figure 7 on [Page 8 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span></span>
- <span data-ttu-id="cbd63-121">Esta operação corresponde a Uₐ em [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span><span class="sxs-lookup"><span data-stu-id="cbd63-121">This operation corresponds to Uₐ in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>