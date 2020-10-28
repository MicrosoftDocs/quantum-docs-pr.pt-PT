---
uid: Microsoft.Quantum.Canon.ApplyToHeadA
title: Aplicação Operação ToHeadA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: ba060243cb01782fd8529e0b05ee7258a66314f5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717258"
---
# <a name="applytoheada-operation"></a><span data-ttu-id="45aa5-102">Aplicação Operação ToHeadA</span><span class="sxs-lookup"><span data-stu-id="45aa5-102">ApplyToHeadA operation</span></span>

<span data-ttu-id="45aa5-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="45aa5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="45aa5-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="45aa5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="45aa5-105">Aplica uma operação ao primeiro elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="45aa5-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="45aa5-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="45aa5-106">Description</span></span>

<span data-ttu-id="45aa5-107">Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="45aa5-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="45aa5-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="45aa5-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="45aa5-109">op : 'T = [Unit](xref:microsoft.quantum.lang-ref.unit) unidade> Adj</span><span class="sxs-lookup"><span data-stu-id="45aa5-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="45aa5-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="45aa5-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="45aa5-111">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="45aa5-111">targets : 'T[]</span></span>

<span data-ttu-id="45aa5-112">Uma série de alvos, dos quais o primeiro será aplicado `op` .</span><span class="sxs-lookup"><span data-stu-id="45aa5-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="45aa5-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="45aa5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="45aa5-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="45aa5-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="45aa5-115">'T</span><span class="sxs-lookup"><span data-stu-id="45aa5-115">'T</span></span>

<span data-ttu-id="45aa5-116">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="45aa5-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="45aa5-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="45aa5-117">See Also</span></span>

- [<span data-ttu-id="45aa5-118">Microsoft.Quantum.Canon.ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="45aa5-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="45aa5-119">Microsoft.Quantum.Canon.ApplyToHeadc</span><span class="sxs-lookup"><span data-stu-id="45aa5-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="45aa5-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="45aa5-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)