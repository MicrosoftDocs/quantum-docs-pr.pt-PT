---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: Função ConstantArray
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: a3ad8a18856888a0ca6f9dd691242156b0c044d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846233"
---
# <a name="constantarray-function"></a><span data-ttu-id="a5828-102">Função ConstantArray</span><span class="sxs-lookup"><span data-stu-id="a5828-102">ConstantArray function</span></span>

<span data-ttu-id="a5828-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a5828-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a5828-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a5828-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a5828-105">Cria uma matriz de comprimento dado com todos os elementos iguais ao valor dado.</span><span class="sxs-lookup"><span data-stu-id="a5828-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="a5828-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a5828-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="a5828-107">comprimento : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a5828-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a5828-108">Comprimento da nova matriz.</span><span class="sxs-lookup"><span data-stu-id="a5828-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="a5828-109">valor : 'T</span><span class="sxs-lookup"><span data-stu-id="a5828-109">value : 'T</span></span>

<span data-ttu-id="a5828-110">O valor de cada elemento da nova matriz.</span><span class="sxs-lookup"><span data-stu-id="a5828-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="a5828-111">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="a5828-111">Output : 'T[]</span></span>

<span data-ttu-id="a5828-112">Uma nova matriz de `length` comprimento, de tal forma que cada elemento é `value` .</span><span class="sxs-lookup"><span data-stu-id="a5828-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a5828-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="a5828-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a5828-114">'T</span><span class="sxs-lookup"><span data-stu-id="a5828-114">'T</span></span>



## <a name="example"></a><span data-ttu-id="a5828-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a5828-115">Example</span></span>

<span data-ttu-id="a5828-116">O seguinte código cria uma matriz de 3 valores booleanas, cada um igual `true` a:</span><span class="sxs-lookup"><span data-stu-id="a5828-116">The following code creates an array of 3 Boolean values, each equal to `true`:</span></span>

```qsharp
let array = ConstantArray(3, true);
```