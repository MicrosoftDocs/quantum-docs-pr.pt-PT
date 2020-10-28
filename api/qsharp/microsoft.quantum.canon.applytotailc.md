---
uid: Microsoft.Quantum.Canon.ApplyToTailC
title: Aplicar operaçãoToTailC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailC
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 631e08666002d8077c6f8b78525b06b104dd4c7c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716967"
---
# <a name="applytotailc-operation"></a><span data-ttu-id="7bca7-102">Aplicar operaçãoToTailC</span><span class="sxs-lookup"><span data-stu-id="7bca7-102">ApplyToTailC operation</span></span>

<span data-ttu-id="7bca7-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7bca7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7bca7-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7bca7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7bca7-105">Aplica uma operação ao último elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="7bca7-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="7bca7-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="7bca7-106">Description</span></span>

<span data-ttu-id="7bca7-107">Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="7bca7-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="7bca7-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="7bca7-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="7bca7-109">op : 'T => [Unidade](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="7bca7-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="7bca7-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="7bca7-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="7bca7-111">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="7bca7-111">targets : 'T[]</span></span>

<span data-ttu-id="7bca7-112">Uma série de alvos, dos quais o último será aplicado `op` .</span><span class="sxs-lookup"><span data-stu-id="7bca7-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7bca7-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7bca7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7bca7-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="7bca7-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7bca7-115">'T</span><span class="sxs-lookup"><span data-stu-id="7bca7-115">'T</span></span>

<span data-ttu-id="7bca7-116">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="7bca7-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="7bca7-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7bca7-117">See Also</span></span>

- [<span data-ttu-id="7bca7-118">Microsoft.Quantum.Canon.ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="7bca7-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="7bca7-119">Microsoft.Quantum.Canon.ApplyToTaila</span><span class="sxs-lookup"><span data-stu-id="7bca7-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="7bca7-120">Microsoft.Quantum.Canon.ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="7bca7-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)