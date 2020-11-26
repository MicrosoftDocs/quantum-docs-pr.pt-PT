---
uid: Microsoft.Quantum.Synthesis.DecompositionState
title: Decomposição Esclarou o tipo definido pelo utilizador
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecompositionState
qsharp.summary: State during decomposition based on variable indexes
ms.openlocfilehash: cd2a55013f1232d4158dd6c33143b7cf6c0aafbc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203200"
---
# <a name="decompositionstate-user-defined-type"></a><span data-ttu-id="04396-102">Decomposição Esclarou o tipo definido pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="04396-102">DecompositionState user defined type</span></span>

<span data-ttu-id="04396-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="04396-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="04396-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="04396-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="04396-105">Estado durante a decomposição com base em índices variáveis</span><span class="sxs-lookup"><span data-stu-id="04396-105">State during decomposition based on variable indexes</span></span>

```qsharp

newtype DecompositionState = (Perm : Int[], Lfunctions : (BigInt, Int)[], Rfunctions : (BigInt, Int)[]);
```



## <a name="named-items"></a><span data-ttu-id="04396-106">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="04396-106">Named Items</span></span>

### <a name="perm--int"></a><span data-ttu-id="04396-107">Perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="04396-107">Perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>


### <a name="lfunctions--bigintint"></a><span data-ttu-id="04396-108">Funções : ([BigInt,](xref:microsoft.quantum.lang-ref.bigint)[Int](xref:microsoft.quantum.lang-ref.int))[]</span><span class="sxs-lookup"><span data-stu-id="04396-108">Lfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>


### <a name="rfunctions--bigintint"></a><span data-ttu-id="04396-109">Rfunctions : ([BigInt,](xref:microsoft.quantum.lang-ref.bigint)[Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="04396-109">Rfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>



## <a name="description"></a><span data-ttu-id="04396-110">Description</span><span class="sxs-lookup"><span data-stu-id="04396-110">Description</span></span>

<span data-ttu-id="04396-111">O Estado detém a permutação atual e as funções atualmente geradas para portões controlados à esquerda, e portões controlados à direita.</span><span class="sxs-lookup"><span data-stu-id="04396-111">The state holds the current permutation and the currently generated functions for controlled gates on the left, and controlled gates on the right.</span></span>