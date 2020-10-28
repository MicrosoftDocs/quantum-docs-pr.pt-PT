---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: Com a função ComZeroInsertedAt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 6e13251741dadb19740b208cdfc13a14964a48dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725158"
---
# <a name="withzeroinsertedat-function"></a><span data-ttu-id="d060c-102">Com a função ComZeroInsertedAt</span><span class="sxs-lookup"><span data-stu-id="d060c-102">WithZeroInsertedAt function</span></span>

<span data-ttu-id="d060c-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="d060c-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="d060c-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d060c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d060c-105">Insira um 0-bit num inteiro</span><span class="sxs-lookup"><span data-stu-id="d060c-105">Insert a 0-bit into an integer</span></span>

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a><span data-ttu-id="d060c-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="d060c-106">Description</span></span>

<span data-ttu-id="d060c-107">Esta operação requer um inteiro, insere um 0 em `position` pouco, e devolve o valor atualizado como um inteiro.</span><span class="sxs-lookup"><span data-stu-id="d060c-107">This operation takes an integer, inserts a 0 at bit `position`, and returns the updated value as an integer.</span></span>  <span data-ttu-id="d060c-108">Por exemplo, inserir um 0 na posição 2 no número 10 ($10_ {10} = 1010_ {2} $) devolve o número 18 ($18_ {10} = 10010_ {2} $).</span><span class="sxs-lookup"><span data-stu-id="d060c-108">For example, inserting a 0 at position 2 in the number 10 ($10_{10} = 1010_{2}$) returns the number 18 ($18_{10} = 10010_{2}$).</span></span>

## <a name="input"></a><span data-ttu-id="d060c-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="d060c-109">Input</span></span>

### <a name="position--int"></a><span data-ttu-id="d060c-110">posição : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d060c-110">position : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d060c-111">A posição em que 0 é inserido</span><span class="sxs-lookup"><span data-stu-id="d060c-111">The position at which 0 is inserted</span></span>


### <a name="value--int"></a><span data-ttu-id="d060c-112">valor : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d060c-112">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d060c-113">O valor que é modificado</span><span class="sxs-lookup"><span data-stu-id="d060c-113">The value that is modified</span></span>



## <a name="output--int"></a><span data-ttu-id="d060c-114">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d060c-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d060c-115">Valor modificado</span><span class="sxs-lookup"><span data-stu-id="d060c-115">Modified value</span></span>