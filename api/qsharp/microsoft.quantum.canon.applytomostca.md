---
uid: Microsoft.Quantum.Canon.ApplyToMostCA
title: Aplicação Da OperaçãoMostCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostCA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 0a80c23e0c6ff45083c192579dd8301d2277cef2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841318"
---
# <a name="applytomostca-operation"></a><span data-ttu-id="14e24-102">Aplicação Da OperaçãoMostCA</span><span class="sxs-lookup"><span data-stu-id="14e24-102">ApplyToMostCA operation</span></span>

<span data-ttu-id="14e24-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="14e24-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="14e24-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="14e24-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="14e24-105">Aplica uma operação a todos, menos ao último elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="14e24-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="14e24-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="14e24-106">Description</span></span>

<span data-ttu-id="14e24-107">Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="14e24-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="14e24-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="14e24-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="14e24-109">op : 'T[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="14e24-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="14e24-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="14e24-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="14e24-111">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="14e24-111">targets : 'T[]</span></span>

<span data-ttu-id="14e24-112">Uma série de alvos, dos quais todos, menos o último, serão aplicados `op` a .</span><span class="sxs-lookup"><span data-stu-id="14e24-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="14e24-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="14e24-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="14e24-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="14e24-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="14e24-115">'T</span><span class="sxs-lookup"><span data-stu-id="14e24-115">'T</span></span>

<span data-ttu-id="14e24-116">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="14e24-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="14e24-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="14e24-117">See Also</span></span>

- [<span data-ttu-id="14e24-118">Microsoft.Quantum.Canon.ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="14e24-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="14e24-119">Microsoft.Quantum.Canon.ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="14e24-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="14e24-120">Microsoft.Quantum.Canon.ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="14e24-120">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)