---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: Função EmbedPauli
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: c78406aa4557834ac2bb40cf1847696d075e5135
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716197"
---
# <a name="embedpauli-function"></a><span data-ttu-id="be81e-102">Função EmbedPauli</span><span class="sxs-lookup"><span data-stu-id="be81e-102">EmbedPauli function</span></span>

<span data-ttu-id="be81e-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="be81e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="be81e-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="be81e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="be81e-105">Dado um operador pauli de um único qubit e o índice de um qubit, devolve um operador Pauli multi-qubit com o operador de um único qubit dado nesse índice e `PauliI` em todos os outros índices.</span><span class="sxs-lookup"><span data-stu-id="be81e-105">Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.</span></span>

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="be81e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="be81e-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="be81e-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="be81e-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="be81e-108">Um operador pauli de um único qubit a ser colocado no local dado.</span><span class="sxs-lookup"><span data-stu-id="be81e-108">A single-qubit Pauli operator to be placed at the given location.</span></span>


### <a name="location--int"></a><span data-ttu-id="be81e-109">localização : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="be81e-109">location : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="be81e-110">Um índice tal `output[location] == pauli` que, onde `output` está a saída desta função.</span><span class="sxs-lookup"><span data-stu-id="be81e-110">An index such that `output[location] == pauli`, where `output` is the output of this function.</span></span>


### <a name="n--int"></a><span data-ttu-id="be81e-111">n : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="be81e-111">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="be81e-112">Comprimento da matriz a ser devolvido.</span><span class="sxs-lookup"><span data-stu-id="be81e-112">Length of the array to be returned.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="be81e-113">Saída : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="be81e-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

