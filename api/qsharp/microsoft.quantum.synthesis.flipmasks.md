---
uid: Microsoft.Quantum.Synthesis.FlipMasks
title: Função FlipMasks
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FlipMasks
qsharp.summary: For every 2-level unitary calculates "flip mask", which denotes qubits which should be inverted before and after applying corresponding 1-qubit gate. For convenience prepends result with 0.
ms.openlocfilehash: ca0ce69b3353379a42cc109cebb32efe4e364825
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859206"
---
# <a name="flipmasks-function"></a><span data-ttu-id="5a2fc-102">Função FlipMasks</span><span class="sxs-lookup"><span data-stu-id="5a2fc-102">FlipMasks function</span></span>

<span data-ttu-id="5a2fc-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="5a2fc-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="5a2fc-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5a2fc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5a2fc-105">Para cada 2 níveis unitário calcula "flip mask", que denota qubits que devem ser invertidos antes e depois de aplicar o portão de 1 qubit correspondente.</span><span class="sxs-lookup"><span data-stu-id="5a2fc-105">For every 2-level unitary calculates "flip mask", which denotes qubits which should be inverted before and after applying corresponding 1-qubit gate.</span></span>
<span data-ttu-id="5a2fc-106">Para os preparativos de conveniência resultam com 0.</span><span class="sxs-lookup"><span data-stu-id="5a2fc-106">For convenience prepends result with 0.</span></span>

```qsharp
function FlipMasks (decomposition : (Microsoft.Quantum.Math.Complex[][], Int, Int)[], allQubitsMask : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="5a2fc-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="5a2fc-107">Input</span></span>

### <a name="decomposition--complexintint"></a><span data-ttu-id="5a2fc-108">decomposição:[(Complexo](xref:Microsoft.Quantum.Math.Complex)[],[Int,](xref:microsoft.quantum.lang-ref.int)[Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5a2fc-108">decomposition : ([Complex](xref:Microsoft.Quantum.Math.Complex)[][],[Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>




### <a name="allqubitsmask--int"></a><span data-ttu-id="5a2fc-109">allQubitsMask : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5a2fc-109">allQubitsMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="5a2fc-110">Saída : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5a2fc-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

