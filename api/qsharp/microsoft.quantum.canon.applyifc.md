---
uid: Microsoft.Quantum.Canon.ApplyIfC
title: Operação ApplyIfC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfC
qsharp.summary: Applies a controllable operation conditioned on a classical bit.
ms.openlocfilehash: 35430cb7cf491965b7b69ace6d3f41599dbadd51
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218721"
---
# <a name="applyifc-operation"></a><span data-ttu-id="919dd-102">Operação ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="919dd-102">ApplyIfC operation</span></span>

<span data-ttu-id="919dd-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="919dd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="919dd-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="919dd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="919dd-105">Aplica uma operação controlável condicionada a uma parte clássica.</span><span class="sxs-lookup"><span data-stu-id="919dd-105">Applies a controllable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfC<'T> (op : ('T => Unit is Ctl), bit : Bool, target : 'T) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="919dd-106">Description</span><span class="sxs-lookup"><span data-stu-id="919dd-106">Description</span></span>

<span data-ttu-id="919dd-107">Dada uma operação `op` e um pouco de `bit` valor, aplica-se `op` ao se é `target` `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="919dd-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="919dd-108">Se, `false` nada acontecer ao `target` .</span><span class="sxs-lookup"><span data-stu-id="919dd-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="919dd-109">O `C` sufixo indica que a operação a aplicar é controlável.</span><span class="sxs-lookup"><span data-stu-id="919dd-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="919dd-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="919dd-110">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="919dd-111">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é CTL</span><span class="sxs-lookup"><span data-stu-id="919dd-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="919dd-112">Uma operação a ser aplicada condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="919dd-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="919dd-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="919dd-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="919dd-114">um booleano que controla se a operação é aplicada ou não.</span><span class="sxs-lookup"><span data-stu-id="919dd-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="919dd-115">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="919dd-115">target : 'T</span></span>

<span data-ttu-id="919dd-116">A entrada à qual a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="919dd-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="919dd-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="919dd-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="919dd-118">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="919dd-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="919dd-119">'T</span><span class="sxs-lookup"><span data-stu-id="919dd-119">'T</span></span>

<span data-ttu-id="919dd-120">O tipo de entrada da operação a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="919dd-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="919dd-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="919dd-121">See Also</span></span>

- [<span data-ttu-id="919dd-122">Microsoft.Quantum.Canon.ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="919dd-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="919dd-123">Microsoft.Quantum.Canon.ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="919dd-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="919dd-124">Microsoft.Quantum.Canon.ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="919dd-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)