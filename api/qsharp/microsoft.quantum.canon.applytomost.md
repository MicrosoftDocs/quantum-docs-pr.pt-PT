---
uid: Microsoft.Quantum.Canon.ApplyToMost
title: AplicaçãoToMosta operação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMost
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 2c6c8873859439e71436f6beb0de40dfd1e21f43
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717230"
---
# <a name="applytomost-operation"></a><span data-ttu-id="4c428-102">AplicaçãoToMosta operação</span><span class="sxs-lookup"><span data-stu-id="4c428-102">ApplyToMost operation</span></span>

<span data-ttu-id="4c428-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4c428-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4c428-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4c428-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4c428-105">Aplica uma operação a todos, menos ao último elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="4c428-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMost<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="4c428-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="4c428-106">Description</span></span>

<span data-ttu-id="4c428-107">Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="4c428-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="4c428-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="4c428-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="4c428-109">op : 'T[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="4c428-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4c428-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="4c428-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="4c428-111">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="4c428-111">targets : 'T[]</span></span>

<span data-ttu-id="4c428-112">Uma série de alvos, dos quais todos, menos o último, serão aplicados `op` a .</span><span class="sxs-lookup"><span data-stu-id="4c428-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4c428-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4c428-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4c428-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="4c428-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4c428-115">'T</span><span class="sxs-lookup"><span data-stu-id="4c428-115">'T</span></span>

<span data-ttu-id="4c428-116">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="4c428-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c428-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4c428-117">See Also</span></span>

- [<span data-ttu-id="4c428-118">Microsoft.Quantum.Canon.ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="4c428-118">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="4c428-119">Microsoft.Quantum.Canon.ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="4c428-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="4c428-120">Microsoft.Quantum.Canon.ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="4c428-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)