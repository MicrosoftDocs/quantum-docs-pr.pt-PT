---
uid: Microsoft.Quantum.Canon.ApplyToMostA
title: Aplicação OperaçãoToMostA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 7c226de9b2c99d124c467175dfe65a60a89d4332
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208504"
---
# <a name="applytomosta-operation"></a><span data-ttu-id="f8a2b-102">Aplicação OperaçãoToMostA</span><span class="sxs-lookup"><span data-stu-id="f8a2b-102">ApplyToMostA operation</span></span>

<span data-ttu-id="f8a2b-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f8a2b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f8a2b-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f8a2b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f8a2b-105">Aplica uma operação a todos, menos ao último elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="f8a2b-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="f8a2b-106">Description</span><span class="sxs-lookup"><span data-stu-id="f8a2b-106">Description</span></span>

<span data-ttu-id="f8a2b-107">Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="f8a2b-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="f8a2b-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="f8a2b-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="f8a2b-109">op : 'T[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="f8a2b-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="f8a2b-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="f8a2b-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="f8a2b-111">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="f8a2b-111">targets : 'T[]</span></span>

<span data-ttu-id="f8a2b-112">Uma série de alvos, dos quais todos, menos o último, serão aplicados `op` a .</span><span class="sxs-lookup"><span data-stu-id="f8a2b-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f8a2b-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f8a2b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f8a2b-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="f8a2b-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f8a2b-115">'T</span><span class="sxs-lookup"><span data-stu-id="f8a2b-115">'T</span></span>

<span data-ttu-id="f8a2b-116">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="f8a2b-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8a2b-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f8a2b-117">See Also</span></span>

- [<span data-ttu-id="f8a2b-118">Microsoft.Quantum.Canon.ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="f8a2b-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="f8a2b-119">Microsoft.Quantum.Canon.ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="f8a2b-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="f8a2b-120">Microsoft.Quantum.Canon.ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="f8a2b-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)