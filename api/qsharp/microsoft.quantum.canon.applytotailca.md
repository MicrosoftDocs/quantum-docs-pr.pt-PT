---
uid: Microsoft.Quantum.Canon.ApplyToTailCA
title: Aplicar operaçãoToTailCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailCA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: afb9eaa277814d7434b00a5c853a0c002190c1ae
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207858"
---
# <a name="applytotailca-operation"></a><span data-ttu-id="88002-102">Aplicar operaçãoToTailCA</span><span class="sxs-lookup"><span data-stu-id="88002-102">ApplyToTailCA operation</span></span>

<span data-ttu-id="88002-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="88002-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="88002-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="88002-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="88002-105">Aplica uma operação ao último elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="88002-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="88002-106">Description</span><span class="sxs-lookup"><span data-stu-id="88002-106">Description</span></span>

<span data-ttu-id="88002-107">Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="88002-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="88002-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="88002-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="88002-109">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="88002-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="88002-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="88002-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="88002-111">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="88002-111">targets : 'T[]</span></span>

<span data-ttu-id="88002-112">Uma série de alvos, dos quais o último será aplicado `op` .</span><span class="sxs-lookup"><span data-stu-id="88002-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="88002-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="88002-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="88002-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="88002-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="88002-115">'T</span><span class="sxs-lookup"><span data-stu-id="88002-115">'T</span></span>

<span data-ttu-id="88002-116">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="88002-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="88002-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="88002-117">See Also</span></span>

- [<span data-ttu-id="88002-118">Microsoft.Quantum.Canon.ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="88002-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="88002-119">Microsoft.Quantum.Canon.ApplyToTaila</span><span class="sxs-lookup"><span data-stu-id="88002-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="88002-120">Microsoft.Quantum.Canon.ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="88002-120">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)