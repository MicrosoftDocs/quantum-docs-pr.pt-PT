---
uid: Microsoft.Quantum.Arrays.Reversed
title: Função invertida
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 99244195e581dc00db24b938f5aa1c541cd4433a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718907"
---
# <a name="reversed-function"></a><span data-ttu-id="89a66-102">Função invertida</span><span class="sxs-lookup"><span data-stu-id="89a66-102">Reversed function</span></span>

<span data-ttu-id="89a66-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="89a66-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="89a66-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="89a66-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="89a66-105">Crie uma matriz que contenha os mesmos elementos que uma matriz de entrada, mas em ordem invertida.</span><span class="sxs-lookup"><span data-stu-id="89a66-105">Create an array that contains the same elements as an input array but in Reversed order.</span></span>

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="89a66-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="89a66-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="89a66-107">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="89a66-107">array : 'T[]</span></span>

<span data-ttu-id="89a66-108">Uma matriz cujos elementos devem ser copiados por ordem inversa.</span><span class="sxs-lookup"><span data-stu-id="89a66-108">An array whose elements are to be copied in Reversed order.</span></span>



## <a name="output--t"></a><span data-ttu-id="89a66-109">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="89a66-109">Output : 'T[]</span></span>

<span data-ttu-id="89a66-110">Uma matriz contendo os `array[Length(array) - 1]` elementos..</span><span class="sxs-lookup"><span data-stu-id="89a66-110">An array containing the elements `array[Length(array) - 1]` ..</span></span> <span data-ttu-id="89a66-111">`array[0]`.</span><span class="sxs-lookup"><span data-stu-id="89a66-111">`array[0]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="89a66-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="89a66-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="89a66-113">'T</span><span class="sxs-lookup"><span data-stu-id="89a66-113">'T</span></span>

<span data-ttu-id="89a66-114">O tipo de elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="89a66-114">The type of the array elements.</span></span>