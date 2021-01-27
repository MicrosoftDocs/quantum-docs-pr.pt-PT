---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyC
title: Aplicar operaçãoConditionalC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyC
qsharp.summary: ''
ms.openlocfilehash: 09496d384a70fa9fb6826304ce9909034297a118
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847860"
---
# <a name="applyconditionallyc-operation"></a><span data-ttu-id="f8286-102">Aplicar operaçãoConditionalC</span><span class="sxs-lookup"><span data-stu-id="f8286-102">ApplyConditionallyC operation</span></span>

<span data-ttu-id="f8286-103">Espaço de nome: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="f8286-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="f8286-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f8286-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyC<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl), nonEqualArg : 'U)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="f8286-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="f8286-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="f8286-106">medidasResultos: __inválido <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="f8286-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="f8286-107">resultados Valores: __inválido <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="f8286-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit--is-ctl"></a><span data-ttu-id="f8286-108">onEqualOp : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é CTL</span><span class="sxs-lookup"><span data-stu-id="f8286-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="f8286-109">equalArg : 'T</span><span class="sxs-lookup"><span data-stu-id="f8286-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit--is-ctl"></a><span data-ttu-id="f8286-110">onNonEqualOp : 'U = [> Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span><span class="sxs-lookup"><span data-stu-id="f8286-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="f8286-111">nonEqualArg : 'U</span><span class="sxs-lookup"><span data-stu-id="f8286-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="f8286-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f8286-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f8286-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="f8286-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f8286-114">'T</span><span class="sxs-lookup"><span data-stu-id="f8286-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="f8286-115">'U</span><span class="sxs-lookup"><span data-stu-id="f8286-115">'U</span></span>

