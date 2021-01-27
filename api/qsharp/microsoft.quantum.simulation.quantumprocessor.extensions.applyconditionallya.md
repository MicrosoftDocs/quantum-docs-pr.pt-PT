---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyA
title: Aplicar operaçãoConditionalA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyA
qsharp.summary: ''
ms.openlocfilehash: 18ea79e363c28d4fa7aacb69d53a43f6ce39df36
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847879"
---
# <a name="applyconditionallya-operation"></a><span data-ttu-id="16f47-102">Aplicar operaçãoConditionalA</span><span class="sxs-lookup"><span data-stu-id="16f47-102">ApplyConditionallyA operation</span></span>

<span data-ttu-id="16f47-103">Espaço de nome: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="16f47-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="16f47-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="16f47-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Adj), nonEqualArg : 'U)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="16f47-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="16f47-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="16f47-106">medidasResultos: __inválido <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="16f47-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="16f47-107">resultados Valores: __inválido <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="16f47-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit--is-adj"></a><span data-ttu-id="16f47-108">onEqualOp : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="16f47-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="16f47-109">equalArg : 'T</span><span class="sxs-lookup"><span data-stu-id="16f47-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit--is-adj"></a><span data-ttu-id="16f47-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span><span class="sxs-lookup"><span data-stu-id="16f47-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="16f47-111">nonEqualArg : 'U</span><span class="sxs-lookup"><span data-stu-id="16f47-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="16f47-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="16f47-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="16f47-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="16f47-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="16f47-114">'T</span><span class="sxs-lookup"><span data-stu-id="16f47-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="16f47-115">'U</span><span class="sxs-lookup"><span data-stu-id="16f47-115">'U</span></span>

