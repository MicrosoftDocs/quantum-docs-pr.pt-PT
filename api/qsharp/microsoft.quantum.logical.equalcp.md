---
uid: Microsoft.Quantum.Logical.EqualCP
title: Função EqualCP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualCP
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 83bf5ba245038ad1c7c6ed4e8cdb493317276e6a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817150"
---
# <a name="equalcp-function"></a><span data-ttu-id="1ee82-102">Função EqualCP</span><span class="sxs-lookup"><span data-stu-id="1ee82-102">EqualCP function</span></span>

<span data-ttu-id="1ee82-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="1ee82-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="1ee82-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1ee82-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1ee82-105">Retorna verdadeira se e somente se duas entradas forem iguais.</span><span class="sxs-lookup"><span data-stu-id="1ee82-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="1ee82-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1ee82-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="1ee82-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="1ee82-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="1ee82-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="1ee82-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="1ee82-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="1ee82-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="1ee82-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="1ee82-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="1ee82-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1ee82-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1ee82-112">`true` se e somente se `a` for igual a `b` .</span><span class="sxs-lookup"><span data-stu-id="1ee82-112">`true` if and only if `a` is equal to `b`.</span></span>