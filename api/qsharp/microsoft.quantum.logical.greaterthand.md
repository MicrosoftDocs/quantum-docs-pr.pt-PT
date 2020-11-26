---
uid: Microsoft.Quantum.Logical.GreaterThanD
title: Função GreaterThanD
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanD
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: c23d85cf513bb6d37e67260eeeb3b81b42e6771a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198032"
---
# <a name="greaterthand-function"></a><span data-ttu-id="8f393-102">Função GreaterThanD</span><span class="sxs-lookup"><span data-stu-id="8f393-102">GreaterThanD function</span></span>

<span data-ttu-id="8f393-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="8f393-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="8f393-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8f393-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8f393-105">Retorna verdadeira se e somente se um número for maior que outro número.</span><span class="sxs-lookup"><span data-stu-id="8f393-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="8f393-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8f393-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="8f393-107">a : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8f393-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8f393-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="8f393-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="8f393-109">b : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8f393-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8f393-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="8f393-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="8f393-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8f393-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8f393-112">`true` se e somente se `a` for estritamente maior do que `b` .</span><span class="sxs-lookup"><span data-stu-id="8f393-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="8f393-113">Observações</span><span class="sxs-lookup"><span data-stu-id="8f393-113">Remarks</span></span>

<span data-ttu-id="8f393-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="8f393-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanD(a, b);
```