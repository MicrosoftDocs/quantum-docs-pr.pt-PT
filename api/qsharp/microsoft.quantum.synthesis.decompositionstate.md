---
uid: Microsoft.Quantum.Synthesis.DecompositionState
title: Decomposição Esclarou o tipo definido pelo utilizador
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecompositionState
qsharp.summary: State during decomposition based on variable indexes
ms.openlocfilehash: eb2aed53b4116a4ea72ee732ff46c4a10eb3d67b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855511"
---
# <a name="decompositionstate-user-defined-type"></a><span data-ttu-id="b45d6-102">Decomposição Esclarou o tipo definido pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="b45d6-102">DecompositionState user defined type</span></span>

<span data-ttu-id="b45d6-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="b45d6-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="b45d6-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b45d6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b45d6-105">Estado durante a decomposição com base em índices variáveis</span><span class="sxs-lookup"><span data-stu-id="b45d6-105">State during decomposition based on variable indexes</span></span>

```qsharp

newtype DecompositionState = (Perm : Int[], Lfunctions : (BigInt, Int)[], Rfunctions : (BigInt, Int)[]);
```



## <a name="named-items"></a><span data-ttu-id="b45d6-106">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="b45d6-106">Named Items</span></span>

### <a name="perm--int"></a><span data-ttu-id="b45d6-107">Perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b45d6-107">Perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>


### <a name="lfunctions--bigintint"></a><span data-ttu-id="b45d6-108">Funções : ([BigInt,](xref:microsoft.quantum.lang-ref.bigint)[Int](xref:microsoft.quantum.lang-ref.int))[]</span><span class="sxs-lookup"><span data-stu-id="b45d6-108">Lfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>


### <a name="rfunctions--bigintint"></a><span data-ttu-id="b45d6-109">Rfunctions : ([BigInt,](xref:microsoft.quantum.lang-ref.bigint)[Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b45d6-109">Rfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>



## <a name="description"></a><span data-ttu-id="b45d6-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="b45d6-110">Description</span></span>

<span data-ttu-id="b45d6-111">O Estado detém a permutação atual e as funções atualmente geradas para portões controlados à esquerda, e portões controlados à direita.</span><span class="sxs-lookup"><span data-stu-id="b45d6-111">The state holds the current permutation and the currently generated functions for controlled gates on the left, and controlled gates on the right.</span></span>