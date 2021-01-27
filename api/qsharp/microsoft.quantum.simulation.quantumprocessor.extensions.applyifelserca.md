---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRCA
title: Aplicação OperaçãoIfElseRCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRCA
qsharp.summary: ''
ms.openlocfilehash: 2f72da8b470e340d8b283a27643797d41b44592e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855634"
---
# <a name="applyifelserca-operation"></a><span data-ttu-id="8f27c-102">Aplicação OperaçãoIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="8f27c-102">ApplyIfElseRCA operation</span></span>

<span data-ttu-id="8f27c-103">Espaço de nome: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="8f27c-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="8f27c-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="8f27c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseRCA<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj + Ctl), zeroArg : 'T), (onResultOneOp : ('U => Unit is Adj + Ctl), oneArg : 'U)) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="8f27c-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="8f27c-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="8f27c-106">measurementResult : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="8f27c-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-adj--ctl"></a><span data-ttu-id="8f27c-107">onResultZeroOp : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="8f27c-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="8f27c-108">zeroArg : 'T</span><span class="sxs-lookup"><span data-stu-id="8f27c-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit--is-adj--ctl"></a><span data-ttu-id="8f27c-109">onResultOneOp : 'U = [> Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="8f27c-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="onearg--u"></a><span data-ttu-id="8f27c-110">oneArg : 'U</span><span class="sxs-lookup"><span data-stu-id="8f27c-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="8f27c-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8f27c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8f27c-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="8f27c-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8f27c-113">'T</span><span class="sxs-lookup"><span data-stu-id="8f27c-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="8f27c-114">'U</span><span class="sxs-lookup"><span data-stu-id="8f27c-114">'U</span></span>

