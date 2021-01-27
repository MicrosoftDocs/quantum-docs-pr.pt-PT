---
uid: Microsoft.Quantum.Canon.ApplyToRestC
title: Aplicar operaçãoToRestC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestC
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 1e533a9f0994b70054aeca2f9ddd97f4e200b03f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850500"
---
# <a name="applytorestc-operation"></a><span data-ttu-id="fb5b1-102">Aplicar operaçãoToRestC</span><span class="sxs-lookup"><span data-stu-id="fb5b1-102">ApplyToRestC operation</span></span>

<span data-ttu-id="fb5b1-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fb5b1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fb5b1-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fb5b1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fb5b1-105">Aplica uma operação a todos menos ao primeiro elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="fb5b1-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="fb5b1-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="fb5b1-106">Description</span></span>

<span data-ttu-id="fb5b1-107">Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="fb5b1-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="fb5b1-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="fb5b1-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="fb5b1-109">op : 'T[] = [> Unidade](xref:microsoft.quantum.lang-ref.unit)  é CTL</span><span class="sxs-lookup"><span data-stu-id="fb5b1-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="fb5b1-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="fb5b1-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="fb5b1-111">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="fb5b1-111">targets : 'T[]</span></span>

<span data-ttu-id="fb5b1-112">Uma série de alvos, dos quais todos, menos o primeiro, serão aplicados `op` a .</span><span class="sxs-lookup"><span data-stu-id="fb5b1-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fb5b1-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fb5b1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fb5b1-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="fb5b1-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fb5b1-115">'T</span><span class="sxs-lookup"><span data-stu-id="fb5b1-115">'T</span></span>

<span data-ttu-id="fb5b1-116">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="fb5b1-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb5b1-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="fb5b1-117">See Also</span></span>

- [<span data-ttu-id="fb5b1-118">Microsoft.Quantum.Canon.ApplyTorest</span><span class="sxs-lookup"><span data-stu-id="fb5b1-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="fb5b1-119">Microsoft.Quantum.Canon.ApplyToresta</span><span class="sxs-lookup"><span data-stu-id="fb5b1-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="fb5b1-120">Microsoft.Quantum.Canon.applyTorestCA</span><span class="sxs-lookup"><span data-stu-id="fb5b1-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)