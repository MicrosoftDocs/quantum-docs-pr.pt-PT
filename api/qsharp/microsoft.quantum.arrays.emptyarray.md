---
uid: Microsoft.Quantum.Arrays.EmptyArray
title: Função EmptyArray
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EmptyArray
qsharp.summary: Returns the empty array of a given type.
ms.openlocfilehash: cf15e61862bb64fb3408db2318fafb56d532b365
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846181"
---
# <a name="emptyarray-function"></a><span data-ttu-id="46069-102">Função EmptyArray</span><span class="sxs-lookup"><span data-stu-id="46069-102">EmptyArray function</span></span>

<span data-ttu-id="46069-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="46069-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="46069-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="46069-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="46069-105">Devolve a matriz vazia de um determinado tipo.</span><span class="sxs-lookup"><span data-stu-id="46069-105">Returns the empty array of a given type.</span></span>

```qsharp
function EmptyArray<'TElement> () : 'TElement[]
```


## <a name="output--telement"></a><span data-ttu-id="46069-106">Saída : 'TElement[]</span><span class="sxs-lookup"><span data-stu-id="46069-106">Output : 'TElement[]</span></span>

<span data-ttu-id="46069-107">A matriz vazia.</span><span class="sxs-lookup"><span data-stu-id="46069-107">The empty array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="46069-108">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="46069-108">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="46069-109">'TElement</span><span class="sxs-lookup"><span data-stu-id="46069-109">'TElement</span></span>

<span data-ttu-id="46069-110">O tipo de elementos da matriz.</span><span class="sxs-lookup"><span data-stu-id="46069-110">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="46069-111">Exemplo</span><span class="sxs-lookup"><span data-stu-id="46069-111">Example</span></span>

```qsharp
let empty = EmptyArray<Int>();
```