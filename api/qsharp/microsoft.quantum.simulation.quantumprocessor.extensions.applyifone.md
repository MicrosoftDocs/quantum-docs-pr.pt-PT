---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOne
title: AplicarIfOne
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOne
qsharp.summary: ''
ms.openlocfilehash: f8f4f3b05d3986d94e6f1be380d6c83151d87f17
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230672"
---
# <a name="applyifone-operation"></a><span data-ttu-id="98de0-102">AplicarIfOne</span><span class="sxs-lookup"><span data-stu-id="98de0-102">ApplyIfOne operation</span></span>

<span data-ttu-id="98de0-103">Espaço de nome: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="98de0-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="98de0-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="98de0-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOne<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit), oneArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="98de0-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="98de0-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="98de0-106">measurementResult : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="98de0-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit"></a><span data-ttu-id="98de0-107">onResultOneOp : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="98de0-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onearg--t"></a><span data-ttu-id="98de0-108">oneArg : 'T</span><span class="sxs-lookup"><span data-stu-id="98de0-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="98de0-109">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="98de0-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="98de0-110">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="98de0-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="98de0-111">'T</span><span class="sxs-lookup"><span data-stu-id="98de0-111">'T</span></span>

