---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: Função Não funcional daOpA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: 21df20354ad2388891f32b1bf1c7781287904983
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715217"
---
# <a name="uncurriedopa-function"></a><span data-ttu-id="af865-102">Função Não funcional daOpA</span><span class="sxs-lookup"><span data-stu-id="af865-102">UncurriedOpA function</span></span>

<span data-ttu-id="af865-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="af865-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="af865-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="af865-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="af865-105">Dada a função que devolve as operações, devolve uma nova operação que toma ambas as entradas como tuple.</span><span class="sxs-lookup"><span data-stu-id="af865-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="af865-106">O modificador `A` indica que as operações são adjacentes.</span><span class="sxs-lookup"><span data-stu-id="af865-106">The modifier `A` indicates that the operations are adjointable.</span></span>

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="af865-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="af865-107">Input</span></span>

### <a name="curriedop--t---u--unit-adj"></a><span data-ttu-id="af865-108">curriedOp : 'T-> 'U = [unidade](xref:microsoft.quantum.lang-ref.unit)> Adj</span><span class="sxs-lookup"><span data-stu-id="af865-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="af865-109">Uma função que devolve as operações.</span><span class="sxs-lookup"><span data-stu-id="af865-109">A function which returns operations.</span></span>



## <a name="output--tu--unit-adj"></a><span data-ttu-id="af865-110">Saída : ('T,'U) => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj</span><span class="sxs-lookup"><span data-stu-id="af865-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="af865-111">Uma nova operação `op` tal que `op(t, u)` equivale `(curriedOp(t))(u)` a.</span><span class="sxs-lookup"><span data-stu-id="af865-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="af865-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="af865-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="af865-113">'T</span><span class="sxs-lookup"><span data-stu-id="af865-113">'T</span></span>

<span data-ttu-id="af865-114">O tipo do primeiro argumento de uma função curada.</span><span class="sxs-lookup"><span data-stu-id="af865-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="af865-115">'U</span><span class="sxs-lookup"><span data-stu-id="af865-115">'U</span></span>

<span data-ttu-id="af865-116">O tipo do segundo argumento de uma função curada.</span><span class="sxs-lookup"><span data-stu-id="af865-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="af865-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="af865-117">See Also</span></span>

- [<span data-ttu-id="af865-118">Microsoft.Quantum.Canon.UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="af865-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)