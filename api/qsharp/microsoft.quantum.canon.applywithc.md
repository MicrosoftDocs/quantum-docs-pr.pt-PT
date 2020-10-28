---
uid: Microsoft.Quantum.Canon.ApplyWithC
title: Aplicação DeC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithC
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: 8de1ddf0bf176853b33926be7647bc5d1d35095d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716897"
---
# <a name="applywithc-operation"></a><span data-ttu-id="b15b5-102">Aplicação DeC</span><span class="sxs-lookup"><span data-stu-id="b15b5-102">ApplyWithC operation</span></span>

<span data-ttu-id="b15b5-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b15b5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b15b5-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b15b5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b15b5-105">Tendo em conta duas operações, aplica-se uma como conjugada com a outra.</span><span class="sxs-lookup"><span data-stu-id="b15b5-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWithC<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Ctl), target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="b15b5-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="b15b5-106">Description</span></span>

<span data-ttu-id="b15b5-107">Tendo em conta duas operações, respectivamente descritas pelos operadores unitários $U$ e $V$, aplica-as na sequência $U^{\dagger} V U$.</span><span class="sxs-lookup"><span data-stu-id="b15b5-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="b15b5-108">Ou seja, esta operação implementa o operador unitário dado por $V$ conjugado com $U$.</span><span class="sxs-lookup"><span data-stu-id="b15b5-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="b15b5-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="b15b5-109">Input</span></span>

### <a name="outeroperation--t--unit-adj"></a><span data-ttu-id="b15b5-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span><span class="sxs-lookup"><span data-stu-id="b15b5-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="b15b5-111">A operação $U$ que deve ser usada para conjugar $V dólares.</span><span class="sxs-lookup"><span data-stu-id="b15b5-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="b15b5-112">Note que a operação exterior $U$ tem de ser adjacente, mas não precisa de ser controlável.</span><span class="sxs-lookup"><span data-stu-id="b15b5-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit-ctl"></a><span data-ttu-id="b15b5-113">inoperação interna : 'T => [Unidade](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="b15b5-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="b15b5-114">A operação $V dólares a ser conjugada.</span><span class="sxs-lookup"><span data-stu-id="b15b5-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="b15b5-115">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="b15b5-115">target : 'T</span></span>

<span data-ttu-id="b15b5-116">A entrada a fornecer às operações exteriores e internas.</span><span class="sxs-lookup"><span data-stu-id="b15b5-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b15b5-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b15b5-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b15b5-118">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="b15b5-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b15b5-119">'T</span><span class="sxs-lookup"><span data-stu-id="b15b5-119">'T</span></span>

<span data-ttu-id="b15b5-120">O alvo em que cada uma das operações internas e exteriores atuam.</span><span class="sxs-lookup"><span data-stu-id="b15b5-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="b15b5-121">Observações</span><span class="sxs-lookup"><span data-stu-id="b15b5-121">Remarks</span></span>

<span data-ttu-id="b15b5-122">Presume-se sempre que a operação exterior é contígua, mas não é necessário controlável para que a operação combinada seja controlável.</span><span class="sxs-lookup"><span data-stu-id="b15b5-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="b15b5-123">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b15b5-123">See Also</span></span>

- [<span data-ttu-id="b15b5-124">Microsoft.Quantum.Canon.ApplyWith</span><span class="sxs-lookup"><span data-stu-id="b15b5-124">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)
- [<span data-ttu-id="b15b5-125">Microsoft.Quantum.Canon.ApplyWithA</span><span class="sxs-lookup"><span data-stu-id="b15b5-125">Microsoft.Quantum.Canon.ApplyWithA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [<span data-ttu-id="b15b5-126">Microsoft.Quantum.Canon.ApplyWithCA</span><span class="sxs-lookup"><span data-stu-id="b15b5-126">Microsoft.Quantum.Canon.ApplyWithCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithCA)