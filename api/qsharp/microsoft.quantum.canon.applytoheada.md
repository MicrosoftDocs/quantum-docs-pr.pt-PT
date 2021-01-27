---
uid: Microsoft.Quantum.Canon.ApplyToHeadA
title: Aplicação Operação ToHeadA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 290347ff54492c4291db540e82cedcdd822a354e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850647"
---
# <a name="applytoheada-operation"></a><span data-ttu-id="b8653-102">Aplicação Operação ToHeadA</span><span class="sxs-lookup"><span data-stu-id="b8653-102">ApplyToHeadA operation</span></span>

<span data-ttu-id="b8653-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b8653-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b8653-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b8653-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b8653-105">Aplica uma operação ao primeiro elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="b8653-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="b8653-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="b8653-106">Description</span></span>

<span data-ttu-id="b8653-107">Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="b8653-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="b8653-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="b8653-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="b8653-109">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="b8653-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="b8653-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="b8653-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="b8653-111">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="b8653-111">targets : 'T[]</span></span>

<span data-ttu-id="b8653-112">Uma série de alvos, dos quais o primeiro será aplicado `op` .</span><span class="sxs-lookup"><span data-stu-id="b8653-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b8653-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b8653-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b8653-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="b8653-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b8653-115">'T</span><span class="sxs-lookup"><span data-stu-id="b8653-115">'T</span></span>

<span data-ttu-id="b8653-116">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="b8653-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="b8653-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b8653-117">See Also</span></span>

- [<span data-ttu-id="b8653-118">Microsoft.Quantum.Canon.ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="b8653-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="b8653-119">Microsoft.Quantum.Canon.ApplyToHeadc</span><span class="sxs-lookup"><span data-stu-id="b8653-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="b8653-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="b8653-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)