---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: Com a função ComZeroInsertedAt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 7d5f8838b6ae555524fb0e82e14f93e6c77e43d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855202"
---
# <a name="withzeroinsertedat-function"></a><span data-ttu-id="ecb4e-102">Com a função ComZeroInsertedAt</span><span class="sxs-lookup"><span data-stu-id="ecb4e-102">WithZeroInsertedAt function</span></span>

<span data-ttu-id="ecb4e-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="ecb4e-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="ecb4e-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ecb4e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ecb4e-105">Insira um 0-bit num inteiro</span><span class="sxs-lookup"><span data-stu-id="ecb4e-105">Insert a 0-bit into an integer</span></span>

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a><span data-ttu-id="ecb4e-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="ecb4e-106">Description</span></span>

<span data-ttu-id="ecb4e-107">Esta operação requer um inteiro, insere um 0 em `position` pouco, e devolve o valor atualizado como um inteiro.</span><span class="sxs-lookup"><span data-stu-id="ecb4e-107">This operation takes an integer, inserts a 0 at bit `position`, and returns the updated value as an integer.</span></span>  <span data-ttu-id="ecb4e-108">Por exemplo, inserir um 0 na posição 2 no número 10 ($10_ {10} = 1010_ {2} $) devolve o número 18 ($18_ {10} = 10010_ {2} $).</span><span class="sxs-lookup"><span data-stu-id="ecb4e-108">For example, inserting a 0 at position 2 in the number 10 ($10_{10} = 1010_{2}$) returns the number 18 ($18_{10} = 10010_{2}$).</span></span>

## <a name="input"></a><span data-ttu-id="ecb4e-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="ecb4e-109">Input</span></span>

### <a name="position--int"></a><span data-ttu-id="ecb4e-110">posição : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ecb4e-110">position : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ecb4e-111">A posição em que 0 é inserido</span><span class="sxs-lookup"><span data-stu-id="ecb4e-111">The position at which 0 is inserted</span></span>


### <a name="value--int"></a><span data-ttu-id="ecb4e-112">valor : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ecb4e-112">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ecb4e-113">O valor que é modificado</span><span class="sxs-lookup"><span data-stu-id="ecb4e-113">The value that is modified</span></span>



## <a name="output--int"></a><span data-ttu-id="ecb4e-114">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ecb4e-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ecb4e-115">Valor modificado</span><span class="sxs-lookup"><span data-stu-id="ecb4e-115">Modified value</span></span>