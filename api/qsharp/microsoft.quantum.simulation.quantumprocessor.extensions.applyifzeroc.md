---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroC
title: Aplicação OperaçãoIfZeroC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroC
qsharp.summary: ''
ms.openlocfilehash: c4d1618ff5e2a3d61823eddd6905445effcecfdd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854173"
---
# <a name="applyifzeroc-operation"></a><span data-ttu-id="c019b-102">Aplicação OperaçãoIfZeroC</span><span class="sxs-lookup"><span data-stu-id="c019b-102">ApplyIfZeroC operation</span></span>

<span data-ttu-id="c019b-103">Espaço de nome: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="c019b-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="c019b-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c019b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZeroC<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="c019b-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="c019b-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="c019b-106">measurementResult : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="c019b-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-ctl"></a><span data-ttu-id="c019b-107">onResultZeroOp : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Ctl</span><span class="sxs-lookup"><span data-stu-id="c019b-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="c019b-108">zeroArg : 'T</span><span class="sxs-lookup"><span data-stu-id="c019b-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="c019b-109">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c019b-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c019b-110">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="c019b-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c019b-111">'T</span><span class="sxs-lookup"><span data-stu-id="c019b-111">'T</span></span>

