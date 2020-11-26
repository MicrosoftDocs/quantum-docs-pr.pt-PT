---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyCA
title: Aplicar operação ComacionalmenteCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyCA
qsharp.summary: ''
ms.openlocfilehash: 18db01f8e5e00c2f115b8ffe73c0f8eea275beb0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230247"
---
# <a name="applyconditionallyca-operation"></a><span data-ttu-id="b11a7-102">Aplicar operação ComacionalmenteCA</span><span class="sxs-lookup"><span data-stu-id="b11a7-102">ApplyConditionallyCA operation</span></span>

<span data-ttu-id="b11a7-103">Espaço de nome: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="b11a7-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="b11a7-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b11a7-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyCA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl + Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl + Adj), nonEqualArg : 'U)) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b11a7-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="b11a7-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="b11a7-106">medidasResultos: __inválido <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="b11a7-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="b11a7-107">resultados Valores: __inválido <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="b11a7-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit--is-adj--ctl"></a><span data-ttu-id="b11a7-108">onEqualOp : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="b11a7-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="b11a7-109">equalArg : 'T</span><span class="sxs-lookup"><span data-stu-id="b11a7-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit--is-adj--ctl"></a><span data-ttu-id="b11a7-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="b11a7-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="b11a7-111">nonEqualArg : 'U</span><span class="sxs-lookup"><span data-stu-id="b11a7-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="b11a7-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b11a7-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b11a7-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="b11a7-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b11a7-114">'T</span><span class="sxs-lookup"><span data-stu-id="b11a7-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="b11a7-115">'U</span><span class="sxs-lookup"><span data-stu-id="b11a7-115">'U</span></span>

