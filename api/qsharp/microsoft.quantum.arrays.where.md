---
uid: Microsoft.Quantum.Arrays.Where
title: Onde funciona
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 4a938114689177f7a9ee182e6e5f36debe4edac7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842208"
---
# <a name="where-function"></a><span data-ttu-id="dc8b5-102">Onde funciona</span><span class="sxs-lookup"><span data-stu-id="dc8b5-102">Where function</span></span>

<span data-ttu-id="dc8b5-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="dc8b5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="dc8b5-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dc8b5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dc8b5-105">Dado um predicado e uma matriz, devolve os índices daquela matriz onde o predicado é verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="dc8b5-105">Given a predicate and an array, returns the indices of that array where the predicate is true.</span></span>

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="dc8b5-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="dc8b5-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="dc8b5-107">predicado: 'T-> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="dc8b5-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="dc8b5-108">Uma função de `'T` Boolean que é usada para filtrar elementos.</span><span class="sxs-lookup"><span data-stu-id="dc8b5-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="dc8b5-109">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="dc8b5-109">array : 'T[]</span></span>

<span data-ttu-id="dc8b5-110">Uma série de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="dc8b5-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="dc8b5-111">Saída : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="dc8b5-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="dc8b5-112">Uma série de índices onde `predicate` é verdade.</span><span class="sxs-lookup"><span data-stu-id="dc8b5-112">An array of indices where `predicate` is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="dc8b5-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="dc8b5-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dc8b5-114">'T</span><span class="sxs-lookup"><span data-stu-id="dc8b5-114">'T</span></span>

<span data-ttu-id="dc8b5-115">O tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="dc8b5-115">The type of `array` elements.</span></span>