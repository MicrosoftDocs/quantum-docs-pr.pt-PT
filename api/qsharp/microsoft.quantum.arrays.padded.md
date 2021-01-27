---
uid: Microsoft.Quantum.Arrays.Padded
title: Função acolchoada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 556e5f5175ee54470a99f32c037eeb2cd80588d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845568"
---
# <a name="padded-function"></a><span data-ttu-id="ca741-102">Função acolchoada</span><span class="sxs-lookup"><span data-stu-id="ca741-102">Padded function</span></span>

<span data-ttu-id="ca741-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ca741-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ca741-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ca741-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ca741-105">Devolve uma matriz acolchoada com valores especificados até um comprimento especificado.</span><span class="sxs-lookup"><span data-stu-id="ca741-105">Returns an array padded at with specified values up to a specified length.</span></span>

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="ca741-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ca741-106">Input</span></span>

### <a name="nelementstotal--int"></a><span data-ttu-id="ca741-107">nElementsTotal : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ca741-107">nElementsTotal : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ca741-108">O comprimento da matriz acolchoada.</span><span class="sxs-lookup"><span data-stu-id="ca741-108">The length of the padded array.</span></span> <span data-ttu-id="ca741-109">Se isto for positivo, `inputArray` é acolchoado na cabeça.</span><span class="sxs-lookup"><span data-stu-id="ca741-109">If this is positive, `inputArray` is padded at the head.</span></span> <span data-ttu-id="ca741-110">Se isto for negativo, `inputArray` é acolchoado na cauda.</span><span class="sxs-lookup"><span data-stu-id="ca741-110">If this is negative, `inputArray` is padded at the tail.</span></span>


### <a name="defaultelement--t"></a><span data-ttu-id="ca741-111">defaultElement : 'T</span><span class="sxs-lookup"><span data-stu-id="ca741-111">defaultElement : 'T</span></span>

<span data-ttu-id="ca741-112">Valor predefinido a utilizar para elementos de enchimento.</span><span class="sxs-lookup"><span data-stu-id="ca741-112">Default value to use for padding elements.</span></span>


### <a name="inputarray--t"></a><span data-ttu-id="ca741-113">inputArray : 'T[]</span><span class="sxs-lookup"><span data-stu-id="ca741-113">inputArray : 'T[]</span></span>

<span data-ttu-id="ca741-114">Matriz cujos valores estão na cabeça da matriz de saída.</span><span class="sxs-lookup"><span data-stu-id="ca741-114">Array whose values are at the head of the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="ca741-115">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="ca741-115">Output : 'T[]</span></span>

<span data-ttu-id="ca741-116">Uma matriz `output` que é o `inputArray` acolchoado na cabeça com `defaultElement` s até ter `output` comprimento `nElementsTotal`</span><span class="sxs-lookup"><span data-stu-id="ca741-116">An array `output` that is the `inputArray` padded at the head with `defaultElement`s until `output` has length `nElementsTotal`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ca741-117">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="ca741-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ca741-118">'T</span><span class="sxs-lookup"><span data-stu-id="ca741-118">'T</span></span>

<span data-ttu-id="ca741-119">O tipo de elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="ca741-119">The type of the array elements.</span></span>

## <a name="example"></a><span data-ttu-id="ca741-120">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ca741-120">Example</span></span>

```qsharp
let array = [10, 11, 12];
// The following line returns [10, 12, 15, 2, 2, 2].
let output = Padded(-6, array, 2);
// The following line returns [2, 2, 2, 10, 12, 15].
let output = Padded(6, array, 2);
```