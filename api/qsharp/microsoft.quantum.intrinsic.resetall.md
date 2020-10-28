---
uid: Microsoft.Quantum.Intrinsic.ResetAll
title: ResetTo operação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ResetAll
qsharp.summary: Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.
ms.openlocfilehash: 00b7c0f508d76fb0f5b46c7ec00c0718469365a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711409"
---
# <a name="resetall-operation"></a><span data-ttu-id="d5b47-102">ResetTo operação</span><span class="sxs-lookup"><span data-stu-id="d5b47-102">ResetAll operation</span></span>

<span data-ttu-id="d5b47-103">Espaço de nome: [Microsoft.Quantum.Intrínseco](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="d5b47-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="d5b47-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d5b47-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d5b47-105">Dada uma série de qubits, meça-os e garanta que estão no estado de 0⟩ de modo a que possam ser libertados em segurança.</span><span class="sxs-lookup"><span data-stu-id="d5b47-105">Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.</span></span>

```qsharp
operation ResetAll (qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="d5b47-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d5b47-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="d5b47-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d5b47-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d5b47-108">Uma série de qubits cujos estados devem ser repostos para $\ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="d5b47-108">An array of qubits whose states are to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d5b47-109">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d5b47-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

