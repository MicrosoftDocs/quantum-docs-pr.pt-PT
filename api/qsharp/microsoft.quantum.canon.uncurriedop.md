---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: Função UncurriedOp
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: cad508f166d4af805cb98cd21a0260d9babb6a4c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204645"
---
# <a name="uncurriedop-function"></a><span data-ttu-id="a2754-102">Função UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="a2754-102">UncurriedOp function</span></span>

<span data-ttu-id="a2754-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a2754-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a2754-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a2754-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a2754-105">Dada a função que devolve as operações, devolve uma nova operação que toma ambas as entradas como tuple.</span><span class="sxs-lookup"><span data-stu-id="a2754-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a><span data-ttu-id="a2754-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a2754-106">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="a2754-107">curriedOp : 'T-> 'U = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="a2754-107">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a2754-108">Uma função que devolve as operações.</span><span class="sxs-lookup"><span data-stu-id="a2754-108">A function which returns operations.</span></span>



## <a name="output--tu--unit"></a><span data-ttu-id="a2754-109">Saída : ('T,'U) = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="a2754-109">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a2754-110">Uma nova operação `op` tal que `op(t, u)` equivale `(curriedOp(t))(u)` a.</span><span class="sxs-lookup"><span data-stu-id="a2754-110">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a2754-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="a2754-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a2754-112">'T</span><span class="sxs-lookup"><span data-stu-id="a2754-112">'T</span></span>

<span data-ttu-id="a2754-113">O tipo de primeira entrada para uma operação com cura.</span><span class="sxs-lookup"><span data-stu-id="a2754-113">The type of the first input to a curried operation.</span></span>
### <a name="u"></a><span data-ttu-id="a2754-114">'U</span><span class="sxs-lookup"><span data-stu-id="a2754-114">'U</span></span>

<span data-ttu-id="a2754-115">O tipo da segunda entrada para uma operação com cura.</span><span class="sxs-lookup"><span data-stu-id="a2754-115">The type of the second input to a curried operation.</span></span>

## <a name="see-also"></a><span data-ttu-id="a2754-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a2754-116">See Also</span></span>

- [<span data-ttu-id="a2754-117">Microsoft.Quantum.Canon.UncurriedOpC</span><span class="sxs-lookup"><span data-stu-id="a2754-117">Microsoft.Quantum.Canon.UncurriedOpC</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [<span data-ttu-id="a2754-118">Microsoft.Quantum.Canon.UncurriedOpA</span><span class="sxs-lookup"><span data-stu-id="a2754-118">Microsoft.Quantum.Canon.UncurriedOpA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [<span data-ttu-id="a2754-119">Microsoft.Quantum.Canon.UncurriedOpCA</span><span class="sxs-lookup"><span data-stu-id="a2754-119">Microsoft.Quantum.Canon.UncurriedOpCA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpCA)