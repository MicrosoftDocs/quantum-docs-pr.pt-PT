---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Função intercalada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 1ff5999cc19f47e3dcae601b960446923b613d90
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220965"
---
# <a name="interleaved-function"></a><span data-ttu-id="4f74c-102">Função intercalada</span><span class="sxs-lookup"><span data-stu-id="4f74c-102">Interleaved function</span></span>

<span data-ttu-id="4f74c-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4f74c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4f74c-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4f74c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4f74c-105">Entrelaça duas matrizes de (quase) mesmo tamanho.</span><span class="sxs-lookup"><span data-stu-id="4f74c-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="4f74c-106">Description</span><span class="sxs-lookup"><span data-stu-id="4f74c-106">Description</span></span>

<span data-ttu-id="4f74c-107">Esta função devolve a interleaving de duas matrizes, começando com o primeiro elemento da primeira matriz, em seguida, o primeiro elemento da segunda matriz, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="4f74c-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="4f74c-108">A primeira matriz deve ter o mesmo comprimento que a segunda, ou pode ter mais um elemento.</span><span class="sxs-lookup"><span data-stu-id="4f74c-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="4f74c-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="4f74c-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="4f74c-110">primeiro : 'T[]</span><span class="sxs-lookup"><span data-stu-id="4f74c-110">first : 'T[]</span></span>

<span data-ttu-id="4f74c-111">A primeira matriz a ser intercalada.</span><span class="sxs-lookup"><span data-stu-id="4f74c-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="4f74c-112">segundo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="4f74c-112">second : 'T[]</span></span>

<span data-ttu-id="4f74c-113">A segunda matriz a ser intercalada.</span><span class="sxs-lookup"><span data-stu-id="4f74c-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="4f74c-114">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="4f74c-114">Output : 'T[]</span></span>

<span data-ttu-id="4f74c-115">Matriz intercalada</span><span class="sxs-lookup"><span data-stu-id="4f74c-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4f74c-116">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="4f74c-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4f74c-117">'T</span><span class="sxs-lookup"><span data-stu-id="4f74c-117">'T</span></span>

<span data-ttu-id="4f74c-118">O tipo de cada elemento de `first` e `second` .</span><span class="sxs-lookup"><span data-stu-id="4f74c-118">The type of each element of `first` and `second`.</span></span>