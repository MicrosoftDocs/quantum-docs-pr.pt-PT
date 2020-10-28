---
uid: Microsoft.Quantum.Intrinsic.S
title: S operação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: S
qsharp.summary: Applies the S gate to a single qubit.
ms.openlocfilehash: 8a57c60ac1df8f6e94b58acf7183c47f395d291a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722652"
---
# <a name="s-operation"></a><span data-ttu-id="d3bc5-102">S operação</span><span class="sxs-lookup"><span data-stu-id="d3bc5-102">S operation</span></span>

<span data-ttu-id="d3bc5-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="d3bc5-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="d3bc5-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d3bc5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d3bc5-105">Aplica o portão S a um único qubit.</span><span class="sxs-lookup"><span data-stu-id="d3bc5-105">Applies the S gate to a single qubit.</span></span>

```qsharp
operation S (qubit : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="d3bc5-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="d3bc5-106">Description</span></span>

<span data-ttu-id="d3bc5-107">Esta operação pode ser simulada pela matriz unitária \start{align} S \mathrel{:=} \start{bmatrix} 1 & 0 \\ \\ 0 & i \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="d3bc5-107">This operation can be simulated by the unitary matrix \begin{align} S \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
<span data-ttu-id="d3bc5-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="d3bc5-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="d3bc5-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="d3bc5-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="d3bc5-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d3bc5-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d3bc5-111">Qubit ao qual o portão deve ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="d3bc5-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d3bc5-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d3bc5-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

