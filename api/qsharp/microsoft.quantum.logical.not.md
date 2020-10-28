---
uid: Microsoft.Quantum.Logical.Not
title: Não funcionar
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: 3a688aac0178a2f4127496c1009fe7d5ee7ae198
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709866"
---
# <a name="not-function"></a><span data-ttu-id="765a2-102">Não funcionar</span><span class="sxs-lookup"><span data-stu-id="765a2-102">Not function</span></span>

<span data-ttu-id="765a2-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="765a2-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="765a2-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="765a2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="765a2-105">Devolve a negação booleana de um valor.</span><span class="sxs-lookup"><span data-stu-id="765a2-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="765a2-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="765a2-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="765a2-107">valor : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="765a2-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="765a2-108">O valor a ser negado.</span><span class="sxs-lookup"><span data-stu-id="765a2-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="765a2-109">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="765a2-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="765a2-110">`true` se e somente se `value` for `false` .</span><span class="sxs-lookup"><span data-stu-id="765a2-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="765a2-111">Observações</span><span class="sxs-lookup"><span data-stu-id="765a2-111">Remarks</span></span>

<span data-ttu-id="765a2-112">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="765a2-112">The following are equivalent:</span></span>

```Q#
let x = not value;
let x = Not(value);
```