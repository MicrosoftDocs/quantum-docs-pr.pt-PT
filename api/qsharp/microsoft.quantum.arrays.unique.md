---
uid: Microsoft.Quantum.Arrays.Unique
title: Função única
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: c5d40bb82f2de640e9c78eef0c27e4766b477826
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718786"
---
# <a name="unique-function"></a><span data-ttu-id="2ec26-102">Função única</span><span class="sxs-lookup"><span data-stu-id="2ec26-102">Unique function</span></span>

<span data-ttu-id="2ec26-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2ec26-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2ec26-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2ec26-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2ec26-105">Devolve uma nova matriz que não tem elementos adjacentes iguais.</span><span class="sxs-lookup"><span data-stu-id="2ec26-105">Returns a new array that has no equal adjacent elements.</span></span>

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="2ec26-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="2ec26-106">Description</span></span>

<span data-ttu-id="2ec26-107">Dada a variedade de elementos e uma função para testar a igualdade, esta função devolve uma nova matriz na qual a ordem relativa dos elementos é mantida, mas todos os elementos adjacentes que são iguais são filtrados a apenas um elemento.</span><span class="sxs-lookup"><span data-stu-id="2ec26-107">Given some array of elements and a function to test equality, this function returns a new array in which the relative order of elements is kept, but all adjacent elements which are equal are filtered to just a single element.</span></span>

## <a name="input"></a><span data-ttu-id="2ec26-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="2ec26-108">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="2ec26-109">igual: ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2ec26-109">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2ec26-110">Uma função que compara dois elementos tais que `a` são considerados iguais a `b` se `equal(a, b)` for `true` .</span><span class="sxs-lookup"><span data-stu-id="2ec26-110">A function that compares two elements such that `a` is considered to be equal to `b` if `equal(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="2ec26-111">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="2ec26-111">array : 'T[]</span></span>

<span data-ttu-id="2ec26-112">A matriz a ser filtrada para elementos únicos.</span><span class="sxs-lookup"><span data-stu-id="2ec26-112">The array to be filtered for unique elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="2ec26-113">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="2ec26-113">Output : 'T[]</span></span>

<span data-ttu-id="2ec26-114">Matriz sem elementos adjacentes iguais.</span><span class="sxs-lookup"><span data-stu-id="2ec26-114">Array with no equal adjacent elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2ec26-115">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="2ec26-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2ec26-116">'T</span><span class="sxs-lookup"><span data-stu-id="2ec26-116">'T</span></span>

<span data-ttu-id="2ec26-117">O tipo de cada elemento de `array` .</span><span class="sxs-lookup"><span data-stu-id="2ec26-117">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2ec26-118">Observações</span><span class="sxs-lookup"><span data-stu-id="2ec26-118">Remarks</span></span>

<span data-ttu-id="2ec26-119">Se houver vários elementos iguais, mas não próximos uns dos outros, haverá múltiplas ocorrências na matriz de saída.</span><span class="sxs-lookup"><span data-stu-id="2ec26-119">If there are multiple elements that are equal but not next to each other, there will be multiple occurrences in the output array.</span></span>  <span data-ttu-id="2ec26-120">Utilize esta função juntamente com `Sorted` para obter uma matriz com elementos únicos em geral.</span><span class="sxs-lookup"><span data-stu-id="2ec26-120">Use this function together with `Sorted` to get an array with overall unique elements.</span></span>