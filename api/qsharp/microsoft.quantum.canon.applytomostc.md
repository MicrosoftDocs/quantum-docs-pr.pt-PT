---
uid: Microsoft.Quantum.Canon.ApplyToMostC
title: Aplicação OperaçãoToMostC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostC
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 14de9f367aa7d19f64f13186d402239ae1fef3c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850564"
---
# <a name="applytomostc-operation"></a><span data-ttu-id="8ab62-102">Aplicação OperaçãoToMostC</span><span class="sxs-lookup"><span data-stu-id="8ab62-102">ApplyToMostC operation</span></span>

<span data-ttu-id="8ab62-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8ab62-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8ab62-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8ab62-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8ab62-105">Aplica uma operação a todos, menos ao último elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="8ab62-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="8ab62-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="8ab62-106">Description</span></span>

<span data-ttu-id="8ab62-107">Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="8ab62-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="8ab62-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="8ab62-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="8ab62-109">op : 'T[] = [> Unidade](xref:microsoft.quantum.lang-ref.unit)  é CTL</span><span class="sxs-lookup"><span data-stu-id="8ab62-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="8ab62-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="8ab62-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="8ab62-111">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="8ab62-111">targets : 'T[]</span></span>

<span data-ttu-id="8ab62-112">Uma série de alvos, dos quais todos, menos o último, serão aplicados `op` a .</span><span class="sxs-lookup"><span data-stu-id="8ab62-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8ab62-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8ab62-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8ab62-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="8ab62-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8ab62-115">'T</span><span class="sxs-lookup"><span data-stu-id="8ab62-115">'T</span></span>

<span data-ttu-id="8ab62-116">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="8ab62-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ab62-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8ab62-117">See Also</span></span>

- [<span data-ttu-id="8ab62-118">Microsoft.Quantum.Canon.ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="8ab62-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="8ab62-119">Microsoft.Quantum.Canon.ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="8ab62-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="8ab62-120">Microsoft.Quantum.Canon.ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="8ab62-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)