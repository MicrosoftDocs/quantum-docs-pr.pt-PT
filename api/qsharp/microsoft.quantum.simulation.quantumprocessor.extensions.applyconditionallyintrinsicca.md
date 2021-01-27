---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsicCA
title: Aplicar operação CÍtrina Desmedida
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsicCA
qsharp.summary: ''
ms.openlocfilehash: 137168d7360842df18d1ed2893f7a1b2e9a548cc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854209"
---
# <a name="applyconditionallyintrinsicca-operation"></a><span data-ttu-id="da885-102">Aplicar operação CÍtrina Desmedida</span><span class="sxs-lookup"><span data-stu-id="da885-102">ApplyConditionallyIntrinsicCA operation</span></span>

<span data-ttu-id="da885-103">Espaço de nome: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="da885-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="da885-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="da885-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyIntrinsicCA (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit is Ctl + Adj), onNonEqualOp : (Unit => Unit is Ctl + Adj)) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="da885-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="da885-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="da885-106">medidasResultos: __inválido <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="da885-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="da885-107">resultados Valores: __inválido <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="da885-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--unit--unit--is-adj--ctl"></a><span data-ttu-id="da885-108">onEqualOp [](xref:microsoft.quantum.lang-ref.unit) : => [Unidade](xref:microsoft.quantum.lang-ref.unit) unidade é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="da885-108">onEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="onnonequalop--unit--unit--is-adj--ctl"></a><span data-ttu-id="da885-109">onNonEqualOp : [Unidade](xref:microsoft.quantum.lang-ref.unit) unidade é => [](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="da885-109">onNonEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>





## <a name="output--unit"></a><span data-ttu-id="da885-110">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="da885-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

