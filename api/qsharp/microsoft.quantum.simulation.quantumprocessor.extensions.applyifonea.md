---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneA
title: AplicarIfOneA operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneA
qsharp.summary: ''
ms.openlocfilehash: 63ce44300f6e50cb91294b62611275e3e8942655
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855602"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="7cff8-102">AplicarIfOneA operação</span><span class="sxs-lookup"><span data-stu-id="7cff8-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="7cff8-103">Espaço de nome: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="7cff8-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="7cff8-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="7cff8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOneA<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Adj), oneArg : 'T)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="7cff8-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="7cff8-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="7cff8-106">measurementResult : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="7cff8-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit--is-adj"></a><span data-ttu-id="7cff8-107">onResultOneOp : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="7cff8-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="onearg--t"></a><span data-ttu-id="7cff8-108">oneArg : 'T</span><span class="sxs-lookup"><span data-stu-id="7cff8-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="7cff8-109">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7cff8-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7cff8-110">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="7cff8-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7cff8-111">'T</span><span class="sxs-lookup"><span data-stu-id="7cff8-111">'T</span></span>

