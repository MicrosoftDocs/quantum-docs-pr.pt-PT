---
uid: Microsoft.Quantum.Canon.ApplyToTailC
title: Aplicar operaçãoToTailC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailC
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 8408dff24c5c57efbedb649ac182fac49e836a3e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850424"
---
# <a name="applytotailc-operation"></a><span data-ttu-id="1e49f-102">Aplicar operaçãoToTailC</span><span class="sxs-lookup"><span data-stu-id="1e49f-102">ApplyToTailC operation</span></span>

<span data-ttu-id="1e49f-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1e49f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1e49f-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1e49f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1e49f-105">Aplica uma operação ao último elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="1e49f-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="1e49f-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="1e49f-106">Description</span></span>

<span data-ttu-id="1e49f-107">Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="1e49f-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="1e49f-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="1e49f-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="1e49f-109">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é CTL</span><span class="sxs-lookup"><span data-stu-id="1e49f-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="1e49f-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="1e49f-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="1e49f-111">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="1e49f-111">targets : 'T[]</span></span>

<span data-ttu-id="1e49f-112">Uma série de alvos, dos quais o último será aplicado `op` .</span><span class="sxs-lookup"><span data-stu-id="1e49f-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1e49f-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1e49f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1e49f-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="1e49f-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1e49f-115">'T</span><span class="sxs-lookup"><span data-stu-id="1e49f-115">'T</span></span>

<span data-ttu-id="1e49f-116">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="1e49f-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e49f-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1e49f-117">See Also</span></span>

- [<span data-ttu-id="1e49f-118">Microsoft.Quantum.Canon.ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="1e49f-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="1e49f-119">Microsoft.Quantum.Canon.ApplyToTaila</span><span class="sxs-lookup"><span data-stu-id="1e49f-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="1e49f-120">Microsoft.Quantum.Canon.ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="1e49f-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)