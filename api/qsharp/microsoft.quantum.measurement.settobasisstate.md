---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: Operação SetToBasisState
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: dfa054360a5e82b7ae6ec5a6d52e7d5fe566f42e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854630"
---
# <a name="settobasisstate-operation"></a><span data-ttu-id="274c7-102">Operação SetToBasisState</span><span class="sxs-lookup"><span data-stu-id="274c7-102">SetToBasisState operation</span></span>

<span data-ttu-id="274c7-103">Espaço de nome: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="274c7-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="274c7-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="274c7-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="274c7-105">Define um qubit a um dado estado de base computacional medindo o qubit e aplicando um pouco de flip, se necessário.</span><span class="sxs-lookup"><span data-stu-id="274c7-105">Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.</span></span>

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="274c7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="274c7-106">Input</span></span>

### <a name="desired--__invalidresult__"></a><span data-ttu-id="274c7-107">desejado : __<Result> inválido__</span><span class="sxs-lookup"><span data-stu-id="274c7-107">desired : __invalid<Result>__</span></span>

<span data-ttu-id="274c7-108">A base diz que o qubit deve ser definido para.</span><span class="sxs-lookup"><span data-stu-id="274c7-108">The basis state that the qubit should be set to.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="274c7-109">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="274c7-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="274c7-110">O qubit cujo estado deve ser definido.</span><span class="sxs-lookup"><span data-stu-id="274c7-110">The qubit whose state is to be set.</span></span>



## <a name="output--unit"></a><span data-ttu-id="274c7-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="274c7-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="274c7-112">Observações</span><span class="sxs-lookup"><span data-stu-id="274c7-112">Remarks</span></span>

<span data-ttu-id="274c7-113">Como invariante desta operação, a chamada `M(q)` imediatamente a seguir `SetToBasisState(result, q)` `result` regressará.</span><span class="sxs-lookup"><span data-stu-id="274c7-113">As an invariant of this operation, calling `M(q)` immediately after `SetToBasisState(result, q)` will return `result`.</span></span>