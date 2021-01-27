---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: Aplicar operação ToHead
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 4e627b467e9354e774c2ead8b89ddd3ff3a42ef7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841326"
---
# <a name="applytohead-operation"></a><span data-ttu-id="f00bc-102">Aplicar operação ToHead</span><span class="sxs-lookup"><span data-stu-id="f00bc-102">ApplyToHead operation</span></span>

<span data-ttu-id="f00bc-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f00bc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f00bc-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f00bc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f00bc-105">Aplica uma operação ao primeiro elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="f00bc-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHead<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="f00bc-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="f00bc-106">Description</span></span>

<span data-ttu-id="f00bc-107">Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="f00bc-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="f00bc-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="f00bc-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="f00bc-109">op : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="f00bc-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f00bc-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="f00bc-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="f00bc-111">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="f00bc-111">targets : 'T[]</span></span>

<span data-ttu-id="f00bc-112">Uma série de alvos, dos quais o primeiro será aplicado `op` .</span><span class="sxs-lookup"><span data-stu-id="f00bc-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f00bc-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f00bc-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f00bc-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="f00bc-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f00bc-115">'T</span><span class="sxs-lookup"><span data-stu-id="f00bc-115">'T</span></span>

<span data-ttu-id="f00bc-116">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="f00bc-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="f00bc-117">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f00bc-117">Example</span></span>

<span data-ttu-id="f00bc-118">Os seguintes cortes Q# são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="f00bc-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToHead(H, register);
H(Head(register));
```

## <a name="see-also"></a><span data-ttu-id="f00bc-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f00bc-119">See Also</span></span>

- [<span data-ttu-id="f00bc-120">Microsoft.Quantum.Canon.ApplyToHeada</span><span class="sxs-lookup"><span data-stu-id="f00bc-120">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="f00bc-121">Microsoft.Quantum.Canon.ApplyToHeadc</span><span class="sxs-lookup"><span data-stu-id="f00bc-121">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="f00bc-122">Microsoft.Quantum.Canon.ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="f00bc-122">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)