---
uid: Microsoft.Quantum.Canon.ApplyIfA
title: Operação ApplyIfA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfA
qsharp.summary: Applies a adjointable operation conditioned on a classical bit.
ms.openlocfilehash: d2880bbb95ebaf621ef9e5885051b94f32a3f1cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218772"
---
# <a name="applyifa-operation"></a><span data-ttu-id="2d937-102">Operação ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="2d937-102">ApplyIfA operation</span></span>

<span data-ttu-id="2d937-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2d937-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2d937-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2d937-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2d937-105">Aplica uma operação contígua condicionada a uma parte clássica.</span><span class="sxs-lookup"><span data-stu-id="2d937-105">Applies a adjointable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfA<'T> (op : ('T => Unit is Adj), bit : Bool, target : 'T) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="2d937-106">Description</span><span class="sxs-lookup"><span data-stu-id="2d937-106">Description</span></span>

<span data-ttu-id="2d937-107">Dada uma operação `op` e um pouco de `bit` valor, aplica-se `op` ao se é `target` `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="2d937-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="2d937-108">Se, `false` nada acontecer ao `target` .</span><span class="sxs-lookup"><span data-stu-id="2d937-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="2d937-109">O `A` sufixo indica que a operação a aplicar é adjacente.</span><span class="sxs-lookup"><span data-stu-id="2d937-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="2d937-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="2d937-110">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="2d937-111">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="2d937-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="2d937-112">Uma operação a ser aplicada condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="2d937-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="2d937-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2d937-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2d937-114">um booleano que controla se a operação é aplicada ou não.</span><span class="sxs-lookup"><span data-stu-id="2d937-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="2d937-115">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="2d937-115">target : 'T</span></span>

<span data-ttu-id="2d937-116">A entrada à qual a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="2d937-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2d937-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2d937-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2d937-118">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="2d937-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2d937-119">'T</span><span class="sxs-lookup"><span data-stu-id="2d937-119">'T</span></span>

<span data-ttu-id="2d937-120">O tipo de entrada da operação a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="2d937-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="2d937-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="2d937-121">See Also</span></span>

- [<span data-ttu-id="2d937-122">Microsoft.Quantum.Canon.ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="2d937-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="2d937-123">Microsoft.Quantum.Canon.ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="2d937-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="2d937-124">Microsoft.Quantum.Canon.ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="2d937-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)