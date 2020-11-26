---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneCA
title: AplicarIfOneCA operação
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneCA
qsharp.summary: ''
ms.openlocfilehash: e997cf4b20fdd2c52285191b732297ca99886c22
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230944"
---
# <a name="applyifoneca-operation"></a><span data-ttu-id="41819-102">AplicarIfOneCA operação</span><span class="sxs-lookup"><span data-stu-id="41819-102">ApplyIfOneCA operation</span></span>

<span data-ttu-id="41819-103">Espaço de nome: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="41819-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="41819-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="41819-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOneCA<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Ctl + Adj), oneArg : 'T)) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="41819-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="41819-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="41819-106">measurementResult : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="41819-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit--is-adj--ctl"></a><span data-ttu-id="41819-107">onResultOneOp : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="41819-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="onearg--t"></a><span data-ttu-id="41819-108">oneArg : 'T</span><span class="sxs-lookup"><span data-stu-id="41819-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="41819-109">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="41819-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="41819-110">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="41819-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="41819-111">'T</span><span class="sxs-lookup"><span data-stu-id="41819-111">'T</span></span>

