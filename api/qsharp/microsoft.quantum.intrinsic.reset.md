---
uid: Microsoft.Quantum.Intrinsic.Reset
title: Operação de reset
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: c89cbbce49e294e56abc11b3b0492d2ed8e980a8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720874"
---
# <a name="reset-operation"></a><span data-ttu-id="36897-102">Operação de reset</span><span class="sxs-lookup"><span data-stu-id="36897-102">Reset operation</span></span>

<span data-ttu-id="36897-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="36897-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="36897-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="36897-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="36897-105">Perante um único qubit, mede-o e garante que está no estado de [0⟩ de modo a poder ser libertado com segurança.</span><span class="sxs-lookup"><span data-stu-id="36897-105">Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.</span></span>

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="36897-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="36897-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="36897-107">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="36897-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="36897-108">O qubit cujo estado deve ser reposto para $\ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="36897-108">The qubit whose state is to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="36897-109">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="36897-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

