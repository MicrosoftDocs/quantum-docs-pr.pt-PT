---
uid: Microsoft.Quantum.Arrays.IsSorted
title: Função IsSorted
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsSorted
qsharp.summary: Given an array, returns whether that array is sorted as defined by a given comparison function.
ms.openlocfilehash: a5916b5cbf36e1b6c421a81e04016a333e2b5be7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845726"
---
# <a name="issorted-function"></a><span data-ttu-id="e7bab-102">Função IsSorted</span><span class="sxs-lookup"><span data-stu-id="e7bab-102">IsSorted function</span></span>

<span data-ttu-id="e7bab-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e7bab-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e7bab-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e7bab-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e7bab-105">Dada uma matriz, devolve se essa matriz é classificada como definida por uma determinada função de comparação.</span><span class="sxs-lookup"><span data-stu-id="e7bab-105">Given an array, returns whether that array is sorted as defined by a given comparison function.</span></span>

```qsharp
function IsSorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="e7bab-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e7bab-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="e7bab-107">comparação: ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e7bab-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e7bab-108">Uma função que compara dois elementos tais que `a` são considerados inferiores ou iguais a `b` se for `comparison(a, b)` `true` .</span><span class="sxs-lookup"><span data-stu-id="e7bab-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="e7bab-109">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="e7bab-109">array : 'T[]</span></span>

<span data-ttu-id="e7bab-110">A matriz a ser verificada.</span><span class="sxs-lookup"><span data-stu-id="e7bab-110">The array to be checked.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e7bab-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e7bab-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e7bab-112">`true` se e somente se para cada par de elementos `a` e de ocorrer por esta `b` `array` ordem, é `comparison(a, b)` `true` .</span><span class="sxs-lookup"><span data-stu-id="e7bab-112">`true` if and only if for each pair of elements `a` and `b` of `array` occuring in that order, `comparison(a, b)` is `true`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e7bab-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="e7bab-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e7bab-114">'T</span><span class="sxs-lookup"><span data-stu-id="e7bab-114">'T</span></span>

<span data-ttu-id="e7bab-115">O tipo de cada elemento de `array` .</span><span class="sxs-lookup"><span data-stu-id="e7bab-115">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e7bab-116">Observações</span><span class="sxs-lookup"><span data-stu-id="e7bab-116">Remarks</span></span>

<span data-ttu-id="e7bab-117">A função `comparison` é assumida como transitiva, de tal forma que se `comparison(a, b)` e , `comparison(b, c)` `comparison(a, c)` então, é assumido.</span><span class="sxs-lookup"><span data-stu-id="e7bab-117">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="e7bab-118">Se esta propriedade não tiver, então a saída desta função pode estar incorreta.</span><span class="sxs-lookup"><span data-stu-id="e7bab-118">If this property does not hold, then the output of this function may be incorrect.</span></span>