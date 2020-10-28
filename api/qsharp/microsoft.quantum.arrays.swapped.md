---
uid: Microsoft.Quantum.Arrays.Swapped
title: Função trocada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: fa5b37b4caf5d8f19ed05075ddd7bc4217036bfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718823"
---
# <a name="swapped-function"></a><span data-ttu-id="de6d5-102">Função trocada</span><span class="sxs-lookup"><span data-stu-id="de6d5-102">Swapped function</span></span>

<span data-ttu-id="de6d5-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="de6d5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="de6d5-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="de6d5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="de6d5-105">Aplica uma troca de dois elementos numa matriz.</span><span class="sxs-lookup"><span data-stu-id="de6d5-105">Applies a swap of two elements in an array.</span></span>

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="de6d5-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="de6d5-106">Input</span></span>

### <a name="firstindex--int"></a><span data-ttu-id="de6d5-107">firstIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="de6d5-107">firstIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="de6d5-108">Índice do primeiro elemento a ser trocado.</span><span class="sxs-lookup"><span data-stu-id="de6d5-108">Index of the first element to be swapped.</span></span>


### <a name="secondindex--int"></a><span data-ttu-id="de6d5-109">secondIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="de6d5-109">secondIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="de6d5-110">Índice do segundo elemento a ser trocado.</span><span class="sxs-lookup"><span data-stu-id="de6d5-110">Index of the second element to be swapped.</span></span>


### <a name="arr--t"></a><span data-ttu-id="de6d5-111">arr : 'T]]</span><span class="sxs-lookup"><span data-stu-id="de6d5-111">arr : 'T[]</span></span>

<span data-ttu-id="de6d5-112">Matriz com elementos a serem trocados.</span><span class="sxs-lookup"><span data-stu-id="de6d5-112">Array with elements to be swapped.</span></span>



## <a name="output--t"></a><span data-ttu-id="de6d5-113">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="de6d5-113">Output : 'T[]</span></span>

<span data-ttu-id="de6d5-114">A matriz com a troca de lugar aplicada.</span><span class="sxs-lookup"><span data-stu-id="de6d5-114">The array with the in place swap applied.</span></span>

## <a name="example"></a><span data-ttu-id="de6d5-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="de6d5-115">Example</span></span>

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a><span data-ttu-id="de6d5-116">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="de6d5-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="de6d5-117">'T</span><span class="sxs-lookup"><span data-stu-id="de6d5-117">'T</span></span>

