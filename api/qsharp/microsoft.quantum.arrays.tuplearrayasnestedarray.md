---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: TupleArrayAsNestedArray
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: 917f35db949790ab3ae6e7a2184bcfcf5ed50be6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718810"
---
# <a name="tuplearrayasnestedarray-function"></a><span data-ttu-id="c4d1c-102">TupleArrayAsNestedArray</span><span class="sxs-lookup"><span data-stu-id="c4d1c-102">TupleArrayAsNestedArray function</span></span>

<span data-ttu-id="c4d1c-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c4d1c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c4d1c-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c4d1c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c4d1c-105">Transforma uma lista de 2 tuples numa matriz aninhada.</span><span class="sxs-lookup"><span data-stu-id="c4d1c-105">Turns a list of 2-tuples into a nested array.</span></span>

```qsharp
function TupleArrayAsNestedArray<'T> (tupleList : ('T, 'T)[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="c4d1c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c4d1c-106">Input</span></span>

### <a name="tuplelist--tt"></a><span data-ttu-id="c4d1c-107">tupleList : ('T,'T)[]</span><span class="sxs-lookup"><span data-stu-id="c4d1c-107">tupleList : ('T,'T)[]</span></span>

<span data-ttu-id="c4d1c-108">Lista de 2 tuples para ser transformado em uma matriz aninhada.</span><span class="sxs-lookup"><span data-stu-id="c4d1c-108">List of 2-tuples to be turned into a nested array.</span></span>



## <a name="output--t"></a><span data-ttu-id="c4d1c-109">Saída : 'T[][]</span><span class="sxs-lookup"><span data-stu-id="c4d1c-109">Output : 'T[][]</span></span>

<span data-ttu-id="c4d1c-110">Uma matriz aninhada com comprimento correspondente à tupleList.</span><span class="sxs-lookup"><span data-stu-id="c4d1c-110">A nested array with length matching the tupleList.</span></span>

## <a name="example"></a><span data-ttu-id="c4d1c-111">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c4d1c-111">Example</span></span>

```qsharp
// The following returns [[2, 3], [4, 5]]
TupleArrayAsNestedArray([(2, 3), (4, 5)]);
```

## <a name="type-parameters"></a><span data-ttu-id="c4d1c-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="c4d1c-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c4d1c-113">'T</span><span class="sxs-lookup"><span data-stu-id="c4d1c-113">'T</span></span>

