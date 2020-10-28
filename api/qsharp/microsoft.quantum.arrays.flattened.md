---
uid: Microsoft.Quantum.Arrays.Flattened
title: Função achatada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 91a35f0ac2c2f8609bac07734265fcf4e88bf50b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719242"
---
# <a name="flattened-function"></a><span data-ttu-id="8ed5d-102">Função achatada</span><span class="sxs-lookup"><span data-stu-id="8ed5d-102">Flattened function</span></span>

<span data-ttu-id="8ed5d-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8ed5d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8ed5d-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8ed5d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8ed5d-105">Dada uma variedade de matrizes, devolve a concatenação de todas as matrizes.</span><span class="sxs-lookup"><span data-stu-id="8ed5d-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="8ed5d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8ed5d-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="8ed5d-107">matrizes : 'T[][]</span><span class="sxs-lookup"><span data-stu-id="8ed5d-107">arrays : 'T[][]</span></span>

<span data-ttu-id="8ed5d-108">Conjunto de matrizes.</span><span class="sxs-lookup"><span data-stu-id="8ed5d-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="8ed5d-109">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="8ed5d-109">Output : 'T[]</span></span>

<span data-ttu-id="8ed5d-110">Concatenação de todas as matrizes.</span><span class="sxs-lookup"><span data-stu-id="8ed5d-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8ed5d-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="8ed5d-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8ed5d-112">'T</span><span class="sxs-lookup"><span data-stu-id="8ed5d-112">'T</span></span>

<span data-ttu-id="8ed5d-113">O tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="8ed5d-113">The type of `array` elements.</span></span>