---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionally
title: Aplicar operação condicional
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionally
qsharp.summary: ''
ms.openlocfilehash: 67a4dcba5c193222c06ab429813adf12d7bbedfb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847889"
---
# <a name="applyconditionally-operation"></a><span data-ttu-id="1a0d4-102">Aplicar operação condicional</span><span class="sxs-lookup"><span data-stu-id="1a0d4-102">ApplyConditionally operation</span></span>

<span data-ttu-id="1a0d4-103">Espaço de nome: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="1a0d4-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="1a0d4-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1a0d4-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionally<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit), equalArg : 'T), (onNonEqualOp : ('U => Unit), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="1a0d4-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="1a0d4-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="1a0d4-106">medidasResultos: __inválido <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="1a0d4-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="1a0d4-107">resultados Valores: __inválido <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="1a0d4-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit"></a><span data-ttu-id="1a0d4-108">onEqualOp : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="1a0d4-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="equalarg--t"></a><span data-ttu-id="1a0d4-109">equalArg : 'T</span><span class="sxs-lookup"><span data-stu-id="1a0d4-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit"></a><span data-ttu-id="1a0d4-110">onNonEqualOp : 'U = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="1a0d4-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="nonequalarg--u"></a><span data-ttu-id="1a0d4-111">nonEqualArg : 'U</span><span class="sxs-lookup"><span data-stu-id="1a0d4-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="1a0d4-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1a0d4-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1a0d4-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="1a0d4-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1a0d4-114">'T</span><span class="sxs-lookup"><span data-stu-id="1a0d4-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="1a0d4-115">'U</span><span class="sxs-lookup"><span data-stu-id="1a0d4-115">'U</span></span>

