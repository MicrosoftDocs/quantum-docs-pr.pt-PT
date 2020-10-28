---
uid: Microsoft.Quantum.Canon.ConjugatedByC
title: Função ConjugatedByC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByC
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: c4c381e40c5a941487bcf78ebe5339574aedb45d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716460"
---
# <a name="conjugatedbyc-function"></a><span data-ttu-id="586ae-102">Função ConjugatedByC</span><span class="sxs-lookup"><span data-stu-id="586ae-102">ConjugatedByC function</span></span>

<span data-ttu-id="586ae-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="586ae-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="586ae-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="586ae-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="586ae-105">Dadas as operações exteriores e interiores, devolve uma nova operação que conjuga a operação interna pela operação exterior.</span><span class="sxs-lookup"><span data-stu-id="586ae-105">Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.</span></span>

```qsharp
function ConjugatedByC<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Ctl)) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="586ae-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="586ae-106">Input</span></span>

### <a name="outeroperation--t--unit-adj"></a><span data-ttu-id="586ae-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span><span class="sxs-lookup"><span data-stu-id="586ae-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="586ae-108">A operação $U$ que deve ser usada para conjugar $V dólares.</span><span class="sxs-lookup"><span data-stu-id="586ae-108">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="586ae-109">Note que a operação exterior $U$ tem de ser adjacente, mas não precisa de ser controlável.</span><span class="sxs-lookup"><span data-stu-id="586ae-109">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit-ctl"></a><span data-ttu-id="586ae-110">inoperação interna : 'T => [Unidade](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="586ae-110">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="586ae-111">A operação $V dólares a ser conjugada.</span><span class="sxs-lookup"><span data-stu-id="586ae-111">The operation $V$ being conjugated.</span></span>



## <a name="output--t--unit-ctl"></a><span data-ttu-id="586ae-112">Saída : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit)> Ctl</span><span class="sxs-lookup"><span data-stu-id="586ae-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="586ae-113">Uma nova operação cuja ação é representada pelo $U^{\dagger} V U$.</span><span class="sxs-lookup"><span data-stu-id="586ae-113">A new operation whose action is represented by the unitary $U^{\dagger} V U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="586ae-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="586ae-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="586ae-115">'T</span><span class="sxs-lookup"><span data-stu-id="586ae-115">'T</span></span>

<span data-ttu-id="586ae-116">O tipo de alvo em que cada uma das operações internas e exteriores atuam.</span><span class="sxs-lookup"><span data-stu-id="586ae-116">The type of the target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="586ae-117">Observações</span><span class="sxs-lookup"><span data-stu-id="586ae-117">Remarks</span></span>

<span data-ttu-id="586ae-118">Presume-se sempre que a operação exterior é contígua, mas não é necessário controlável para que a operação combinada seja controlável.</span><span class="sxs-lookup"><span data-stu-id="586ae-118">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="586ae-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="586ae-119">See Also</span></span>

- [<span data-ttu-id="586ae-120">Microsoft.Quantum.Canon.ConjugatedBy</span><span class="sxs-lookup"><span data-stu-id="586ae-120">Microsoft.Quantum.Canon.ConjugatedBy</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedBy)
- [<span data-ttu-id="586ae-121">Microsoft.Quantum.Canon.conjugatedBya</span><span class="sxs-lookup"><span data-stu-id="586ae-121">Microsoft.Quantum.Canon.ConjugatedByA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [<span data-ttu-id="586ae-122">Microsoft.Quantum.Canon.ConjugatedByCA</span><span class="sxs-lookup"><span data-stu-id="586ae-122">Microsoft.Quantum.Canon.ConjugatedByCA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [<span data-ttu-id="586ae-123">Microsoft.Quantum.Canon.ApplyWith</span><span class="sxs-lookup"><span data-stu-id="586ae-123">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)