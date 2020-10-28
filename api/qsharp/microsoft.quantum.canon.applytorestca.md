---
uid: Microsoft.Quantum.Canon.ApplyToRestCA
title: Aplicação OperaçãoToRestCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestCA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: d2dc10803044980d53f80f0577d16cb14a2eb301
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717065"
---
# <a name="applytorestca-operation"></a><span data-ttu-id="a48a2-102">Aplicação OperaçãoToRestCA</span><span class="sxs-lookup"><span data-stu-id="a48a2-102">ApplyToRestCA operation</span></span>

<span data-ttu-id="a48a2-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a48a2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a48a2-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a48a2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a48a2-105">Aplica uma operação a todos menos ao primeiro elemento de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="a48a2-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="a48a2-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="a48a2-106">Description</span></span>

<span data-ttu-id="a48a2-107">Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="a48a2-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="a48a2-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="a48a2-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="a48a2-109">op : 'T[] => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="a48a2-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="a48a2-110">Uma operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="a48a2-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="a48a2-111">objetivos : 'T[]</span><span class="sxs-lookup"><span data-stu-id="a48a2-111">targets : 'T[]</span></span>

<span data-ttu-id="a48a2-112">Uma série de alvos, dos quais todos, menos o primeiro, serão aplicados `op` a .</span><span class="sxs-lookup"><span data-stu-id="a48a2-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a48a2-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a48a2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a48a2-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="a48a2-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a48a2-115">'T</span><span class="sxs-lookup"><span data-stu-id="a48a2-115">'T</span></span>

<span data-ttu-id="a48a2-116">O tipo de entrada da operação a aplicar.</span><span class="sxs-lookup"><span data-stu-id="a48a2-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="a48a2-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a48a2-117">See Also</span></span>

- [<span data-ttu-id="a48a2-118">Microsoft.Quantum.Canon.ApplyTorest</span><span class="sxs-lookup"><span data-stu-id="a48a2-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="a48a2-119">Microsoft.Quantum.Canon.ApplyToresta</span><span class="sxs-lookup"><span data-stu-id="a48a2-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="a48a2-120">Microsoft.Quantum.Canon.ApplyTorestC</span><span class="sxs-lookup"><span data-stu-id="a48a2-120">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)