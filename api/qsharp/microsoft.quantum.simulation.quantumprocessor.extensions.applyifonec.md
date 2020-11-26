---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneC
title: Aplicar operaçãoIfOneC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneC
qsharp.summary: ''
ms.openlocfilehash: d7c4e39ba26befeabad612e888da4abd00efaeb5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230961"
---
# <a name="applyifonec-operation"></a><span data-ttu-id="14094-102">Aplicar operaçãoIfOneC</span><span class="sxs-lookup"><span data-stu-id="14094-102">ApplyIfOneC operation</span></span>

<span data-ttu-id="14094-103">Espaço de nome: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="14094-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="14094-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="14094-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOneC<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Ctl), oneArg : 'T)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="14094-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="14094-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="14094-106">measurementResult : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="14094-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit--is-ctl"></a><span data-ttu-id="14094-107">onResultOneOp : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Ctl</span><span class="sxs-lookup"><span data-stu-id="14094-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="onearg--t"></a><span data-ttu-id="14094-108">oneArg : 'T</span><span class="sxs-lookup"><span data-stu-id="14094-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="14094-109">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="14094-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="14094-110">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="14094-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="14094-111">'T</span><span class="sxs-lookup"><span data-stu-id="14094-111">'T</span></span>

