---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroC
title: Aplicação OperaçãoIfZeroC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroC
qsharp.summary: ''
ms.openlocfilehash: 6de4fcf86495136f2caec6fb6f873a18d751c977
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725690"
---
# <a name="applyifzeroc-operation"></a><span data-ttu-id="8091d-102">Aplicação OperaçãoIfZeroC</span><span class="sxs-lookup"><span data-stu-id="8091d-102">ApplyIfZeroC operation</span></span>

<span data-ttu-id="8091d-103">Espaço de nome: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="8091d-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="8091d-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8091d-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfZeroC<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="8091d-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="8091d-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="8091d-106">measurementResult : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="8091d-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit-ctl"></a><span data-ttu-id="8091d-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="8091d-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="8091d-108">zeroArg : 'T</span><span class="sxs-lookup"><span data-stu-id="8091d-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="8091d-109">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8091d-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8091d-110">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="8091d-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8091d-111">'T</span><span class="sxs-lookup"><span data-stu-id="8091d-111">'T</span></span>

