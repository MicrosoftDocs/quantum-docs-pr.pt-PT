---
uid: Microsoft.Quantum.Logical.Not
title: Não funcionar
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: f2db43f4a2ce83d8cad1d60aa8c481a33b0c7d44
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197454"
---
# <a name="not-function"></a><span data-ttu-id="44c4f-102">Não funcionar</span><span class="sxs-lookup"><span data-stu-id="44c4f-102">Not function</span></span>

<span data-ttu-id="44c4f-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="44c4f-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="44c4f-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="44c4f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="44c4f-105">Devolve a negação booleana de um valor.</span><span class="sxs-lookup"><span data-stu-id="44c4f-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="44c4f-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="44c4f-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="44c4f-107">valor : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="44c4f-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="44c4f-108">O valor a ser negado.</span><span class="sxs-lookup"><span data-stu-id="44c4f-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="44c4f-109">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="44c4f-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="44c4f-110">`true` se e somente se `value` for `false` .</span><span class="sxs-lookup"><span data-stu-id="44c4f-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="44c4f-111">Observações</span><span class="sxs-lookup"><span data-stu-id="44c4f-111">Remarks</span></span>

<span data-ttu-id="44c4f-112">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="44c4f-112">The following are equivalent:</span></span>

```Q#
let x = not value;
let x = Not(value);
```