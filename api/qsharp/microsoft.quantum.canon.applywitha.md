---
uid: Microsoft.Quantum.Canon.ApplyWithA
title: Aplicação OperaçãoWithA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: b8847d4b3ddb88031ef360f183b86f6483706cc6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207875"
---
# <a name="applywitha-operation"></a><span data-ttu-id="981a8-102">Aplicação OperaçãoWithA</span><span class="sxs-lookup"><span data-stu-id="981a8-102">ApplyWithA operation</span></span>

<span data-ttu-id="981a8-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="981a8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="981a8-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="981a8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="981a8-105">Tendo em conta duas operações, aplica-se uma como conjugada com a outra.</span><span class="sxs-lookup"><span data-stu-id="981a8-105">Given two operations, applies one as conjugated with the other.</span></span>

```qsharp
operation ApplyWithA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj), target : 'T) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="981a8-106">Description</span><span class="sxs-lookup"><span data-stu-id="981a8-106">Description</span></span>

<span data-ttu-id="981a8-107">Tendo em conta duas operações, respectivamente descritas pelos operadores unitários $U$ e $V$, aplica-as na sequência $U^{\dagger} V U$.</span><span class="sxs-lookup"><span data-stu-id="981a8-107">Given two operations, respectively described by unitary operators $U$ and $V$, applies them in the sequence $U^{\dagger} V U$.</span></span> <span data-ttu-id="981a8-108">Ou seja, esta operação implementa o operador unitário dado por $V$ conjugado com $U$.</span><span class="sxs-lookup"><span data-stu-id="981a8-108">That is, this operation implements the unitary operator given by $V$ conjugated with $U$.</span></span>

## <a name="input"></a><span data-ttu-id="981a8-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="981a8-109">Input</span></span>

### <a name="outeroperation--t--unit--is-adj"></a><span data-ttu-id="981a8-110">outerOperation : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="981a8-110">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="981a8-111">A operação $U$ que deve ser usada para conjugar $V dólares.</span><span class="sxs-lookup"><span data-stu-id="981a8-111">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="981a8-112">Note que a operação exterior $U$ tem de ser adjacente, mas não precisa de ser controlável.</span><span class="sxs-lookup"><span data-stu-id="981a8-112">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit--is-adj"></a><span data-ttu-id="981a8-113">insuflação : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="981a8-113">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="981a8-114">A operação $V dólares a ser conjugada.</span><span class="sxs-lookup"><span data-stu-id="981a8-114">The operation $V$ being conjugated.</span></span>


### <a name="target--t"></a><span data-ttu-id="981a8-115">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="981a8-115">target : 'T</span></span>

<span data-ttu-id="981a8-116">A entrada a fornecer às operações exteriores e internas.</span><span class="sxs-lookup"><span data-stu-id="981a8-116">The input to be provided to the outer and inner operations.</span></span>



## <a name="output--unit"></a><span data-ttu-id="981a8-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="981a8-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="981a8-118">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="981a8-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="981a8-119">'T</span><span class="sxs-lookup"><span data-stu-id="981a8-119">'T</span></span>

<span data-ttu-id="981a8-120">O alvo em que cada uma das operações internas e exteriores atuam.</span><span class="sxs-lookup"><span data-stu-id="981a8-120">The target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="981a8-121">Observações</span><span class="sxs-lookup"><span data-stu-id="981a8-121">Remarks</span></span>

<span data-ttu-id="981a8-122">Presume-se sempre que a operação exterior é contígua, mas não é necessário controlável para que a operação combinada seja controlável.</span><span class="sxs-lookup"><span data-stu-id="981a8-122">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="981a8-123">Consulte também</span><span class="sxs-lookup"><span data-stu-id="981a8-123">See Also</span></span>

- [<span data-ttu-id="981a8-124">Microsoft.Quantum.Canon.ApplyWith</span><span class="sxs-lookup"><span data-stu-id="981a8-124">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)
- [<span data-ttu-id="981a8-125">Microsoft.Quantum.Canon.ApplyWithC</span><span class="sxs-lookup"><span data-stu-id="981a8-125">Microsoft.Quantum.Canon.ApplyWithC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithC)
- [<span data-ttu-id="981a8-126">Microsoft.Quantum.Canon.ApplyWithCA</span><span class="sxs-lookup"><span data-stu-id="981a8-126">Microsoft.Quantum.Canon.ApplyWithCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithCA)