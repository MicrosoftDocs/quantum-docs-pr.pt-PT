---
uid: Microsoft.Quantum.Arrays.IndexOf
title: Indexação da função
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 7ff80f13f432a18f216b2dee4bd65b1e82034fa5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719171"
---
# <a name="indexof-function"></a><span data-ttu-id="a063b-102">Indexação da função</span><span class="sxs-lookup"><span data-stu-id="a063b-102">IndexOf function</span></span>

<span data-ttu-id="a063b-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a063b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a063b-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a063b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a063b-105">Devolve o primeiro índice do primeiro elemento numa matriz que satisfaz um dado predicado.</span><span class="sxs-lookup"><span data-stu-id="a063b-105">Returns the first index of the first element in an array that satisfies a given predicate.</span></span> <span data-ttu-id="a063b-106">Se não existir tal elemento, de volta -1.</span><span class="sxs-lookup"><span data-stu-id="a063b-106">If no such element exists, returns -1.</span></span>

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="a063b-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="a063b-107">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="a063b-108">predicado: 'T-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a063b-108">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a063b-109">Uma função predicado agindo sobre elementos da matriz.</span><span class="sxs-lookup"><span data-stu-id="a063b-109">A predicate function acting on elements of the array.</span></span>


### <a name="arr--t"></a><span data-ttu-id="a063b-110">arr : 'T]]</span><span class="sxs-lookup"><span data-stu-id="a063b-110">arr : 'T[]</span></span>

<span data-ttu-id="a063b-111">Uma matriz a ser revistada usando o predicado dado.</span><span class="sxs-lookup"><span data-stu-id="a063b-111">An array to be searched using the given predicate.</span></span>



## <a name="output--int"></a><span data-ttu-id="a063b-112">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a063b-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a063b-113">Ou o menor índice `idx` que `predicate(arr[idx])` é verdade, ou -1 se tal elemento não existir.</span><span class="sxs-lookup"><span data-stu-id="a063b-113">Either the smallest index `idx` such that `predicate(arr[idx])` is true, or -1 if no such element exists.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a063b-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="a063b-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a063b-115">'T</span><span class="sxs-lookup"><span data-stu-id="a063b-115">'T</span></span>

