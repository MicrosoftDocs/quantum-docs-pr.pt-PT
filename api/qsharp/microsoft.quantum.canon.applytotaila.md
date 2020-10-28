---
uid: Microsoft.Quantum.Canon.ApplyToTailA
title: Aplicar operaçãoToTailA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: a84fa6c53f3e11bef82b8b83fffa1451a8299511
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716978"
---
# <a name="applytotaila-operation"></a><span data-ttu-id="9614a-102">Aplicar operaçãoToTailA</span><span class="sxs-lookup"><span data-stu-id="9614a-102">ApplyToTailA operation</span></span>

<span data-ttu-id="9614a-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9614a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9614a-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9614a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9614a-105">Aplica uma operação ao último elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="9614a-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="9614a-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="9614a-106">Description</span></span>

<span data-ttu-id="9614a-107">Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="9614a-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="9614a-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="9614a-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="9614a-109">op : 'T = [Unit](xref:microsoft.quantum.lang-ref.unit) unidade> Adj</span><span class="sxs-lookup"><span data-stu-id="9614a-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="9614a-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="9614a-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="9614a-111">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="9614a-111">targets : 'T[]</span></span>

<span data-ttu-id="9614a-112">Uma série de alvos, dos quais o último será aplicado `op` .</span><span class="sxs-lookup"><span data-stu-id="9614a-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9614a-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9614a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9614a-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="9614a-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9614a-115">'T</span><span class="sxs-lookup"><span data-stu-id="9614a-115">'T</span></span>

<span data-ttu-id="9614a-116">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="9614a-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="9614a-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9614a-117">See Also</span></span>

- [<span data-ttu-id="9614a-118">Microsoft.Quantum.Canon.ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="9614a-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="9614a-119">Microsoft.Quantum.Canon.ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="9614a-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="9614a-120">Microsoft.Quantum.Canon.ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="9614a-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)