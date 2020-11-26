---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger
title: IncrementPhaseByModularInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 6a39ce49dfa28c1f1cbe6b29e526144c3ac19e53
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222886"
---
# <a name="incrementphasebymodularinteger-operation"></a><span data-ttu-id="4f43e-102">IncrementPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="4f43e-102">IncrementPhaseByModularInteger operation</span></span>

<span data-ttu-id="4f43e-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4f43e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4f43e-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4f43e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4f43e-105">Executa um incremento modular de um registo qubit por uma constante de inteiro.</span><span class="sxs-lookup"><span data-stu-id="4f43e-105">Performs a modular increment of a qubit register by an integer constant.</span></span>

```qsharp
operation IncrementPhaseByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="4f43e-106">Description</span><span class="sxs-lookup"><span data-stu-id="4f43e-106">Description</span></span>

<span data-ttu-id="4f43e-107">Vamos denotar `increment` por $a$, `modulus` por $N$ e inteiro codificado `target` por $y$.</span><span class="sxs-lookup"><span data-stu-id="4f43e-107">Let us denote `increment` by $a$, `modulus` by $N$ and integer encoded in `target` by $y$.</span></span>
<span data-ttu-id="4f43e-108">Em seguida, a operação executa a seguinte transformação: \start{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Os inteiros são codificados em formato pequeno-endiano na base QFT.</span><span class="sxs-lookup"><span data-stu-id="4f43e-108">Then the operation performs the following transformation: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Integers are encoded in little-endian format in QFT basis.</span></span>

## <a name="input"></a><span data-ttu-id="4f43e-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="4f43e-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="4f43e-110">incremento : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4f43e-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4f43e-111">Incremento inteiro $a$ a ser adicionado a $y$.</span><span class="sxs-lookup"><span data-stu-id="4f43e-111">Integer increment $a$ to be added to $y$.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="4f43e-112">módulo : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4f43e-112">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4f43e-113">Inteiro $N$ que mods $y + a$.</span><span class="sxs-lookup"><span data-stu-id="4f43e-113">Integer $N$ that mods $y + a$.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="4f43e-114">alvo : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4f43e-114">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="4f43e-115">O inteiro $y$ em formato de pequena ponta-de-final codificado por fases a que `increment` $a$ é adicionado.</span><span class="sxs-lookup"><span data-stu-id="4f43e-115">Integer $y$ in phase-encoded little-endian format that `increment` $a$ is added to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4f43e-116">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4f43e-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4f43e-117">Observações</span><span class="sxs-lookup"><span data-stu-id="4f43e-117">Remarks</span></span>

<span data-ttu-id="4f43e-118">Assume que `target` tem a parte mais alta definida para 0.</span><span class="sxs-lookup"><span data-stu-id="4f43e-118">Assumes that `target` has the highest bit set to 0.</span></span>
<span data-ttu-id="4f43e-119">Também assume que o valor do alvo é inferior a $N$.</span><span class="sxs-lookup"><span data-stu-id="4f43e-119">Also assumes that the value of target is less than $N$.</span></span>

<span data-ttu-id="4f43e-120">Para o diagrama do circuito e explicação consulte a figura 5 na [página 5 do arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5).</span><span class="sxs-lookup"><span data-stu-id="4f43e-120">For the circuit diagram and explanation see Figure 5 on [Page 5 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5).</span></span>

## <a name="see-also"></a><span data-ttu-id="4f43e-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4f43e-121">See Also</span></span>

- [<span data-ttu-id="4f43e-122">Microsoft.Quantum.Aithmetic.IncrementByModularInteger</span><span class="sxs-lookup"><span data-stu-id="4f43e-122">Microsoft.Quantum.Arithmetic.IncrementByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByModularInteger)