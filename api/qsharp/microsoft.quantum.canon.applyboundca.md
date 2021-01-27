---
uid: Microsoft.Quantum.Canon.ApplyBoundCA
title: Operação ApplyBoundCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyBoundCA
qsharp.summary: ''
ms.openlocfilehash: 8f6007055c9e96f843689f4500642c6f0e5813ae
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841982"
---
# <a name="applyboundca-operation"></a><span data-ttu-id="9ad14-102">Operação ApplyBoundCA</span><span class="sxs-lookup"><span data-stu-id="9ad14-102">ApplyBoundCA operation</span></span>

<span data-ttu-id="9ad14-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9ad14-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9ad14-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9ad14-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyBoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[], target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9ad14-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="9ad14-105">Input</span></span>

### <a name="operations--t--unit--is-adj--ctl"></a><span data-ttu-id="9ad14-106">operações : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl[]</span><span class="sxs-lookup"><span data-stu-id="9ad14-106">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>




### <a name="target--t"></a><span data-ttu-id="9ad14-107">alvo : 'T</span><span class="sxs-lookup"><span data-stu-id="9ad14-107">target : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="9ad14-108">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9ad14-108">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9ad14-109">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="9ad14-109">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9ad14-110">'T</span><span class="sxs-lookup"><span data-stu-id="9ad14-110">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="9ad14-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9ad14-111">See Also</span></span>

- [<span data-ttu-id="9ad14-112">Microsoft.Quantum.Canon.BoundCA</span><span class="sxs-lookup"><span data-stu-id="9ad14-112">Microsoft.Quantum.Canon.BoundCA</span></span>](xref:Microsoft.Quantum.Canon.BoundCA)