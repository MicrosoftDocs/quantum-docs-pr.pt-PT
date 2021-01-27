---
uid: Microsoft.Quantum.Arrays.Subarray
title: Função subarray
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: ccc041da0213d1f5dc5c8b4ff7a03b8b01ad107d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845425"
---
# <a name="subarray-function"></a><span data-ttu-id="cad0a-102">Função subarray</span><span class="sxs-lookup"><span data-stu-id="cad0a-102">Subarray function</span></span>

<span data-ttu-id="cad0a-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="cad0a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="cad0a-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cad0a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cad0a-105">Pega numa matriz e numa lista de locais e produz uma nova matriz formada a partir dos elementos da matriz original que combinam com os locais dados.</span><span class="sxs-lookup"><span data-stu-id="cad0a-105">Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.</span></span>

```qsharp
function Subarray<'T> (indices : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="cad0a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="cad0a-106">Input</span></span>

### <a name="indices--int"></a><span data-ttu-id="cad0a-107">índices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="cad0a-107">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="cad0a-108">Uma lista de inteiros que é usado para definir a subarray.</span><span class="sxs-lookup"><span data-stu-id="cad0a-108">A list of integers that is used to define the subarray.</span></span>


### <a name="array--t"></a><span data-ttu-id="cad0a-109">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="cad0a-109">array : 'T[]</span></span>

<span data-ttu-id="cad0a-110">Uma série de elementos sobre `'T` .</span><span class="sxs-lookup"><span data-stu-id="cad0a-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="cad0a-111">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="cad0a-111">Output : 'T[]</span></span>

<span data-ttu-id="cad0a-112">Uma série `out` de elementos cujos índices correspondem à subarray, de tal forma que `out[idx] == array[indices[idx]]` . .</span><span class="sxs-lookup"><span data-stu-id="cad0a-112">An array `out` of elements whose indices correspond to the subarray, such that `out[idx] == array[indices[idx]]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="cad0a-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="cad0a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cad0a-114">'T</span><span class="sxs-lookup"><span data-stu-id="cad0a-114">'T</span></span>

<span data-ttu-id="cad0a-115">O tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="cad0a-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="cad0a-116">Observações</span><span class="sxs-lookup"><span data-stu-id="cad0a-116">Remarks</span></span>

<span data-ttu-id="cad0a-117">A função é definida para tipos genéricos, ou seja, sempre que temos uma matriz `'T[]` e uma lista de locais que `Int[]` definem a subarray.</span><span class="sxs-lookup"><span data-stu-id="cad0a-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a list of locations `Int[]` defining the subarray.</span></span>
<span data-ttu-id="cad0a-118">A construção da subarray baseia-se na geração de uma nova cópia profunda da matriz dada em oposição à manutenção de referências.</span><span class="sxs-lookup"><span data-stu-id="cad0a-118">The construction of the subarray is a based on generating a new, deep copy of the given array as opposed to maintaining references.</span></span>

<span data-ttu-id="cad0a-119">Se `Length(indices) < Length(array)` esta função devolver um subconjunto de `array` .</span><span class="sxs-lookup"><span data-stu-id="cad0a-119">If `Length(indices) < Length(array)`, this function will return a subset of `array`.</span></span> <span data-ttu-id="cad0a-120">Por outro lado, se `indices` contiver elementos repetidos, os elementos correspondentes `array` serão igualmente repetidos.</span><span class="sxs-lookup"><span data-stu-id="cad0a-120">On the other hand, if `indices` contains repeated elements, the corresponding elements of `array` will likewise be repeated.</span></span>
<span data-ttu-id="cad0a-121">Se `indices` e tiver o mesmo `array` comprimento, esta função fornece permutações de `array` .</span><span class="sxs-lookup"><span data-stu-id="cad0a-121">If `indices` and `array` are the same length, this function provides permutations of `array`.</span></span>