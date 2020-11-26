---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseR
title: Aplicação OperaçãoIfElseR
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseR
qsharp.summary: ''
ms.openlocfilehash: 9e391b61aa4d22ad02bf657a866f959d35b6628f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192677"
---
# <a name="applyifelser-operation"></a><span data-ttu-id="e62fa-102">Aplicação OperaçãoIfElseR</span><span class="sxs-lookup"><span data-stu-id="e62fa-102">ApplyIfElseR operation</span></span>

<span data-ttu-id="e62fa-103">Espaço de nome: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="e62fa-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="e62fa-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e62fa-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseR<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit), zeroArg : 'T), (onResultOneOp : ('U => Unit), oneArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="e62fa-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="e62fa-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="e62fa-106">measurementResult : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="e62fa-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit"></a><span data-ttu-id="e62fa-107">onResultZeroOp : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="e62fa-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="zeroarg--t"></a><span data-ttu-id="e62fa-108">zeroArg : 'T</span><span class="sxs-lookup"><span data-stu-id="e62fa-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit"></a><span data-ttu-id="e62fa-109">onResultOneOp : 'U = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="e62fa-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onearg--u"></a><span data-ttu-id="e62fa-110">oneArg : 'U</span><span class="sxs-lookup"><span data-stu-id="e62fa-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="e62fa-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e62fa-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e62fa-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="e62fa-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e62fa-113">'T</span><span class="sxs-lookup"><span data-stu-id="e62fa-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="e62fa-114">'U</span><span class="sxs-lookup"><span data-stu-id="e62fa-114">'U</span></span>

