---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: Operação SetToBasisState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: 2612bfe488c830abd835be89b2f8ea6795abf675
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194156"
---
# <a name="settobasisstate-operation"></a><span data-ttu-id="cf12e-102">Operação SetToBasisState</span><span class="sxs-lookup"><span data-stu-id="cf12e-102">SetToBasisState operation</span></span>

<span data-ttu-id="cf12e-103">Espaço de nome: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="cf12e-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="cf12e-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="cf12e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="cf12e-105">Define um qubit a um dado estado de base computacional medindo o qubit e aplicando um pouco de flip, se necessário.</span><span class="sxs-lookup"><span data-stu-id="cf12e-105">Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.</span></span>

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="cf12e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="cf12e-106">Input</span></span>

### <a name="desired--__invalidresult__"></a><span data-ttu-id="cf12e-107">desejado : __<Result> inválido__</span><span class="sxs-lookup"><span data-stu-id="cf12e-107">desired : __invalid<Result>__</span></span>

<span data-ttu-id="cf12e-108">A base diz que o qubit deve ser definido para.</span><span class="sxs-lookup"><span data-stu-id="cf12e-108">The basis state that the qubit should be set to.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="cf12e-109">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cf12e-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="cf12e-110">O qubit cujo estado deve ser definido.</span><span class="sxs-lookup"><span data-stu-id="cf12e-110">The qubit whose state is to be set.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cf12e-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cf12e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cf12e-112">Observações</span><span class="sxs-lookup"><span data-stu-id="cf12e-112">Remarks</span></span>

<span data-ttu-id="cf12e-113">Como invariante desta operação, a chamada `M(q)` imediatamente a seguir `SetToBasisState(result, q)` `result` regressará.</span><span class="sxs-lookup"><span data-stu-id="cf12e-113">As an invariant of this operation, calling `M(q)` immediately after `SetToBasisState(result, q)` will return `result`.</span></span>