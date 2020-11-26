---
uid: Microsoft.Quantum.Logical.Xor
title: Função Xor
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: afb94bd1fd0b791a9a7d84bc28b0cc2baf9a0938
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197097"
---
# <a name="xor-function"></a><span data-ttu-id="f6b7c-102">Função Xor</span><span class="sxs-lookup"><span data-stu-id="f6b7c-102">Xor function</span></span>

<span data-ttu-id="f6b7c-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f6b7c-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f6b7c-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f6b7c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f6b7c-105">Devolve a disjunção exclusiva booleana de dois valores.</span><span class="sxs-lookup"><span data-stu-id="f6b7c-105">Returns the Boolean exclusive disjunction of two values.</span></span>

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="f6b7c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f6b7c-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="f6b7c-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f6b7c-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f6b7c-108">O primeiro valor a ser considerado.</span><span class="sxs-lookup"><span data-stu-id="f6b7c-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="f6b7c-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f6b7c-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f6b7c-110">O segundo valor a considerar.</span><span class="sxs-lookup"><span data-stu-id="f6b7c-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f6b7c-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f6b7c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f6b7c-112">`true` se e somente se exatamente um dos `a` e `b` é `true` .</span><span class="sxs-lookup"><span data-stu-id="f6b7c-112">`true` if and only if exactly one of `a` and `b` is `true`.</span></span>