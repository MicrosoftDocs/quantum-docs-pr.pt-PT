---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsicC
title: Aplicar operação ConditionallyIntrinsicC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsicC
qsharp.summary: ''
ms.openlocfilehash: 64c6693181704d229e36a3e3748258f66e093d96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855753"
---
# <a name="applyconditionallyintrinsicc-operation"></a><span data-ttu-id="52dc9-102">Aplicar operação ConditionallyIntrinsicC</span><span class="sxs-lookup"><span data-stu-id="52dc9-102">ApplyConditionallyIntrinsicC operation</span></span>

<span data-ttu-id="52dc9-103">Espaço de nome: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="52dc9-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="52dc9-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="52dc9-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyIntrinsicC (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit is Ctl), onNonEqualOp : (Unit => Unit is Ctl)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="52dc9-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="52dc9-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="52dc9-106">medidasResultos: __inválido <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="52dc9-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="52dc9-107">resultados Valores: __inválido <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="52dc9-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--unit--unit--is-ctl"></a><span data-ttu-id="52dc9-108">onEqualOp [](xref:microsoft.quantum.lang-ref.unit) : => [Unidade](xref:microsoft.quantum.lang-ref.unit) é CTL</span><span class="sxs-lookup"><span data-stu-id="52dc9-108">onEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="onnonequalop--unit--unit--is-ctl"></a><span data-ttu-id="52dc9-109">onNonEqualOp [](xref:microsoft.quantum.lang-ref.unit) : => [Unidade](xref:microsoft.quantum.lang-ref.unit) é CTL</span><span class="sxs-lookup"><span data-stu-id="52dc9-109">onNonEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>





## <a name="output--unit"></a><span data-ttu-id="52dc9-110">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="52dc9-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

