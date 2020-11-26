---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: Operação PermuteQubits
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: deb5fa5b0bc0509c957e01bf22e491ad3e2214f3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205611"
---
# <a name="permutequbits-operation"></a><span data-ttu-id="678f6-102">Operação PermuteQubits</span><span class="sxs-lookup"><span data-stu-id="678f6-102">PermuteQubits operation</span></span>

<span data-ttu-id="678f6-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="678f6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="678f6-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="678f6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="678f6-105">Permutes qubits utilizando a operação SWAP.</span><span class="sxs-lookup"><span data-stu-id="678f6-105">Permutes qubits by using the SWAP operation.</span></span>

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="678f6-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="678f6-106">Input</span></span>

### <a name="ordering--int"></a><span data-ttu-id="678f6-107">ordenação : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="678f6-107">ordering : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="678f6-108">Descreve a nova encomenda dos qubits, onde o qubit no índice i estará agora a encomendar[i].</span><span class="sxs-lookup"><span data-stu-id="678f6-108">Describes the new ordering of the qubits, where the qubit at index i will now be at ordering[i].</span></span>


### <a name="register--qubit"></a><span data-ttu-id="678f6-109">registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="678f6-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="678f6-110">Registo qubit para ser agido.</span><span class="sxs-lookup"><span data-stu-id="678f6-110">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="678f6-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="678f6-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

