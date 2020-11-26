---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionally
title: Aplicar operação condicional
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionally
qsharp.summary: ''
ms.openlocfilehash: 24d52576d2fb3e83f294874be4b0d1cd6a80f188
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229074"
---
# <a name="applyconditionally-operation"></a><span data-ttu-id="14e8e-102">Aplicar operação condicional</span><span class="sxs-lookup"><span data-stu-id="14e8e-102">ApplyConditionally operation</span></span>

<span data-ttu-id="14e8e-103">Espaço de nome: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="14e8e-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="14e8e-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="14e8e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionally<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit), equalArg : 'T), (onNonEqualOp : ('U => Unit), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="14e8e-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="14e8e-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="14e8e-106">medidasResultos: __inválido <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="14e8e-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="14e8e-107">resultados Valores: __inválido <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="14e8e-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit"></a><span data-ttu-id="14e8e-108">onEqualOp : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="14e8e-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="equalarg--t"></a><span data-ttu-id="14e8e-109">equalArg : 'T</span><span class="sxs-lookup"><span data-stu-id="14e8e-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit"></a><span data-ttu-id="14e8e-110">onNonEqualOp : 'U = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="14e8e-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="nonequalarg--u"></a><span data-ttu-id="14e8e-111">nonEqualArg : 'U</span><span class="sxs-lookup"><span data-stu-id="14e8e-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="14e8e-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="14e8e-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="14e8e-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="14e8e-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="14e8e-114">'T</span><span class="sxs-lookup"><span data-stu-id="14e8e-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="14e8e-115">'U</span><span class="sxs-lookup"><span data-stu-id="14e8e-115">'U</span></span>

