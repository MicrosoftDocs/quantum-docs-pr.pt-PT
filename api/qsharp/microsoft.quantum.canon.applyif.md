---
uid: Microsoft.Quantum.Canon.ApplyIf
title: Aplicação OperaçãoIf
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: c8f6860a7a3b8af86b0edb048baccbf057dd245a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718246"
---
# <a name="applyif-operation"></a><span data-ttu-id="8f95b-102">Aplicação OperaçãoIf</span><span class="sxs-lookup"><span data-stu-id="8f95b-102">ApplyIf operation</span></span>

<span data-ttu-id="8f95b-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8f95b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8f95b-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8f95b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8f95b-105">Aplica uma operação condicionada a uma parte clássica.</span><span class="sxs-lookup"><span data-stu-id="8f95b-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="8f95b-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="8f95b-106">Description</span></span>

<span data-ttu-id="8f95b-107">Dada uma operação `op` e um pouco de `bit` valor, aplica-se `op` ao se é `target` `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="8f95b-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="8f95b-108">Se, `false` nada acontecer ao `target` .</span><span class="sxs-lookup"><span data-stu-id="8f95b-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="8f95b-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="8f95b-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="8f95b-110">op : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="8f95b-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="8f95b-111">Uma operação a ser aplicada condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="8f95b-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="8f95b-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8f95b-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8f95b-113">um booleano que controla se a operação é aplicada ou não.</span><span class="sxs-lookup"><span data-stu-id="8f95b-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="8f95b-114">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="8f95b-114">target : 'T</span></span>

<span data-ttu-id="8f95b-115">A entrada à qual a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="8f95b-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8f95b-116">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8f95b-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8f95b-117">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="8f95b-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8f95b-118">'T</span><span class="sxs-lookup"><span data-stu-id="8f95b-118">'T</span></span>

<span data-ttu-id="8f95b-119">O tipo de entrada da operação a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="8f95b-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f95b-120">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8f95b-120">See Also</span></span>

- [<span data-ttu-id="8f95b-121">Microsoft.Quantum.Canon.ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="8f95b-121">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="8f95b-122">Microsoft.Quantum.Canon.ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="8f95b-122">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="8f95b-123">Microsoft.Quantum.Canon.ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="8f95b-123">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)