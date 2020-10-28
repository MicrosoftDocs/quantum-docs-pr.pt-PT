---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: Operação PermuteQubits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: 0f4d8819d5b08f4d5370f8fdc407b2eb2a3e5f21
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715662"
---
# <a name="permutequbits-operation"></a><span data-ttu-id="67da5-102">Operação PermuteQubits</span><span class="sxs-lookup"><span data-stu-id="67da5-102">PermuteQubits operation</span></span>

<span data-ttu-id="67da5-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="67da5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="67da5-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="67da5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="67da5-105">Permutes qubits utilizando a operação SWAP.</span><span class="sxs-lookup"><span data-stu-id="67da5-105">Permutes qubits by using the SWAP operation.</span></span>

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="67da5-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="67da5-106">Input</span></span>

### <a name="ordering--int"></a><span data-ttu-id="67da5-107">ordenação : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="67da5-107">ordering : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="67da5-108">Descreve a nova encomenda dos qubits, onde o qubit no índice i estará agora a encomendar[i].</span><span class="sxs-lookup"><span data-stu-id="67da5-108">Describes the new ordering of the qubits, where the qubit at index i will now be at ordering[i].</span></span>


### <a name="register--qubit"></a><span data-ttu-id="67da5-109">registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="67da5-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="67da5-110">Registo qubit para ser agido.</span><span class="sxs-lookup"><span data-stu-id="67da5-110">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="67da5-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="67da5-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

