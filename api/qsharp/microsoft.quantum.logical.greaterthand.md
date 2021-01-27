---
uid: Microsoft.Quantum.Logical.GreaterThanD
title: Função GreaterThanD
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanD
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 26a963645758b6de83654304c38830af5c561b3a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849224"
---
# <a name="greaterthand-function"></a><span data-ttu-id="af192-102">Função GreaterThanD</span><span class="sxs-lookup"><span data-stu-id="af192-102">GreaterThanD function</span></span>

<span data-ttu-id="af192-103">Espaço de nome: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="af192-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="af192-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="af192-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="af192-105">Retorna verdadeira se e somente se um número for maior que outro número.</span><span class="sxs-lookup"><span data-stu-id="af192-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="af192-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="af192-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="af192-107">a : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="af192-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="af192-108">O primeiro valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="af192-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="af192-109">b : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="af192-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="af192-110">O segundo valor a ser comparado.</span><span class="sxs-lookup"><span data-stu-id="af192-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="af192-111">Saída : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="af192-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="af192-112">`true` se e somente se `a` for estritamente maior do que `b` .</span><span class="sxs-lookup"><span data-stu-id="af192-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="af192-113">Observações</span><span class="sxs-lookup"><span data-stu-id="af192-113">Remarks</span></span>

<span data-ttu-id="af192-114">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="af192-114">The following are equivalent:</span></span>

```qsharp
let cond = a > b;
let cond = GreaterThanD(a, b);
```