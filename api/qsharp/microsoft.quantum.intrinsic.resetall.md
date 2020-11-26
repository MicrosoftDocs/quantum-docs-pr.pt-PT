---
uid: Microsoft.Quantum.Intrinsic.ResetAll
title: ResetTo operação
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ResetAll
qsharp.summary: Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.
ms.openlocfilehash: d22ce607e8e5cb3a1c041dc1973875f2a0777d2b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198695"
---
# <a name="resetall-operation"></a><span data-ttu-id="b47f5-102">ResetTo operação</span><span class="sxs-lookup"><span data-stu-id="b47f5-102">ResetAll operation</span></span>

<span data-ttu-id="b47f5-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="b47f5-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="b47f5-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b47f5-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b47f5-105">Dada uma série de qubits, meça-os e garanta que estão no estado de 0⟩ de modo a que possam ser libertados em segurança.</span><span class="sxs-lookup"><span data-stu-id="b47f5-105">Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.</span></span>

```qsharp
operation ResetAll (qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="b47f5-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b47f5-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="b47f5-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b47f5-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b47f5-108">Uma série de qubits cujos estados devem ser repostos para $\ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="b47f5-108">An array of qubits whose states are to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b47f5-109">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b47f5-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

