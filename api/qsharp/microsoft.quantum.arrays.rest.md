---
uid: Microsoft.Quantum.Arrays.Rest
title: Função de repouso
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: b6c579df354185a2defb08cd78bce816d8cc5959
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845485"
---
# <a name="rest-function"></a><span data-ttu-id="38ea3-102">Função de repouso</span><span class="sxs-lookup"><span data-stu-id="38ea3-102">Rest function</span></span>

<span data-ttu-id="38ea3-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="38ea3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="38ea3-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="38ea3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="38ea3-105">Cria uma matriz que é igual a uma matriz de entrada, exceto que o primeiro elemento de matriz é largado.</span><span class="sxs-lookup"><span data-stu-id="38ea3-105">Creates an array that is equal to an input array except that the first array element is dropped.</span></span>

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="38ea3-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="38ea3-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="38ea3-107">matriz : 'T[]</span><span class="sxs-lookup"><span data-stu-id="38ea3-107">array : 'T[]</span></span>

<span data-ttu-id="38ea3-108">Uma matriz cujos segundos e últimos elementos são para formar a matriz de saída.</span><span class="sxs-lookup"><span data-stu-id="38ea3-108">An array whose second to last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="38ea3-109">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="38ea3-109">Output : 'T[]</span></span>

<span data-ttu-id="38ea3-110">Uma matriz contendo os `array[1..Length(array) - 1]` elementos.</span><span class="sxs-lookup"><span data-stu-id="38ea3-110">An array containing the elements `array[1..Length(array) - 1]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="38ea3-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="38ea3-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="38ea3-112">'T</span><span class="sxs-lookup"><span data-stu-id="38ea3-112">'T</span></span>

<span data-ttu-id="38ea3-113">O tipo de elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="38ea3-113">The type of the array elements.</span></span>