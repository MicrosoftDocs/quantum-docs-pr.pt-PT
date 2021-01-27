---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: Operação IncrementPhaseByInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: cc7922b2940cb979394958d5eb4e9933144eb062
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843151"
---
# <a name="incrementphasebyinteger-operation"></a><span data-ttu-id="6ce3d-102">Operação IncrementPhaseByInteger</span><span class="sxs-lookup"><span data-stu-id="6ce3d-102">IncrementPhaseByInteger operation</span></span>

<span data-ttu-id="6ce3d-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6ce3d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6ce3d-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6ce3d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6ce3d-105">Incrementa um registo quântico não assinado por um inteiro clássico, usando rotações de fase.</span><span class="sxs-lookup"><span data-stu-id="6ce3d-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="6ce3d-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="6ce3d-106">Description</span></span>

<span data-ttu-id="6ce3d-107">Suponha que `target` codifica um inteiro não assinado $x$ em uma codificação pouco endiana e isso é igual a `increment` $a$.</span><span class="sxs-lookup"><span data-stu-id="6ce3d-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="6ce3d-108">Em seguida, esta operação implementa o unitário $\ket{x} \mapsto \ket{x + a}$, onde a adição é realizada modulo $2^n$, onde $n = \texttt{Comprimento (alvo!)} $.</span><span class="sxs-lookup"><span data-stu-id="6ce3d-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="6ce3d-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="6ce3d-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="6ce3d-110">incremento : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6ce3d-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6ce3d-111">O inteiro pelo qual o `target` é incrementado por.</span><span class="sxs-lookup"><span data-stu-id="6ce3d-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="6ce3d-112">alvo : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6ce3d-112">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="6ce3d-113">Um registo quântico que codifica um número inteiro não assinado utilizando a codificação pouco endiana na base dual (QFT).</span><span class="sxs-lookup"><span data-stu-id="6ce3d-113">A quantum register encoding an unsigned integer using little-endian encoding in the dual (QFT) basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6ce3d-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6ce3d-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6ce3d-115">Observações</span><span class="sxs-lookup"><span data-stu-id="6ce3d-115">Remarks</span></span>

<span data-ttu-id="6ce3d-116">Note que simplificamos o circuito porque o incremento é uma constante clássica, não um registo quântico.</span><span class="sxs-lookup"><span data-stu-id="6ce3d-116">Note that we have simplified the circuit because the increment is a classical constant, not a quantum register.</span></span>

<span data-ttu-id="6ce3d-117">Consulte a figura na [ página 6 do arXiv:quant-ph/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) para o diagrama do circuito e explicação.</span><span class="sxs-lookup"><span data-stu-id="6ce3d-117">See the figure on [ Page 6 of arXiv:quant-ph/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) for the circuit diagram and explanation.</span></span>

## <a name="references"></a><span data-ttu-id="6ce3d-118">Referências</span><span class="sxs-lookup"><span data-stu-id="6ce3d-118">References</span></span>

- [<span data-ttu-id="6ce3d-119">*Thomas G. Draper,* arXiv:quant-ph/0008033</span><span class="sxs-lookup"><span data-stu-id="6ce3d-119"> *Thomas G. Draper*, arXiv:quant-ph/0008033</span></span>](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a><span data-ttu-id="6ce3d-120">Consulte também</span><span class="sxs-lookup"><span data-stu-id="6ce3d-120">See Also</span></span>

- [<span data-ttu-id="6ce3d-121">Microsoft.Quantum.Aithmetic.IncrementByInteger</span><span class="sxs-lookup"><span data-stu-id="6ce3d-121">Microsoft.Quantum.Arithmetic.IncrementByInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)