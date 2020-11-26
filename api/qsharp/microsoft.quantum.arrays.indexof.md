---
uid: Microsoft.Quantum.Arrays.IndexOf
title: Indexação da função
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: d63b204334611f8f2c3860f9ee1d756f637780e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221016"
---
# <a name="indexof-function"></a><span data-ttu-id="0f336-102">Indexação da função</span><span class="sxs-lookup"><span data-stu-id="0f336-102">IndexOf function</span></span>

<span data-ttu-id="0f336-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0f336-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0f336-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0f336-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0f336-105">Devolve o primeiro índice do primeiro elemento numa matriz que satisfaz um dado predicado.</span><span class="sxs-lookup"><span data-stu-id="0f336-105">Returns the first index of the first element in an array that satisfies a given predicate.</span></span> <span data-ttu-id="0f336-106">Se não existir tal elemento, de volta -1.</span><span class="sxs-lookup"><span data-stu-id="0f336-106">If no such element exists, returns -1.</span></span>

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="0f336-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="0f336-107">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="0f336-108">predicado: 'T-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0f336-108">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0f336-109">Uma função predicado agindo sobre elementos da matriz.</span><span class="sxs-lookup"><span data-stu-id="0f336-109">A predicate function acting on elements of the array.</span></span>


### <a name="arr--t"></a><span data-ttu-id="0f336-110">arr : 'T]]</span><span class="sxs-lookup"><span data-stu-id="0f336-110">arr : 'T[]</span></span>

<span data-ttu-id="0f336-111">Uma matriz a ser revistada usando o predicado dado.</span><span class="sxs-lookup"><span data-stu-id="0f336-111">An array to be searched using the given predicate.</span></span>



## <a name="output--int"></a><span data-ttu-id="0f336-112">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0f336-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0f336-113">Ou o menor índice `idx` que `predicate(arr[idx])` é verdade, ou -1 se tal elemento não existir.</span><span class="sxs-lookup"><span data-stu-id="0f336-113">Either the smallest index `idx` such that `predicate(arr[idx])` is true, or -1 if no such element exists.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0f336-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="0f336-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0f336-115">'T</span><span class="sxs-lookup"><span data-stu-id="0f336-115">'T</span></span>

