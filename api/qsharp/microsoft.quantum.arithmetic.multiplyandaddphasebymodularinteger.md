---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: Operação MultiplyAndAddPhaseByModularInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: be7df50f040697329c2fe8bbc319c8cebb8b2687
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719806"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a><span data-ttu-id="37d21-102">Operação MultiplyAndAddPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="37d21-102">MultiplyAndAddPhaseByModularInteger operation</span></span>

<span data-ttu-id="37d21-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="37d21-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="37d21-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="37d21-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="37d21-105">O mesmo que MultiplyAndAddByModularInteger, mas assume que os sumários e codificam inteiros em QFT.</span><span class="sxs-lookup"><span data-stu-id="37d21-105">The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.</span></span>

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="37d21-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="37d21-106">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="37d21-107">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="37d21-107">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="37d21-108">Um inteiro $a$ a ser adicionado a cada rótulo de estado base.</span><span class="sxs-lookup"><span data-stu-id="37d21-108">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="37d21-109">módulo : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="37d21-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="37d21-110">O módulo $N$ que adição e multiplicação é tomada no que diz respeito.</span><span class="sxs-lookup"><span data-stu-id="37d21-110">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="37d21-111">multiplicador : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="37d21-111">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="37d21-112">Um registo quântico que represente um número inteiro não assinado cujo valor deve ser adicionado a cada rótulo de estado de base de `summand` .</span><span class="sxs-lookup"><span data-stu-id="37d21-112">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="phasesummand--phaselittleendian"></a><span data-ttu-id="37d21-113">faseSumand : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="37d21-113">phaseSummand : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="37d21-114">Um registo quântico que representa um número inteiro não assinado para usar como alvo para esta operação.</span><span class="sxs-lookup"><span data-stu-id="37d21-114">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="37d21-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="37d21-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="37d21-116">Observações</span><span class="sxs-lookup"><span data-stu-id="37d21-116">Remarks</span></span>

<span data-ttu-id="37d21-117">Assume que `phaseSummand` tem a parte mais alta definida para 0.</span><span class="sxs-lookup"><span data-stu-id="37d21-117">Assumes that `phaseSummand` has the highest bit set to 0.</span></span>
<span data-ttu-id="37d21-118">Também assume que o valor `phaseSummand` é inferior a $N$.</span><span class="sxs-lookup"><span data-stu-id="37d21-118">Also assumes that the value of `phaseSummand` is less than $N$.</span></span>

## <a name="see-also"></a><span data-ttu-id="37d21-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="37d21-119">See Also</span></span>

- [<span data-ttu-id="37d21-120">Microsoft.Quantum.Aithmetic.MultiplyAndAddByModularInteger</span><span class="sxs-lookup"><span data-stu-id="37d21-120">Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)