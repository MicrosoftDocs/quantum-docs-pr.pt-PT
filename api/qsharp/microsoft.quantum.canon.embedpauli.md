---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: Função EmbedPauli
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: e9042ca9eac4b8791057037dc5698eb14deadd31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207042"
---
# <a name="embedpauli-function"></a><span data-ttu-id="cbd6c-102">Função EmbedPauli</span><span class="sxs-lookup"><span data-stu-id="cbd6c-102">EmbedPauli function</span></span>

<span data-ttu-id="cbd6c-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cbd6c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cbd6c-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cbd6c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cbd6c-105">Dado um operador pauli de um único qubit e o índice de um qubit, devolve um operador Pauli multi-qubit com o operador de um único qubit dado nesse índice e `PauliI` em todos os outros índices.</span><span class="sxs-lookup"><span data-stu-id="cbd6c-105">Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.</span></span>

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="cbd6c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="cbd6c-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="cbd6c-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="cbd6c-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="cbd6c-108">Um operador pauli de um único qubit a ser colocado no local dado.</span><span class="sxs-lookup"><span data-stu-id="cbd6c-108">A single-qubit Pauli operator to be placed at the given location.</span></span>


### <a name="location--int"></a><span data-ttu-id="cbd6c-109">localização : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cbd6c-109">location : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cbd6c-110">Um índice tal `output[location] == pauli` que, onde `output` está a saída desta função.</span><span class="sxs-lookup"><span data-stu-id="cbd6c-110">An index such that `output[location] == pauli`, where `output` is the output of this function.</span></span>


### <a name="n--int"></a><span data-ttu-id="cbd6c-111">n : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cbd6c-111">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cbd6c-112">Comprimento da matriz a ser devolvido.</span><span class="sxs-lookup"><span data-stu-id="cbd6c-112">Length of the array to be returned.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="cbd6c-113">Saída : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="cbd6c-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

