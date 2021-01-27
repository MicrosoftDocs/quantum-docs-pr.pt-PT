---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Função intercalada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 3605c0d0bc43cdb1097d025861c3ec2424763c86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848117"
---
# <a name="interleaved-function"></a><span data-ttu-id="33c3b-102">Função intercalada</span><span class="sxs-lookup"><span data-stu-id="33c3b-102">Interleaved function</span></span>

<span data-ttu-id="33c3b-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="33c3b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="33c3b-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="33c3b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="33c3b-105">Entrelaça duas matrizes de (quase) mesmo tamanho.</span><span class="sxs-lookup"><span data-stu-id="33c3b-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="33c3b-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="33c3b-106">Description</span></span>

<span data-ttu-id="33c3b-107">Esta função devolve a interleaving de duas matrizes, começando com o primeiro elemento da primeira matriz, em seguida, o primeiro elemento da segunda matriz, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="33c3b-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="33c3b-108">A primeira matriz deve ter o mesmo comprimento que a segunda, ou pode ter mais um elemento.</span><span class="sxs-lookup"><span data-stu-id="33c3b-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="33c3b-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="33c3b-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="33c3b-110">primeiro : 'T[]</span><span class="sxs-lookup"><span data-stu-id="33c3b-110">first : 'T[]</span></span>

<span data-ttu-id="33c3b-111">A primeira matriz a ser intercalada.</span><span class="sxs-lookup"><span data-stu-id="33c3b-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="33c3b-112">segundo : 'T[]</span><span class="sxs-lookup"><span data-stu-id="33c3b-112">second : 'T[]</span></span>

<span data-ttu-id="33c3b-113">A segunda matriz a ser intercalada.</span><span class="sxs-lookup"><span data-stu-id="33c3b-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="33c3b-114">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="33c3b-114">Output : 'T[]</span></span>

<span data-ttu-id="33c3b-115">Matriz intercalada</span><span class="sxs-lookup"><span data-stu-id="33c3b-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="33c3b-116">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="33c3b-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="33c3b-117">'T</span><span class="sxs-lookup"><span data-stu-id="33c3b-117">'T</span></span>

<span data-ttu-id="33c3b-118">O tipo de cada elemento de `first` e `second` .</span><span class="sxs-lookup"><span data-stu-id="33c3b-118">The type of each element of `first` and `second`.</span></span>

## <a name="example"></a><span data-ttu-id="33c3b-119">Exemplo</span><span class="sxs-lookup"><span data-stu-id="33c3b-119">Example</span></span>

```qsharp
// same as int1 = [1, -1, 2, -2, 3, -3]
let int1 = Interleaved([1, 2, 3], [-1, -2, -3])

// same as int2 = [false, true, false, true, false]
let int2 = Interleaved(ConstantArray(3, false), ConstantArray(2, true));
```