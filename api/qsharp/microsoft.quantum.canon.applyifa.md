---
uid: Microsoft.Quantum.Canon.ApplyIfA
title: Operação ApplyIfA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfA
qsharp.summary: Applies a adjointable operation conditioned on a classical bit.
ms.openlocfilehash: 279a069176ee24ed83406f72170462bf58c790d9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718247"
---
# <a name="applyifa-operation"></a><span data-ttu-id="016fd-102">Operação ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="016fd-102">ApplyIfA operation</span></span>

<span data-ttu-id="016fd-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="016fd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="016fd-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="016fd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="016fd-105">Aplica uma operação contígua condicionada a uma parte clássica.</span><span class="sxs-lookup"><span data-stu-id="016fd-105">Applies a adjointable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfA<'T> (op : ('T => Unit is Adj), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="016fd-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="016fd-106">Description</span></span>

<span data-ttu-id="016fd-107">Dada uma operação `op` e um pouco de `bit` valor, aplica-se `op` ao se é `target` `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="016fd-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="016fd-108">Se, `false` nada acontecer ao `target` .</span><span class="sxs-lookup"><span data-stu-id="016fd-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="016fd-109">O `A` sufixo indica que a operação a aplicar é adjacente.</span><span class="sxs-lookup"><span data-stu-id="016fd-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="016fd-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="016fd-110">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="016fd-111">op : 'T = [Unit](xref:microsoft.quantum.lang-ref.unit) unidade> Adj</span><span class="sxs-lookup"><span data-stu-id="016fd-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="016fd-112">Uma operação a ser aplicada condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="016fd-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="016fd-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="016fd-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="016fd-114">um booleano que controla se a operação é aplicada ou não.</span><span class="sxs-lookup"><span data-stu-id="016fd-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="016fd-115">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="016fd-115">target : 'T</span></span>

<span data-ttu-id="016fd-116">A entrada à qual a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="016fd-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="016fd-117">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="016fd-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="016fd-118">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="016fd-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="016fd-119">'T</span><span class="sxs-lookup"><span data-stu-id="016fd-119">'T</span></span>

<span data-ttu-id="016fd-120">O tipo de entrada da operação a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="016fd-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="016fd-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="016fd-121">See Also</span></span>

- [<span data-ttu-id="016fd-122">Microsoft.Quantum.Canon.ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="016fd-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="016fd-123">Microsoft.Quantum.Canon.ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="016fd-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="016fd-124">Microsoft.Quantum.Canon.ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="016fd-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)