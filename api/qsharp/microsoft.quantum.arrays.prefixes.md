---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Prefixa a função
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 1576e57e9dc64a605eb65cb841640e72a3b126ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718942"
---
# <a name="prefixes-function"></a><span data-ttu-id="e49f7-102">Prefixa a função</span><span class="sxs-lookup"><span data-stu-id="e49f7-102">Prefixes function</span></span>

<span data-ttu-id="e49f7-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e49f7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e49f7-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e49f7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e49f7-105">Dada uma matriz, devolve todos os seus prefixos.</span><span class="sxs-lookup"><span data-stu-id="e49f7-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="e49f7-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="e49f7-106">Description</span></span>

<span data-ttu-id="e49f7-107">Devolve uma matriz de todos os prefixos, começando com uma matriz que só tem o primeiro elemento até à matriz completa.</span><span class="sxs-lookup"><span data-stu-id="e49f7-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="e49f7-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="e49f7-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="e49f7-109">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="e49f7-109">array : 'T[]</span></span>

<span data-ttu-id="e49f7-110">Uma variedade de elementos.</span><span class="sxs-lookup"><span data-stu-id="e49f7-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="e49f7-111">Saída : 'T[][]</span><span class="sxs-lookup"><span data-stu-id="e49f7-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e49f7-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="e49f7-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e49f7-113">'T</span><span class="sxs-lookup"><span data-stu-id="e49f7-113">'T</span></span>

<span data-ttu-id="e49f7-114">O tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="e49f7-114">The type of `array` elements.</span></span>