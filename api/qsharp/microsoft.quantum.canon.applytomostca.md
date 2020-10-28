---
uid: Microsoft.Quantum.Canon.ApplyToMostCA
title: Aplicação Da OperaçãoMostCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostCA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 797cbd835446f31b2df60dbb184f888e6d0356aa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717163"
---
# <a name="applytomostca-operation"></a><span data-ttu-id="e778c-102">Aplicação Da OperaçãoMostCA</span><span class="sxs-lookup"><span data-stu-id="e778c-102">ApplyToMostCA operation</span></span>

<span data-ttu-id="e778c-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e778c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e778c-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e778c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e778c-105">Aplica uma operação a todos, menos ao último elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="e778c-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="e778c-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="e778c-106">Description</span></span>

<span data-ttu-id="e778c-107">Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="e778c-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="e778c-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="e778c-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="e778c-109">op : 'T[] => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="e778c-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="e778c-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="e778c-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="e778c-111">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="e778c-111">targets : 'T[]</span></span>

<span data-ttu-id="e778c-112">Uma série de alvos, dos quais todos, menos o último, serão aplicados `op` a .</span><span class="sxs-lookup"><span data-stu-id="e778c-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e778c-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e778c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e778c-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="e778c-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e778c-115">'T</span><span class="sxs-lookup"><span data-stu-id="e778c-115">'T</span></span>

<span data-ttu-id="e778c-116">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="e778c-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="e778c-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e778c-117">See Also</span></span>

- [<span data-ttu-id="e778c-118">Microsoft.Quantum.Canon.ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="e778c-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="e778c-119">Microsoft.Quantum.Canon.ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="e778c-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="e778c-120">Microsoft.Quantum.Canon.ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="e778c-120">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)