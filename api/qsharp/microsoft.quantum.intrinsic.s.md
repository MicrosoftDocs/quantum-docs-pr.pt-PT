---
uid: Microsoft.Quantum.Intrinsic.S
title: S operação
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: S
qsharp.summary: Applies the S gate to a single qubit.
ms.openlocfilehash: c697408c4efe1963787b5aee8f0d3bb6b9e64dd5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198457"
---
# <a name="s-operation"></a><span data-ttu-id="62da1-102">S operação</span><span class="sxs-lookup"><span data-stu-id="62da1-102">S operation</span></span>

<span data-ttu-id="62da1-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="62da1-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="62da1-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="62da1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="62da1-105">Aplica o portão S a um único qubit.</span><span class="sxs-lookup"><span data-stu-id="62da1-105">Applies the S gate to a single qubit.</span></span>

```qsharp
operation S (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="62da1-106">Description</span><span class="sxs-lookup"><span data-stu-id="62da1-106">Description</span></span>

<span data-ttu-id="62da1-107">Esta operação pode ser simulada pela matriz unitária \start{align} S \mathrel{:=} \start{bmatrix} 1 & 0 \\ \\ 0 & i \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="62da1-107">This operation can be simulated by the unitary matrix \begin{align} S \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
<span data-ttu-id="62da1-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="62da1-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="62da1-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="62da1-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="62da1-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="62da1-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="62da1-111">Qubit ao qual o portão deve ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="62da1-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="62da1-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="62da1-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

