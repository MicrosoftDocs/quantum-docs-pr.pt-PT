---
uid: Microsoft.Quantum.Canon.ApplyToMost
title: AplicaçãoToMosta operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMost
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: a3918233e101f3d8956601dcc7d85edcf6196ac7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850597"
---
# <a name="applytomost-operation"></a><span data-ttu-id="d9898-102">AplicaçãoToMosta operação</span><span class="sxs-lookup"><span data-stu-id="d9898-102">ApplyToMost operation</span></span>

<span data-ttu-id="d9898-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d9898-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d9898-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d9898-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d9898-105">Aplica uma operação a todos, menos ao último elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="d9898-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMost<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="d9898-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="d9898-106">Description</span></span>

<span data-ttu-id="d9898-107">Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="d9898-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="d9898-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="d9898-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="d9898-109">op : 'T[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="d9898-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d9898-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="d9898-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="d9898-111">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="d9898-111">targets : 'T[]</span></span>

<span data-ttu-id="d9898-112">Uma série de alvos, dos quais todos, menos o último, serão aplicados `op` a .</span><span class="sxs-lookup"><span data-stu-id="d9898-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d9898-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d9898-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d9898-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="d9898-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d9898-115">'T</span><span class="sxs-lookup"><span data-stu-id="d9898-115">'T</span></span>

<span data-ttu-id="d9898-116">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="d9898-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="d9898-117">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d9898-117">Example</span></span>

<span data-ttu-id="d9898-118">Os seguintes cortes Q# são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="d9898-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToMost(ApplyCNOTChain, register);
ApplyCNOTChain(Most(register));
```

## <a name="see-also"></a><span data-ttu-id="d9898-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d9898-119">See Also</span></span>

- [<span data-ttu-id="d9898-120">Microsoft.Quantum.Canon.ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="d9898-120">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="d9898-121">Microsoft.Quantum.Canon.ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="d9898-121">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="d9898-122">Microsoft.Quantum.Canon.ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="d9898-122">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)