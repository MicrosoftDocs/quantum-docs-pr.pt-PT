---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: Função ConstantArray
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 8cba68af2f1e178a1ef96921283f85e4feb498ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210068"
---
# <a name="constantarray-function"></a><span data-ttu-id="01967-102">Função ConstantArray</span><span class="sxs-lookup"><span data-stu-id="01967-102">ConstantArray function</span></span>

<span data-ttu-id="01967-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="01967-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="01967-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="01967-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="01967-105">Cria uma matriz de comprimento dado com todos os elementos iguais ao valor dado.</span><span class="sxs-lookup"><span data-stu-id="01967-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="01967-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="01967-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="01967-107">comprimento : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="01967-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="01967-108">Comprimento da nova matriz.</span><span class="sxs-lookup"><span data-stu-id="01967-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="01967-109">valor : 'T</span><span class="sxs-lookup"><span data-stu-id="01967-109">value : 'T</span></span>

<span data-ttu-id="01967-110">O valor de cada elemento da nova matriz.</span><span class="sxs-lookup"><span data-stu-id="01967-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="01967-111">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="01967-111">Output : 'T[]</span></span>

<span data-ttu-id="01967-112">Uma nova matriz de `length` comprimento, de tal forma que cada elemento é `value` .</span><span class="sxs-lookup"><span data-stu-id="01967-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="01967-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="01967-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="01967-114">'T</span><span class="sxs-lookup"><span data-stu-id="01967-114">'T</span></span>

