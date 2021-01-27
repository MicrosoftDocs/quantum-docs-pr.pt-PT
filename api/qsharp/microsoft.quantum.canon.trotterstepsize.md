---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: Função TrotterStepSize
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: c7b6432645dcad2bd47c62b91e04e0b42cd04ca9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840076"
---
# <a name="trotterstepsize-function"></a><span data-ttu-id="3ea82-102">Função TrotterStepSize</span><span class="sxs-lookup"><span data-stu-id="3ea82-102">TrotterStepSize function</span></span>

<span data-ttu-id="3ea82-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3ea82-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3ea82-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3ea82-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3ea82-105">Computes Trotter tamanho do passo na implementação recursiva do algoritmo de simulação Trotter.</span><span class="sxs-lookup"><span data-stu-id="3ea82-105">Computes Trotter step size in recursive implementation of Trotter simulation algorithm.</span></span>

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a><span data-ttu-id="3ea82-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3ea82-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="3ea82-107">ordem : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3ea82-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--double"></a><span data-ttu-id="3ea82-108">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3ea82-108">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="3ea82-109">Observações</span><span class="sxs-lookup"><span data-stu-id="3ea82-109">Remarks</span></span>

<span data-ttu-id="3ea82-110">Esta operação utiliza uma convenção de indexação diferente da de [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span><span class="sxs-lookup"><span data-stu-id="3ea82-110">This operation uses a different indexing convention than that of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span> <span data-ttu-id="3ea82-111">Em particular, `DecomposedIntoTimeStepsCA(_, 4)` corresponde ao escalão $p_2(\lambda)$ em quant-ph/0508139.</span><span class="sxs-lookup"><span data-stu-id="3ea82-111">In particular, `DecomposedIntoTimeStepsCA(_, 4)` corresponds to the scalar $p_2(\lambda)$ in quant-ph/0508139.</span></span>