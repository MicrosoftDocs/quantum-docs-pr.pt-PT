---
uid: Microsoft.Quantum.Canon.ApplyToRestA
title: Aplicar operaçãoTorestA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 34cb5071dd939d0831e39bb8f1670670ae1fad31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208312"
---
# <a name="applytoresta-operation"></a><span data-ttu-id="5ff67-102">Aplicar operaçãoTorestA</span><span class="sxs-lookup"><span data-stu-id="5ff67-102">ApplyToRestA operation</span></span>

<span data-ttu-id="5ff67-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5ff67-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5ff67-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5ff67-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5ff67-105">Aplica uma operação a todos menos ao primeiro elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="5ff67-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="5ff67-106">Description</span><span class="sxs-lookup"><span data-stu-id="5ff67-106">Description</span></span>

<span data-ttu-id="5ff67-107">Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="5ff67-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="5ff67-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="5ff67-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="5ff67-109">op : 'T[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="5ff67-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="5ff67-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="5ff67-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="5ff67-111">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="5ff67-111">targets : 'T[]</span></span>

<span data-ttu-id="5ff67-112">Uma série de alvos, dos quais todos, menos o primeiro, serão aplicados `op` a .</span><span class="sxs-lookup"><span data-stu-id="5ff67-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5ff67-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5ff67-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5ff67-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="5ff67-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5ff67-115">'T</span><span class="sxs-lookup"><span data-stu-id="5ff67-115">'T</span></span>

<span data-ttu-id="5ff67-116">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="5ff67-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ff67-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5ff67-117">See Also</span></span>

- [<span data-ttu-id="5ff67-118">Microsoft.Quantum.Canon.ApplyTorest</span><span class="sxs-lookup"><span data-stu-id="5ff67-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="5ff67-119">Microsoft.Quantum.Canon.ApplyTorestC</span><span class="sxs-lookup"><span data-stu-id="5ff67-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="5ff67-120">Microsoft.Quantum.Canon.applyTorestCA</span><span class="sxs-lookup"><span data-stu-id="5ff67-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)