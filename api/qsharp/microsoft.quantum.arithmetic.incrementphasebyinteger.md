---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: Operação IncrementPhaseByInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 54b83b3d4460c05478543c51f8f9c0b0e7f5b1fa
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222920"
---
# <a name="incrementphasebyinteger-operation"></a><span data-ttu-id="b3b5b-102">Operação IncrementPhaseByInteger</span><span class="sxs-lookup"><span data-stu-id="b3b5b-102">IncrementPhaseByInteger operation</span></span>

<span data-ttu-id="b3b5b-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b3b5b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b3b5b-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b3b5b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b3b5b-105">Incrementa um registo quântico não assinado por um inteiro clássico, usando rotações de fase.</span><span class="sxs-lookup"><span data-stu-id="b3b5b-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="b3b5b-106">Description</span><span class="sxs-lookup"><span data-stu-id="b3b5b-106">Description</span></span>

<span data-ttu-id="b3b5b-107">Suponha que `target` codifica um inteiro não assinado $x$ em uma codificação pouco endiana e isso é igual a `increment` $a$.</span><span class="sxs-lookup"><span data-stu-id="b3b5b-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="b3b5b-108">Em seguida, esta operação implementa o unitário $\ket{x} \mapsto \ket{x + a}$, onde a adição é realizada modulo $2^n$, onde $n = \texttt{Comprimento (alvo!)} $.</span><span class="sxs-lookup"><span data-stu-id="b3b5b-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="b3b5b-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="b3b5b-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="b3b5b-110">incremento : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b3b5b-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b3b5b-111">O inteiro pelo qual o `target` é incrementado por.</span><span class="sxs-lookup"><span data-stu-id="b3b5b-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="b3b5b-112">alvo : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b3b5b-112">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="b3b5b-113">Um registo quântico que codifica um número inteiro não assinado utilizando a codificação pouco endiana na base dual (QFT).</span><span class="sxs-lookup"><span data-stu-id="b3b5b-113">A quantum register encoding an unsigned integer using little-endian encoding in the dual (QFT) basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b3b5b-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b3b5b-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b3b5b-115">Observações</span><span class="sxs-lookup"><span data-stu-id="b3b5b-115">Remarks</span></span>

<span data-ttu-id="b3b5b-116">Note que simplificamos o circuito porque o incremento é uma constante clássica, não um registo quântico.</span><span class="sxs-lookup"><span data-stu-id="b3b5b-116">Note that we have simplified the circuit because the increment is a classical constant, not a quantum register.</span></span>

<span data-ttu-id="b3b5b-117">Consulte a figura na [ página 6 do arXiv:quant-ph/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) para o diagrama do circuito e explicação.</span><span class="sxs-lookup"><span data-stu-id="b3b5b-117">See the figure on [ Page 6 of arXiv:quant-ph/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) for the circuit diagram and explanation.</span></span>

## <a name="references"></a><span data-ttu-id="b3b5b-118">Referências</span><span class="sxs-lookup"><span data-stu-id="b3b5b-118">References</span></span>

- [<span data-ttu-id="b3b5b-119">*Thomas G. Draper,* arXiv:quant-ph/0008033</span><span class="sxs-lookup"><span data-stu-id="b3b5b-119"> *Thomas G. Draper*, arXiv:quant-ph/0008033</span></span>](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a><span data-ttu-id="b3b5b-120">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b3b5b-120">See Also</span></span>

- [<span data-ttu-id="b3b5b-121">Microsoft.Quantum.Aithmetic.IncrementByInteger</span><span class="sxs-lookup"><span data-stu-id="b3b5b-121">Microsoft.Quantum.Arithmetic.IncrementByInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)