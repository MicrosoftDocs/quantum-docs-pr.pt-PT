---
uid: Microsoft.Quantum.Arrays.Windows
title: Função do Windows
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: adfea2b9a2f6c22446817538d29586284dba723e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842202"
---
# <a name="windows-function"></a><span data-ttu-id="9830f-102">Função do Windows</span><span class="sxs-lookup"><span data-stu-id="9830f-102">Windows function</span></span>

<span data-ttu-id="9830f-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9830f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9830f-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9830f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9830f-105">Devolve todos os subarrays consecutivos de comprimento `size` .</span><span class="sxs-lookup"><span data-stu-id="9830f-105">Returns all consecutive subarrays of length `size`.</span></span>

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="9830f-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="9830f-106">Description</span></span>

<span data-ttu-id="9830f-107">Esta função devolve todos os `n - size + 1` subarrays de comprimento `size` em ordem, onde `n` é o comprimento de `arr` .</span><span class="sxs-lookup"><span data-stu-id="9830f-107">This function returns all `n - size + 1` subarrays of length `size` in order, where `n` is the length of `arr`.</span></span>
<span data-ttu-id="9830f-108">Os primeiros subarrays são `arr[0..size - 1], arr[1..size], arr[2..size + 1]` até à última subarray. `arr[n - size..n - 1]`</span><span class="sxs-lookup"><span data-stu-id="9830f-108">The first subarrays are `arr[0..size - 1], arr[1..size], arr[2..size + 1]` until the last subarray `arr[n - size..n - 1]`.</span></span>

<span data-ttu-id="9830f-109">Se `size <= 0` `size > n` ou, uma matriz vazia é devolvida.</span><span class="sxs-lookup"><span data-stu-id="9830f-109">If `size <= 0` or `size > n`, an empty array is returned.</span></span>

## <a name="input"></a><span data-ttu-id="9830f-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="9830f-110">Input</span></span>

### <a name="size--int"></a><span data-ttu-id="9830f-111">tamanho : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9830f-111">size : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9830f-112">Comprimento dos subarrays.</span><span class="sxs-lookup"><span data-stu-id="9830f-112">Length of the subarrays.</span></span>


### <a name="array--t"></a><span data-ttu-id="9830f-113">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="9830f-113">array : 'T[]</span></span>

<span data-ttu-id="9830f-114">Uma variedade de elementos.</span><span class="sxs-lookup"><span data-stu-id="9830f-114">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="9830f-115">Saída : 'T[][]</span><span class="sxs-lookup"><span data-stu-id="9830f-115">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9830f-116">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="9830f-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9830f-117">'T</span><span class="sxs-lookup"><span data-stu-id="9830f-117">'T</span></span>

<span data-ttu-id="9830f-118">O tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="9830f-118">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="9830f-119">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9830f-119">Example</span></span>

```qsharp
// same as [[1, 2, 3], [2, 3, 4], [3, 4, 5]]
let windows = Windows(3, [1, 2, 3, 4, 5]);
```