---
uid: Microsoft.Quantum.Canon.ConjugatedBy
title: Função ConjugatedBy
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedBy
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: 37fbee9a7c11991645933a372f9f12c1fd696b66
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716474"
---
# <a name="conjugatedby-function"></a><span data-ttu-id="18f3e-102">Função ConjugatedBy</span><span class="sxs-lookup"><span data-stu-id="18f3e-102">ConjugatedBy function</span></span>

<span data-ttu-id="18f3e-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="18f3e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="18f3e-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="18f3e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="18f3e-105">Dadas as operações exteriores e interiores, devolve uma nova operação que conjuga a operação interna pela operação exterior.</span><span class="sxs-lookup"><span data-stu-id="18f3e-105">Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.</span></span>

```qsharp
function ConjugatedBy<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit)) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="18f3e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="18f3e-106">Input</span></span>

### <a name="outeroperation--t--unit-adj"></a><span data-ttu-id="18f3e-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span><span class="sxs-lookup"><span data-stu-id="18f3e-107">outerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="18f3e-108">A operação $U$ que deve ser usada para conjugar $V dólares.</span><span class="sxs-lookup"><span data-stu-id="18f3e-108">The operation $U$ that should be used to conjugate $V$.</span></span> <span data-ttu-id="18f3e-109">Note que a operação exterior $U$ tem de ser adjacente, mas não precisa de ser controlável.</span><span class="sxs-lookup"><span data-stu-id="18f3e-109">Note that the outer operation $U$ needs to be adjointable, but does not need to be controllable.</span></span>


### <a name="inneroperation--t--unit"></a><span data-ttu-id="18f3e-110">inoperação interior : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="18f3e-110">innerOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="18f3e-111">A operação $V dólares a ser conjugada.</span><span class="sxs-lookup"><span data-stu-id="18f3e-111">The operation $V$ being conjugated.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="18f3e-112">Saída : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="18f3e-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="18f3e-113">Uma nova operação cuja ação é representada pelo $U^{\dagger} V U$.</span><span class="sxs-lookup"><span data-stu-id="18f3e-113">A new operation whose action is represented by the unitary $U^{\dagger} V U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="18f3e-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="18f3e-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="18f3e-115">'T</span><span class="sxs-lookup"><span data-stu-id="18f3e-115">'T</span></span>

<span data-ttu-id="18f3e-116">O tipo de alvo em que cada uma das operações internas e exteriores atuam.</span><span class="sxs-lookup"><span data-stu-id="18f3e-116">The type of the target on which each of the inner and outer operations act.</span></span>

## <a name="remarks"></a><span data-ttu-id="18f3e-117">Observações</span><span class="sxs-lookup"><span data-stu-id="18f3e-117">Remarks</span></span>

<span data-ttu-id="18f3e-118">Presume-se sempre que a operação exterior é contígua, mas não é necessário controlável para que a operação combinada seja controlável.</span><span class="sxs-lookup"><span data-stu-id="18f3e-118">The outer operation is always assumed to be adjointable, but does not need to be controllable in order for the combined operation to be controllable.</span></span>

## <a name="see-also"></a><span data-ttu-id="18f3e-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="18f3e-119">See Also</span></span>

- [<span data-ttu-id="18f3e-120">Microsoft.Quantum.Canon.conjugatedBya</span><span class="sxs-lookup"><span data-stu-id="18f3e-120">Microsoft.Quantum.Canon.ConjugatedByA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [<span data-ttu-id="18f3e-121">Microsoft.Quantum.Canon.ConjugatedByC</span><span class="sxs-lookup"><span data-stu-id="18f3e-121">Microsoft.Quantum.Canon.ConjugatedByC</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [<span data-ttu-id="18f3e-122">Microsoft.Quantum.Canon.ConjugatedByCA</span><span class="sxs-lookup"><span data-stu-id="18f3e-122">Microsoft.Quantum.Canon.ConjugatedByCA</span></span>](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [<span data-ttu-id="18f3e-123">Microsoft.Quantum.Canon.ApplyWith</span><span class="sxs-lookup"><span data-stu-id="18f3e-123">Microsoft.Quantum.Canon.ApplyWith</span></span>](xref:Microsoft.Quantum.Canon.ApplyWith)