---
uid: Microsoft.Quantum.Logical.NotEqualB
title: Função NotEqualB
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 9f362b9e08f8a798bf7f7d9c323fee6576dccd9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814413"
---
# <a name="notequalb-function"></a><span data-ttu-id="055ae-102">Função NotEqualB</span><span class="sxs-lookup"><span data-stu-id="055ae-102">NotEqualB function</span></span>

<span data-ttu-id="055ae-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="055ae-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="055ae-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="055ae-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="055ae-105">Retorna verdadeira se e somente se duas entradas não forem iguais.</span><span class="sxs-lookup"><span data-stu-id="055ae-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="055ae-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="055ae-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="055ae-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="055ae-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="055ae-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="055ae-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="055ae-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="055ae-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="055ae-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="055ae-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="055ae-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="055ae-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="055ae-112">`true` se e somente `a` se não for igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="055ae-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="055ae-113">Observações</span><span class="sxs-lookup"><span data-stu-id="055ae-113">Remarks</span></span>

<span data-ttu-id="055ae-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="055ae-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualB(a, b);
```