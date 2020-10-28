---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZero
title: Aplicação OperaçãoIfZero
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZero
qsharp.summary: ''
ms.openlocfilehash: a76c6269ac4445326ac357fe2cdd552847089a6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722683"
---
# <a name="applyifzero-operation"></a><span data-ttu-id="35c60-102">Aplicação OperaçãoIfZero</span><span class="sxs-lookup"><span data-stu-id="35c60-102">ApplyIfZero operation</span></span>

<span data-ttu-id="35c60-103">Espaço de nome: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="35c60-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="35c60-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="35c60-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfZero<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit), zeroArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="35c60-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="35c60-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="35c60-106">measurementResult : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="35c60-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit"></a><span data-ttu-id="35c60-107">onResultZeroOp : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="35c60-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="zeroarg--t"></a><span data-ttu-id="35c60-108">zeroArg : 'T</span><span class="sxs-lookup"><span data-stu-id="35c60-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="35c60-109">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="35c60-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="35c60-110">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="35c60-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="35c60-111">'T</span><span class="sxs-lookup"><span data-stu-id="35c60-111">'T</span></span>

