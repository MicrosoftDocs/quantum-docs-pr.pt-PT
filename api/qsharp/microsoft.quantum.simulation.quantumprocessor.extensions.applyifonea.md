---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneA
title: AplicarIfOneA operação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneA
qsharp.summary: ''
ms.openlocfilehash: c18133403a545f7dc7b9f213a42ed09cd194f2d7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725396"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="b91ef-102">AplicarIfOneA operação</span><span class="sxs-lookup"><span data-stu-id="b91ef-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="b91ef-103">Espaço de nome: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="b91ef-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="b91ef-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b91ef-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfOneA<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Adj), oneArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="b91ef-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="b91ef-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="b91ef-106">measurementResult : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="b91ef-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit-adj"></a><span data-ttu-id="b91ef-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span><span class="sxs-lookup"><span data-stu-id="b91ef-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="onearg--t"></a><span data-ttu-id="b91ef-108">oneArg : 'T</span><span class="sxs-lookup"><span data-stu-id="b91ef-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="b91ef-109">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b91ef-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b91ef-110">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="b91ef-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b91ef-111">'T</span><span class="sxs-lookup"><span data-stu-id="b91ef-111">'T</span></span>

