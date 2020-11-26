---
uid: Microsoft.Quantum.Canon.ApplyBoundCA
title: Operação ApplyBoundCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyBoundCA
qsharp.summary: ''
ms.openlocfilehash: 8eb41318fbb9cbee46159ac3a570b21874358d32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219214"
---
# <a name="applyboundca-operation"></a><span data-ttu-id="bf15b-102">Operação ApplyBoundCA</span><span class="sxs-lookup"><span data-stu-id="bf15b-102">ApplyBoundCA operation</span></span>

<span data-ttu-id="bf15b-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bf15b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bf15b-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bf15b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyBoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[], target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="bf15b-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="bf15b-105">Input</span></span>

### <a name="operations--t--unit--is-adj--ctl"></a><span data-ttu-id="bf15b-106">operações : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl[]</span><span class="sxs-lookup"><span data-stu-id="bf15b-106">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>




### <a name="target--t"></a><span data-ttu-id="bf15b-107">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="bf15b-107">target : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="bf15b-108">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bf15b-108">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bf15b-109">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="bf15b-109">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bf15b-110">'T</span><span class="sxs-lookup"><span data-stu-id="bf15b-110">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="bf15b-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="bf15b-111">See Also</span></span>

- [<span data-ttu-id="bf15b-112">Microsoft.Quantum.Canon.BoundCA</span><span class="sxs-lookup"><span data-stu-id="bf15b-112">Microsoft.Quantum.Canon.BoundCA</span></span>](xref:Microsoft.Quantum.Canon.BoundCA)