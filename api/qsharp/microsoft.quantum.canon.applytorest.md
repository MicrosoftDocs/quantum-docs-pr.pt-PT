---
uid: Microsoft.Quantum.Canon.ApplyToRest
title: Aplicar operação OperaçãoTorest
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRest
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 29bf080d693c668421181f10faef50f5681683be
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717107"
---
# <a name="applytorest-operation"></a><span data-ttu-id="5eb23-102">Aplicar operação OperaçãoTorest</span><span class="sxs-lookup"><span data-stu-id="5eb23-102">ApplyToRest operation</span></span>

<span data-ttu-id="5eb23-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5eb23-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5eb23-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5eb23-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5eb23-105">Aplica uma operação a todos menos ao primeiro elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="5eb23-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRest<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="5eb23-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="5eb23-106">Description</span></span>

<span data-ttu-id="5eb23-107">Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="5eb23-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="5eb23-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="5eb23-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="5eb23-109">op : 'T[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="5eb23-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="5eb23-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="5eb23-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="5eb23-111">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="5eb23-111">targets : 'T[]</span></span>

<span data-ttu-id="5eb23-112">Uma série de alvos, dos quais todos, menos o primeiro, serão aplicados `op` a .</span><span class="sxs-lookup"><span data-stu-id="5eb23-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5eb23-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5eb23-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5eb23-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="5eb23-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5eb23-115">'T</span><span class="sxs-lookup"><span data-stu-id="5eb23-115">'T</span></span>

<span data-ttu-id="5eb23-116">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="5eb23-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="5eb23-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5eb23-117">See Also</span></span>

- [<span data-ttu-id="5eb23-118">Microsoft.Quantum.Canon.ApplyToresta</span><span class="sxs-lookup"><span data-stu-id="5eb23-118">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="5eb23-119">Microsoft.Quantum.Canon.ApplyTorestC</span><span class="sxs-lookup"><span data-stu-id="5eb23-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="5eb23-120">Microsoft.Quantum.Canon.applyTorestCA</span><span class="sxs-lookup"><span data-stu-id="5eb23-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)