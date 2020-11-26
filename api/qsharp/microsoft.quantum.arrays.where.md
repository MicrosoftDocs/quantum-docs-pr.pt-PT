---
uid: Microsoft.Quantum.Arrays.Where
title: Onde funciona
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 97598aa25d2d085aaab94f3d60ee64db9e2b89d6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219928"
---
# <a name="where-function"></a><span data-ttu-id="09a55-102">Onde funciona</span><span class="sxs-lookup"><span data-stu-id="09a55-102">Where function</span></span>

<span data-ttu-id="09a55-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="09a55-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="09a55-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="09a55-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="09a55-105">Dado um predicado e uma matriz, devolve os índices daquela matriz onde o predicado é verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="09a55-105">Given a predicate and an array, returns the indices of that array where the predicate is true.</span></span>

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="09a55-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="09a55-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="09a55-107">predicado: 'T-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="09a55-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="09a55-108">Uma função de `'T` Boolean que é usada para filtrar elementos.</span><span class="sxs-lookup"><span data-stu-id="09a55-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="09a55-109">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="09a55-109">array : 'T[]</span></span>

<span data-ttu-id="09a55-110">Uma série de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="09a55-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="09a55-111">Saída : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="09a55-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="09a55-112">Uma série de índices onde `predicate` é verdade.</span><span class="sxs-lookup"><span data-stu-id="09a55-112">An array of indices where `predicate` is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="09a55-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="09a55-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="09a55-114">'T</span><span class="sxs-lookup"><span data-stu-id="09a55-114">'T</span></span>

<span data-ttu-id="09a55-115">O tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="09a55-115">The type of `array` elements.</span></span>