---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Prefixa a função
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: a2e1721f8f59bf9aa425f04710637023d482a2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845515"
---
# <a name="prefixes-function"></a><span data-ttu-id="28514-102">Prefixa a função</span><span class="sxs-lookup"><span data-stu-id="28514-102">Prefixes function</span></span>

<span data-ttu-id="28514-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="28514-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="28514-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="28514-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="28514-105">Dada uma matriz, devolve todos os seus prefixos.</span><span class="sxs-lookup"><span data-stu-id="28514-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="28514-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="28514-106">Description</span></span>

<span data-ttu-id="28514-107">Devolve uma matriz de todos os prefixos, começando com uma matriz que só tem o primeiro elemento até à matriz completa.</span><span class="sxs-lookup"><span data-stu-id="28514-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="28514-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="28514-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="28514-109">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="28514-109">array : 'T[]</span></span>

<span data-ttu-id="28514-110">Uma variedade de elementos.</span><span class="sxs-lookup"><span data-stu-id="28514-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="28514-111">Saída : 'T[][]</span><span class="sxs-lookup"><span data-stu-id="28514-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="28514-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="28514-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="28514-113">'T</span><span class="sxs-lookup"><span data-stu-id="28514-113">'T</span></span>

<span data-ttu-id="28514-114">O tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="28514-114">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="28514-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="28514-115">Example</span></span>

```qsharp
let prefixes = Prefixes([23, 42, 144]);
// prefixes = [[23], [23, 42], [23, 42, 144]]
```