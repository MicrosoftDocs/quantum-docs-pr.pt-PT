---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: Função de procuraçãoFunction
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: db20795719d11138cbdc5a38c0a19d0f247af059
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220778"
---
# <a name="lookupfunction-function"></a><span data-ttu-id="741ab-102">Função de procuraçãoFunction</span><span class="sxs-lookup"><span data-stu-id="741ab-102">LookupFunction function</span></span>

<span data-ttu-id="741ab-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="741ab-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="741ab-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="741ab-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="741ab-105">Dada uma matriz, devolve uma função que devolve elementos dessa matriz.</span><span class="sxs-lookup"><span data-stu-id="741ab-105">Given an array, returns a function which returns elements of that array.</span></span>

```qsharp
function LookupFunction<'T> (array : 'T[]) : (Int -> 'T)
```


## <a name="input"></a><span data-ttu-id="741ab-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="741ab-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="741ab-107">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="741ab-107">array : 'T[]</span></span>

<span data-ttu-id="741ab-108">A matriz a ser representada como uma função de procuração.</span><span class="sxs-lookup"><span data-stu-id="741ab-108">The array to be represented as a lookup function.</span></span>



## <a name="output--int---t"></a><span data-ttu-id="741ab-109">Saída : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span><span class="sxs-lookup"><span data-stu-id="741ab-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="741ab-110">Uma função `f` de tal forma `f(idx) == f[idx]` que.</span><span class="sxs-lookup"><span data-stu-id="741ab-110">A function `f` such that `f(idx) == f[idx]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="741ab-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="741ab-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="741ab-112">'T</span><span class="sxs-lookup"><span data-stu-id="741ab-112">'T</span></span>

<span data-ttu-id="741ab-113">O tipo de elementos da matriz sendo representados como uma função de procuração.</span><span class="sxs-lookup"><span data-stu-id="741ab-113">The type of the elements of the array being represented as a lookup function.</span></span>

## <a name="remarks"></a><span data-ttu-id="741ab-114">Observações</span><span class="sxs-lookup"><span data-stu-id="741ab-114">Remarks</span></span>

<span data-ttu-id="741ab-115">Esta função é principalmente útil para a interoperação com funções e operações que assumem `Int -> 'T` funções como seus argumentos.</span><span class="sxs-lookup"><span data-stu-id="741ab-115">This function is mainly useful for interoperating with functions and operations that take `Int -> 'T` functions as their arguments.</span></span> <span data-ttu-id="741ab-116">Isto é comum, por exemplo, na biblioteca de representação do gerador, onde as funções são usadas para evitar a necessidade de registar um conjunto inteiro na memória.</span><span class="sxs-lookup"><span data-stu-id="741ab-116">This is common, for instance, in the generator representation library, where functions are used to avoid the need to record an entire array in memory.</span></span>