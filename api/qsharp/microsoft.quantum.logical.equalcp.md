---
uid: Microsoft.Quantum.Logical.EqualCP
title: Função EqualCP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualCP
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: e3175b9b6fd2890963de0452102e2f0de1026b91
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198236"
---
# <a name="equalcp-function"></a><span data-ttu-id="ccc11-102">Função EqualCP</span><span class="sxs-lookup"><span data-stu-id="ccc11-102">EqualCP function</span></span>

<span data-ttu-id="ccc11-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="ccc11-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="ccc11-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ccc11-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ccc11-105">Retorna verdadeira se e somente se duas entradas forem iguais.</span><span class="sxs-lookup"><span data-stu-id="ccc11-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="ccc11-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ccc11-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="ccc11-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="ccc11-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="ccc11-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="ccc11-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="ccc11-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="ccc11-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="ccc11-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="ccc11-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ccc11-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ccc11-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ccc11-112">`true` se e somente se `a` for igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="ccc11-112">`true` if and only if `a` is equal to `b`.</span></span>