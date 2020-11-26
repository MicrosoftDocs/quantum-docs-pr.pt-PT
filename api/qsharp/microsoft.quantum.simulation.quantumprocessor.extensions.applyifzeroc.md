---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroC
title: Aplicação OperaçãoIfZeroC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroC
qsharp.summary: ''
ms.openlocfilehash: 9a73ea9ec607bec89c996c096b235a72185b453d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230842"
---
# <a name="applyifzeroc-operation"></a><span data-ttu-id="7b906-102">Aplicação OperaçãoIfZeroC</span><span class="sxs-lookup"><span data-stu-id="7b906-102">ApplyIfZeroC operation</span></span>

<span data-ttu-id="7b906-103">Espaço de nome: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="7b906-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="7b906-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="7b906-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZeroC<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="7b906-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="7b906-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="7b906-106">measurementResult : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="7b906-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-ctl"></a><span data-ttu-id="7b906-107">onResultZeroOp : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Ctl</span><span class="sxs-lookup"><span data-stu-id="7b906-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="7b906-108">zeroArg : 'T</span><span class="sxs-lookup"><span data-stu-id="7b906-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="7b906-109">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7b906-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7b906-110">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="7b906-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7b906-111">'T</span><span class="sxs-lookup"><span data-stu-id="7b906-111">'T</span></span>

