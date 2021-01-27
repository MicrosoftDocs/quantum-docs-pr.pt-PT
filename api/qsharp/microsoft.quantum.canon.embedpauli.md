---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: Função EmbedPauli
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: 0e6a93e22ee495abcc44bdf522e7c72c0981308b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840524"
---
# <a name="embedpauli-function"></a><span data-ttu-id="89ad1-102">Função EmbedPauli</span><span class="sxs-lookup"><span data-stu-id="89ad1-102">EmbedPauli function</span></span>

<span data-ttu-id="89ad1-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="89ad1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="89ad1-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="89ad1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="89ad1-105">Dado um operador pauli de um único qubit e o índice de um qubit, devolve um operador Pauli multi-qubit com o operador de um único qubit dado nesse índice e `PauliI` em todos os outros índices.</span><span class="sxs-lookup"><span data-stu-id="89ad1-105">Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.</span></span>

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="89ad1-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="89ad1-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="89ad1-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="89ad1-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="89ad1-108">Um operador pauli de um único qubit a ser colocado no local dado.</span><span class="sxs-lookup"><span data-stu-id="89ad1-108">A single-qubit Pauli operator to be placed at the given location.</span></span>


### <a name="location--int"></a><span data-ttu-id="89ad1-109">localização : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="89ad1-109">location : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="89ad1-110">Um índice tal `output[location] == pauli` que, onde `output` está a saída desta função.</span><span class="sxs-lookup"><span data-stu-id="89ad1-110">An index such that `output[location] == pauli`, where `output` is the output of this function.</span></span>


### <a name="n--int"></a><span data-ttu-id="89ad1-111">n : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="89ad1-111">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="89ad1-112">Comprimento da matriz a ser devolvido.</span><span class="sxs-lookup"><span data-stu-id="89ad1-112">Length of the array to be returned.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="89ad1-113">Saída : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="89ad1-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="example"></a><span data-ttu-id="89ad1-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="89ad1-114">Example</span></span>

<span data-ttu-id="89ad1-115">Para obter a `[PauliI, PauliI, PauliX, PauliI]` matriz:</span><span class="sxs-lookup"><span data-stu-id="89ad1-115">To obtain the array `[PauliI, PauliI, PauliX, PauliI]`:</span></span>

```qsharp
EmbedPauli(PauliX, 2, 3);
```