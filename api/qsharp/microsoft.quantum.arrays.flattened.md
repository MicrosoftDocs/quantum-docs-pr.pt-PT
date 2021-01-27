---
uid: Microsoft.Quantum.Arrays.Flattened
title: Função achatada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 272533d4efd8598b21daa341c867c070a2083ce0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848621"
---
# <a name="flattened-function"></a><span data-ttu-id="18583-102">Função achatada</span><span class="sxs-lookup"><span data-stu-id="18583-102">Flattened function</span></span>

<span data-ttu-id="18583-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="18583-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="18583-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="18583-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="18583-105">Dada uma variedade de matrizes, devolve a concatenação de todas as matrizes.</span><span class="sxs-lookup"><span data-stu-id="18583-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="18583-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="18583-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="18583-107">matrizes : 'T[][]</span><span class="sxs-lookup"><span data-stu-id="18583-107">arrays : 'T[][]</span></span>

<span data-ttu-id="18583-108">Conjunto de matrizes.</span><span class="sxs-lookup"><span data-stu-id="18583-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="18583-109">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="18583-109">Output : 'T[]</span></span>

<span data-ttu-id="18583-110">Concatenação de todas as matrizes.</span><span class="sxs-lookup"><span data-stu-id="18583-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="18583-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="18583-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="18583-112">'T</span><span class="sxs-lookup"><span data-stu-id="18583-112">'T</span></span>

<span data-ttu-id="18583-113">O tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="18583-113">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="18583-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="18583-114">Example</span></span>

```qsharp
let flattened = Flattened([[1, 2], [3], [4, 5, 6]]);
// flattened = [1, 2, 3, 4, 5, 6]
```