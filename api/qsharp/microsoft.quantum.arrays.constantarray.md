---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: Função ConstantArray
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 848f18944829d08a10ec602dcb5d99c100c81f76
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719411"
---
# <a name="constantarray-function"></a><span data-ttu-id="066b2-102">Função ConstantArray</span><span class="sxs-lookup"><span data-stu-id="066b2-102">ConstantArray function</span></span>

<span data-ttu-id="066b2-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="066b2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="066b2-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="066b2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="066b2-105">Cria uma matriz de comprimento dado com todos os elementos iguais ao valor dado.</span><span class="sxs-lookup"><span data-stu-id="066b2-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="066b2-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="066b2-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="066b2-107">comprimento : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="066b2-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="066b2-108">Comprimento da nova matriz.</span><span class="sxs-lookup"><span data-stu-id="066b2-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="066b2-109">valor : 'T</span><span class="sxs-lookup"><span data-stu-id="066b2-109">value : 'T</span></span>

<span data-ttu-id="066b2-110">O valor de cada elemento da nova matriz.</span><span class="sxs-lookup"><span data-stu-id="066b2-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="066b2-111">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="066b2-111">Output : 'T[]</span></span>

<span data-ttu-id="066b2-112">Uma nova matriz de `length` comprimento, de tal forma que cada elemento é `value` .</span><span class="sxs-lookup"><span data-stu-id="066b2-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="066b2-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="066b2-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="066b2-114">'T</span><span class="sxs-lookup"><span data-stu-id="066b2-114">'T</span></span>

