---
uid: Microsoft.Quantum.Arrays.Reversed
title: Função invertida
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 50699465711de45ff994095e6c098550d637d608
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845462"
---
# <a name="reversed-function"></a><span data-ttu-id="c525b-102">Função invertida</span><span class="sxs-lookup"><span data-stu-id="c525b-102">Reversed function</span></span>

<span data-ttu-id="c525b-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c525b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c525b-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c525b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c525b-105">Crie uma matriz que contenha os mesmos elementos que uma matriz de entrada, mas em ordem invertida.</span><span class="sxs-lookup"><span data-stu-id="c525b-105">Create an array that contains the same elements as an input array but in Reversed order.</span></span>

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="c525b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c525b-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="c525b-107">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="c525b-107">array : 'T[]</span></span>

<span data-ttu-id="c525b-108">Uma matriz cujos elementos devem ser copiados por ordem inversa.</span><span class="sxs-lookup"><span data-stu-id="c525b-108">An array whose elements are to be copied in Reversed order.</span></span>



## <a name="output--t"></a><span data-ttu-id="c525b-109">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="c525b-109">Output : 'T[]</span></span>

<span data-ttu-id="c525b-110">Uma matriz contendo os `array[Length(array) - 1]` elementos..</span><span class="sxs-lookup"><span data-stu-id="c525b-110">An array containing the elements `array[Length(array) - 1]` ..</span></span> <span data-ttu-id="c525b-111">`array[0]`.</span><span class="sxs-lookup"><span data-stu-id="c525b-111">`array[0]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c525b-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="c525b-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c525b-113">'T</span><span class="sxs-lookup"><span data-stu-id="c525b-113">'T</span></span>

<span data-ttu-id="c525b-114">O tipo de elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="c525b-114">The type of the array elements.</span></span>