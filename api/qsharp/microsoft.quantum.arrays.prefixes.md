---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Prefixa a função
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 3501c11437534b1623bffba272a4517487e5634a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220398"
---
# <a name="prefixes-function"></a><span data-ttu-id="13911-102">Prefixa a função</span><span class="sxs-lookup"><span data-stu-id="13911-102">Prefixes function</span></span>

<span data-ttu-id="13911-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="13911-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="13911-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="13911-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="13911-105">Dada uma matriz, devolve todos os seus prefixos.</span><span class="sxs-lookup"><span data-stu-id="13911-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="13911-106">Description</span><span class="sxs-lookup"><span data-stu-id="13911-106">Description</span></span>

<span data-ttu-id="13911-107">Devolve uma matriz de todos os prefixos, começando com uma matriz que só tem o primeiro elemento até à matriz completa.</span><span class="sxs-lookup"><span data-stu-id="13911-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="13911-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="13911-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="13911-109">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="13911-109">array : 'T[]</span></span>

<span data-ttu-id="13911-110">Uma variedade de elementos.</span><span class="sxs-lookup"><span data-stu-id="13911-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="13911-111">Saída : 'T[][]</span><span class="sxs-lookup"><span data-stu-id="13911-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="13911-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="13911-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="13911-113">'T</span><span class="sxs-lookup"><span data-stu-id="13911-113">'T</span></span>

<span data-ttu-id="13911-114">O tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="13911-114">The type of `array` elements.</span></span>