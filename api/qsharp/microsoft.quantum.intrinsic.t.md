---
uid: Microsoft.Quantum.Intrinsic.T
title: Operação T
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: T
qsharp.summary: Applies the T gate to a single qubit.
ms.openlocfilehash: bee252d9905aed26f6bf663f895e464e38073f44
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817520"
---
# <a name="t-operation"></a><span data-ttu-id="0c61a-102">Operação T</span><span class="sxs-lookup"><span data-stu-id="0c61a-102">T operation</span></span>

<span data-ttu-id="0c61a-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="0c61a-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="0c61a-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="0c61a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="0c61a-105">Aplica o portão T a um único qubit.</span><span class="sxs-lookup"><span data-stu-id="0c61a-105">Applies the T gate to a single qubit.</span></span>

```qsharp
operation T (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="0c61a-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="0c61a-106">Description</span></span>

<span data-ttu-id="0c61a-107">Esta operação pode ser simulada pela matriz unitária \start{align} T \mathrel{:=} \start{bmatrix} 1 & \\ \\ 0 0 & e^{i \pi / 4} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="0c61a-107">This operation can be simulated by the unitary matrix \begin{align} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & e^{i \pi / 4} \end{bmatrix}.</span></span>
<span data-ttu-id="0c61a-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="0c61a-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="0c61a-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="0c61a-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="0c61a-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0c61a-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0c61a-111">Qubit ao qual o portão deve ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="0c61a-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0c61a-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0c61a-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

