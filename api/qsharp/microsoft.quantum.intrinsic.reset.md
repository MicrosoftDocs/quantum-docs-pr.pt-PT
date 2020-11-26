---
uid: Microsoft.Quantum.Intrinsic.Reset
title: Operação de reset
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: 61b5e4ccdf009dcb6c639e3d8e23bc73a6e475b5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198678"
---
# <a name="reset-operation"></a><span data-ttu-id="8edaf-102">Operação de reset</span><span class="sxs-lookup"><span data-stu-id="8edaf-102">Reset operation</span></span>

<span data-ttu-id="8edaf-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="8edaf-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="8edaf-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="8edaf-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="8edaf-105">Perante um único qubit, mede-o e garante que está no estado de [0⟩ de modo a poder ser libertado com segurança.</span><span class="sxs-lookup"><span data-stu-id="8edaf-105">Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.</span></span>

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="8edaf-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8edaf-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="8edaf-107">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8edaf-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8edaf-108">O qubit cujo estado deve ser reposto para $\ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="8edaf-108">The qubit whose state is to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8edaf-109">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8edaf-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

