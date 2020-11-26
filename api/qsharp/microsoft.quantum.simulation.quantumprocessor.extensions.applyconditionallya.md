---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyA
title: Aplicar operaçãoConditionalA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyA
qsharp.summary: ''
ms.openlocfilehash: 8117fd632b78c24c9ecb8545274eaf296645b645
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230417"
---
# <a name="applyconditionallya-operation"></a><span data-ttu-id="6fff5-102">Aplicar operaçãoConditionalA</span><span class="sxs-lookup"><span data-stu-id="6fff5-102">ApplyConditionallyA operation</span></span>

<span data-ttu-id="6fff5-103">Espaço de nome: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="6fff5-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="6fff5-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="6fff5-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Adj), nonEqualArg : 'U)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="6fff5-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="6fff5-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="6fff5-106">medidasResultos: __inválido <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="6fff5-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="6fff5-107">resultados Valores: __inválido <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="6fff5-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit--is-adj"></a><span data-ttu-id="6fff5-108">onEqualOp : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="6fff5-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="6fff5-109">equalArg : 'T</span><span class="sxs-lookup"><span data-stu-id="6fff5-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit--is-adj"></a><span data-ttu-id="6fff5-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span><span class="sxs-lookup"><span data-stu-id="6fff5-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="6fff5-111">nonEqualArg : 'U</span><span class="sxs-lookup"><span data-stu-id="6fff5-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="6fff5-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6fff5-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6fff5-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="6fff5-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6fff5-114">'T</span><span class="sxs-lookup"><span data-stu-id="6fff5-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="6fff5-115">'U</span><span class="sxs-lookup"><span data-stu-id="6fff5-115">'U</span></span>

