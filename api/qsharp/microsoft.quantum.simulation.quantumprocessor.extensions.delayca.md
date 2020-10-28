---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.DelayCA
title: Operação DelayCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: DelayCA
qsharp.summary: ''
ms.openlocfilehash: 8bb33b9bfedcd324a2dea0ac9ab2a0ddadd6db20
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725609"
---
# <a name="delayca-operation"></a><span data-ttu-id="a6f56-102">Operação DelayCA</span><span class="sxs-lookup"><span data-stu-id="a6f56-102">DelayCA operation</span></span>

<span data-ttu-id="a6f56-103">Espaço de nome: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="a6f56-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="a6f56-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a6f56-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation DelayCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T, aux : Unit) : Unit
```


## <a name="input"></a><span data-ttu-id="a6f56-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="a6f56-105">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="a6f56-106">op : 'T = unidade> [Ctl](xref:microsoft.quantum.lang-ref.unit) + Adj</span><span class="sxs-lookup"><span data-stu-id="a6f56-106">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>




### <a name="arg--t"></a><span data-ttu-id="a6f56-107">arg : 'T</span><span class="sxs-lookup"><span data-stu-id="a6f56-107">arg : 'T</span></span>




### <a name="aux--unit"></a><span data-ttu-id="a6f56-108">aux : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a6f56-108">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="a6f56-109">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a6f56-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a6f56-110">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="a6f56-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a6f56-111">'T</span><span class="sxs-lookup"><span data-stu-id="a6f56-111">'T</span></span>

