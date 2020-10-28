---
uid: Microsoft.Quantum.Synthesis.DecompositionState
title: Decomposição Esclarou o tipo definido pelo utilizador
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecompositionState
qsharp.summary: State during decomposition based on variable indexes
ms.openlocfilehash: 0547c04828a80b4f696cc17e13c8cc57d0379f96
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725214"
---
# <a name="decompositionstate-user-defined-type"></a><span data-ttu-id="e9ca7-102">Decomposição Esclarou o tipo definido pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="e9ca7-102">DecompositionState user defined type</span></span>

<span data-ttu-id="e9ca7-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="e9ca7-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="e9ca7-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e9ca7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e9ca7-105">Estado durante a decomposição com base em índices variáveis</span><span class="sxs-lookup"><span data-stu-id="e9ca7-105">State during decomposition based on variable indexes</span></span>

```qsharp

newtype DecompositionState = (Perm : Int[], Lfunctions : (BigInt, Int)[], Rfunctions : (BigInt, Int)[]);
```



## <a name="named-items"></a><span data-ttu-id="e9ca7-106">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="e9ca7-106">Named Items</span></span>

### <a name="perm--int"></a><span data-ttu-id="e9ca7-107">Perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e9ca7-107">Perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>


### <a name="lfunctions--bigintint"></a><span data-ttu-id="e9ca7-108">Funções : ([BigInt,](xref:microsoft.quantum.lang-ref.bigint)[Int](xref:microsoft.quantum.lang-ref.int))[]</span><span class="sxs-lookup"><span data-stu-id="e9ca7-108">Lfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>


### <a name="rfunctions--bigintint"></a><span data-ttu-id="e9ca7-109">Rfunctions : ([BigInt,](xref:microsoft.quantum.lang-ref.bigint)[Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e9ca7-109">Rfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>



## <a name="description"></a><span data-ttu-id="e9ca7-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="e9ca7-110">Description</span></span>

<span data-ttu-id="e9ca7-111">O Estado detém a permutação atual e as funções atualmente geradas para portões controlados à esquerda, e portões controlados à direita.</span><span class="sxs-lookup"><span data-stu-id="e9ca7-111">The state holds the current permutation and the currently generated functions for controlled gates on the left, and controlled gates on the right.</span></span>