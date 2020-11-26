---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: TupleArrayAsNestedArray
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: c898178b6385b27f753509f0748a8b666b5066bd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220081"
---
# <a name="tuplearrayasnestedarray-function"></a><span data-ttu-id="b7129-102">TupleArrayAsNestedArray</span><span class="sxs-lookup"><span data-stu-id="b7129-102">TupleArrayAsNestedArray function</span></span>

<span data-ttu-id="b7129-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b7129-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b7129-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b7129-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b7129-105">Transforma uma lista de 2 tuples numa matriz aninhada.</span><span class="sxs-lookup"><span data-stu-id="b7129-105">Turns a list of 2-tuples into a nested array.</span></span>

```qsharp
function TupleArrayAsNestedArray<'T> (tupleList : ('T, 'T)[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="b7129-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b7129-106">Input</span></span>

### <a name="tuplelist--tt"></a><span data-ttu-id="b7129-107">tupleList : ('T,'T)[]</span><span class="sxs-lookup"><span data-stu-id="b7129-107">tupleList : ('T,'T)[]</span></span>

<span data-ttu-id="b7129-108">Lista de 2 tuples para ser transformado em uma matriz aninhada.</span><span class="sxs-lookup"><span data-stu-id="b7129-108">List of 2-tuples to be turned into a nested array.</span></span>



## <a name="output--t"></a><span data-ttu-id="b7129-109">Saída : 'T[][]</span><span class="sxs-lookup"><span data-stu-id="b7129-109">Output : 'T[][]</span></span>

<span data-ttu-id="b7129-110">Uma matriz aninhada com comprimento correspondente à tupleList.</span><span class="sxs-lookup"><span data-stu-id="b7129-110">A nested array with length matching the tupleList.</span></span>

## <a name="example"></a><span data-ttu-id="b7129-111">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b7129-111">Example</span></span>

```qsharp
// The following returns [[2, 3], [4, 5]]
TupleArrayAsNestedArray([(2, 3), (4, 5)]);
```

## <a name="type-parameters"></a><span data-ttu-id="b7129-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="b7129-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b7129-113">'T</span><span class="sxs-lookup"><span data-stu-id="b7129-113">'T</span></span>

