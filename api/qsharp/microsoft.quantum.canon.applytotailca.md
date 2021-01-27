---
uid: Microsoft.Quantum.Canon.ApplyToTailCA
title: Aplicar operaçãoToTailCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailCA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 4c702a9d310adae7a4ec404f3cf12893547623b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841189"
---
# <a name="applytotailca-operation"></a><span data-ttu-id="99f93-102">Aplicar operaçãoToTailCA</span><span class="sxs-lookup"><span data-stu-id="99f93-102">ApplyToTailCA operation</span></span>

<span data-ttu-id="99f93-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="99f93-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="99f93-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="99f93-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="99f93-105">Aplica uma operação ao último elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="99f93-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="99f93-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="99f93-106">Description</span></span>

<span data-ttu-id="99f93-107">Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="99f93-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="99f93-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="99f93-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="99f93-109">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="99f93-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="99f93-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="99f93-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="99f93-111">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="99f93-111">targets : 'T[]</span></span>

<span data-ttu-id="99f93-112">Uma série de alvos, dos quais o último será aplicado `op` .</span><span class="sxs-lookup"><span data-stu-id="99f93-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="99f93-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="99f93-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="99f93-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="99f93-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="99f93-115">'T</span><span class="sxs-lookup"><span data-stu-id="99f93-115">'T</span></span>

<span data-ttu-id="99f93-116">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="99f93-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="99f93-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="99f93-117">See Also</span></span>

- [<span data-ttu-id="99f93-118">Microsoft.Quantum.Canon.ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="99f93-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="99f93-119">Microsoft.Quantum.Canon.ApplyToTaila</span><span class="sxs-lookup"><span data-stu-id="99f93-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="99f93-120">Microsoft.Quantum.Canon.ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="99f93-120">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)