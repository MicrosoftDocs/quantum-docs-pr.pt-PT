---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRC
title: Aplicação OperaçãoIfElseRC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRC
qsharp.summary: ''
ms.openlocfilehash: 21069c43c16bc9712973ac4e0afea8320c0d83a9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709463"
---
# <a name="applyifelserc-operation"></a><span data-ttu-id="ca057-102">Aplicação OperaçãoIfElseRC</span><span class="sxs-lookup"><span data-stu-id="ca057-102">ApplyIfElseRC operation</span></span>

<span data-ttu-id="ca057-103">Espaço de nome: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="ca057-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="ca057-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ca057-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfElseRC<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T), (onResultOneOp : ('U => Unit is Ctl), oneArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="ca057-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="ca057-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="ca057-106">measurementResult : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="ca057-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit-ctl"></a><span data-ttu-id="ca057-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="ca057-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="ca057-108">zeroArg : 'T</span><span class="sxs-lookup"><span data-stu-id="ca057-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit-ctl"></a><span data-ttu-id="ca057-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="ca057-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="onearg--u"></a><span data-ttu-id="ca057-110">oneArg : 'U</span><span class="sxs-lookup"><span data-stu-id="ca057-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="ca057-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ca057-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ca057-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="ca057-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ca057-113">'T</span><span class="sxs-lookup"><span data-stu-id="ca057-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="ca057-114">'U</span><span class="sxs-lookup"><span data-stu-id="ca057-114">'U</span></span>

