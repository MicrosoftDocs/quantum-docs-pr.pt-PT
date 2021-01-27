---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyCA
title: Aplicar operação ComacionalmenteCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyCA
qsharp.summary: ''
ms.openlocfilehash: ce82ae10341d3be5f6e0e025631e5dd91a33e622
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847848"
---
# <a name="applyconditionallyca-operation"></a><span data-ttu-id="5b158-102">Aplicar operação ComacionalmenteCA</span><span class="sxs-lookup"><span data-stu-id="5b158-102">ApplyConditionallyCA operation</span></span>

<span data-ttu-id="5b158-103">Espaço de nome: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="5b158-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="5b158-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="5b158-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyCA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl + Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl + Adj), nonEqualArg : 'U)) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5b158-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="5b158-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="5b158-106">medidasResultos: __inválido <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="5b158-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="5b158-107">resultados Valores: __inválido <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="5b158-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit--is-adj--ctl"></a><span data-ttu-id="5b158-108">onEqualOp : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="5b158-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="5b158-109">equalArg : 'T</span><span class="sxs-lookup"><span data-stu-id="5b158-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit--is-adj--ctl"></a><span data-ttu-id="5b158-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="5b158-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="5b158-111">nonEqualArg : 'U</span><span class="sxs-lookup"><span data-stu-id="5b158-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="5b158-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5b158-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5b158-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="5b158-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5b158-114">'T</span><span class="sxs-lookup"><span data-stu-id="5b158-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="5b158-115">'U</span><span class="sxs-lookup"><span data-stu-id="5b158-115">'U</span></span>

