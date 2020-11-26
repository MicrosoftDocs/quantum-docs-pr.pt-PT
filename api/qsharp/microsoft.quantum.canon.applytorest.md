---
uid: Microsoft.Quantum.Canon.ApplyToRest
title: Aplicar operação OperaçãoTorest
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRest
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: fe49361f3c2259960eaa58d47df9b69b30b572a8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208275"
---
# <a name="applytorest-operation"></a><span data-ttu-id="d44d1-102">Aplicar operação OperaçãoTorest</span><span class="sxs-lookup"><span data-stu-id="d44d1-102">ApplyToRest operation</span></span>

<span data-ttu-id="d44d1-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d44d1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d44d1-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d44d1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d44d1-105">Aplica uma operação a todos menos ao primeiro elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="d44d1-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRest<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="d44d1-106">Description</span><span class="sxs-lookup"><span data-stu-id="d44d1-106">Description</span></span>

<span data-ttu-id="d44d1-107">Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="d44d1-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="d44d1-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="d44d1-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="d44d1-109">op : 'T[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="d44d1-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d44d1-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="d44d1-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="d44d1-111">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="d44d1-111">targets : 'T[]</span></span>

<span data-ttu-id="d44d1-112">Uma série de alvos, dos quais todos, menos o primeiro, serão aplicados `op` a .</span><span class="sxs-lookup"><span data-stu-id="d44d1-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d44d1-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d44d1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d44d1-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="d44d1-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d44d1-115">'T</span><span class="sxs-lookup"><span data-stu-id="d44d1-115">'T</span></span>

<span data-ttu-id="d44d1-116">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="d44d1-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="d44d1-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d44d1-117">See Also</span></span>

- [<span data-ttu-id="d44d1-118">Microsoft.Quantum.Canon.ApplyToresta</span><span class="sxs-lookup"><span data-stu-id="d44d1-118">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="d44d1-119">Microsoft.Quantum.Canon.ApplyTorestC</span><span class="sxs-lookup"><span data-stu-id="d44d1-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="d44d1-120">Microsoft.Quantum.Canon.applyTorestCA</span><span class="sxs-lookup"><span data-stu-id="d44d1-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)