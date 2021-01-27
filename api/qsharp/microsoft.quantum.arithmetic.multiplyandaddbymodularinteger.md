---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger
title: Operação MultiplyAndAddByModularInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddByModularInteger
qsharp.summary: Performs a modular multiply-and-add by integer constants on a qubit register.
ms.openlocfilehash: e4de934a5776e80dbf5f0d8334bf806e6a84b743
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846522"
---
# <a name="multiplyandaddbymodularinteger-operation"></a><span data-ttu-id="59d5f-102">Operação MultiplyAndAddByModularInteger</span><span class="sxs-lookup"><span data-stu-id="59d5f-102">MultiplyAndAddByModularInteger operation</span></span>

<span data-ttu-id="59d5f-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="59d5f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="59d5f-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="59d5f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="59d5f-105">Executa uma multiplicação modular multiplicadora e adiciona por constantes de número inteiro num registo qubit.</span><span class="sxs-lookup"><span data-stu-id="59d5f-105">Performs a modular multiply-and-add by integer constants on a qubit register.</span></span>

```qsharp
operation MultiplyAndAddByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, summand : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="59d5f-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="59d5f-106">Description</span></span>

<span data-ttu-id="59d5f-107">Implementa o mapa $$ \start{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{$y $a $N x</span><span class="sxs-lookup"><span data-stu-id="59d5f-107">Implements the map $$ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{align} $$ for a given modulus $N$, constant multiplier $a$, and summand $y$.</span></span>

## <a name="input"></a><span data-ttu-id="59d5f-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="59d5f-108">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="59d5f-109">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="59d5f-109">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="59d5f-110">Um inteiro $a$ a ser adicionado a cada rótulo de estado base.</span><span class="sxs-lookup"><span data-stu-id="59d5f-110">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="59d5f-111">módulo : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="59d5f-111">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="59d5f-112">O módulo $N$ que adição e multiplicação é tomada no que diz respeito.</span><span class="sxs-lookup"><span data-stu-id="59d5f-112">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="59d5f-113">multiplicador : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="59d5f-113">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="59d5f-114">Um registo quântico que represente um número inteiro não assinado cujo valor deve ser adicionado a cada rótulo de estado de base de `summand` .</span><span class="sxs-lookup"><span data-stu-id="59d5f-114">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="summand--littleendian"></a><span data-ttu-id="59d5f-115">summand : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="59d5f-115">summand : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="59d5f-116">Um registo quântico que representa um número inteiro não assinado para usar como alvo para esta operação.</span><span class="sxs-lookup"><span data-stu-id="59d5f-116">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="59d5f-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="59d5f-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="59d5f-118">Observações</span><span class="sxs-lookup"><span data-stu-id="59d5f-118">Remarks</span></span>

- <span data-ttu-id="59d5f-119">Para o diagrama do circuito e explicação consulte a figura 6 na [página 7 do arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)</span><span class="sxs-lookup"><span data-stu-id="59d5f-119">For the circuit diagram and explanation see Figure 6 on [Page 7 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)</span></span>
- <span data-ttu-id="59d5f-120">Esta operação corresponde à CMULT(a)MOD(N) em [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span><span class="sxs-lookup"><span data-stu-id="59d5f-120">This operation corresponds to CMULT(a)MOD(N) in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>

## <a name="see-also"></a><span data-ttu-id="59d5f-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="59d5f-121">See Also</span></span>

- [<span data-ttu-id="59d5f-122">Microsoft.Quantum.Aithmetic.MultiplyAndAddPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="59d5f-122">Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger)