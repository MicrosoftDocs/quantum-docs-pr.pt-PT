---
uid: Microsoft.Quantum.Arrays.Flattened
title: Função achatada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 331b1714109259b21982e99d030aa0662e3aaadb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221220"
---
# <a name="flattened-function"></a><span data-ttu-id="bf3bf-102">Função achatada</span><span class="sxs-lookup"><span data-stu-id="bf3bf-102">Flattened function</span></span>

<span data-ttu-id="bf3bf-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bf3bf-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bf3bf-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bf3bf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bf3bf-105">Dada uma variedade de matrizes, devolve a concatenação de todas as matrizes.</span><span class="sxs-lookup"><span data-stu-id="bf3bf-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="bf3bf-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="bf3bf-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="bf3bf-107">matrizes : 'T[][]</span><span class="sxs-lookup"><span data-stu-id="bf3bf-107">arrays : 'T[][]</span></span>

<span data-ttu-id="bf3bf-108">Conjunto de matrizes.</span><span class="sxs-lookup"><span data-stu-id="bf3bf-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="bf3bf-109">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="bf3bf-109">Output : 'T[]</span></span>

<span data-ttu-id="bf3bf-110">Concatenação de todas as matrizes.</span><span class="sxs-lookup"><span data-stu-id="bf3bf-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bf3bf-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="bf3bf-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bf3bf-112">'T</span><span class="sxs-lookup"><span data-stu-id="bf3bf-112">'T</span></span>

<span data-ttu-id="bf3bf-113">O tipo de `array` elementos.</span><span class="sxs-lookup"><span data-stu-id="bf3bf-113">The type of `array` elements.</span></span>