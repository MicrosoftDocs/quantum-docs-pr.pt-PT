---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: Função Não curadaopCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 6a0f2e1b345d0ba3ac5c779c5dc2bfffaf659a0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715203"
---
# <a name="uncurriedopca-function"></a><span data-ttu-id="dde3f-102">Função Não curadaopCA</span><span class="sxs-lookup"><span data-stu-id="dde3f-102">UncurriedOpCA function</span></span>

<span data-ttu-id="dde3f-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dde3f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dde3f-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dde3f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dde3f-105">Dada a função que devolve as operações, devolve uma nova operação que toma ambas as entradas como tuple.</span><span class="sxs-lookup"><span data-stu-id="dde3f-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="dde3f-106">O modificador `CA` indica que as operações são controláveis e adjacentes.</span><span class="sxs-lookup"><span data-stu-id="dde3f-106">The modifier `CA` indicates that the operations are controllable and adjointable.</span></span>

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="dde3f-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="dde3f-107">Input</span></span>

### <a name="curriedop--t---u--unit-ctl--adj"></a><span data-ttu-id="dde3f-108">curriedOp : 'T-> 'U = [unidade](xref:microsoft.quantum.lang-ref.unit)> Ctl + Adj</span><span class="sxs-lookup"><span data-stu-id="dde3f-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="dde3f-109">Uma função que devolve as operações.</span><span class="sxs-lookup"><span data-stu-id="dde3f-109">A function which returns operations.</span></span>



## <a name="output--tu--unit-ctl--adj"></a><span data-ttu-id="dde3f-110">Saída : ('T,'U) => [Unidade](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span><span class="sxs-lookup"><span data-stu-id="dde3f-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="dde3f-111">Uma nova operação `op` tal que `op(t, u)` equivale `(curriedOp(t))(u)` a.</span><span class="sxs-lookup"><span data-stu-id="dde3f-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="dde3f-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="dde3f-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dde3f-113">'T</span><span class="sxs-lookup"><span data-stu-id="dde3f-113">'T</span></span>

<span data-ttu-id="dde3f-114">O tipo do primeiro argumento de uma função curada.</span><span class="sxs-lookup"><span data-stu-id="dde3f-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="dde3f-115">'U</span><span class="sxs-lookup"><span data-stu-id="dde3f-115">'U</span></span>

<span data-ttu-id="dde3f-116">O tipo do segundo argumento de uma função curada.</span><span class="sxs-lookup"><span data-stu-id="dde3f-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="dde3f-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="dde3f-117">See Also</span></span>

- [<span data-ttu-id="dde3f-118">Microsoft.Quantum.Canon.UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="dde3f-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)