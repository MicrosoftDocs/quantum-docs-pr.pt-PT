---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: Função DeOpC nãocurried
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: f3e5ecf3f7df0393dfbb948f064c27505f04cfcf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715214"
---
# <a name="uncurriedopc-function"></a><span data-ttu-id="b1a95-102">Função DeOpC nãocurried</span><span class="sxs-lookup"><span data-stu-id="b1a95-102">UncurriedOpC function</span></span>

<span data-ttu-id="b1a95-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b1a95-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b1a95-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b1a95-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b1a95-105">Dada a função que devolve as operações, devolve uma nova operação que toma ambas as entradas como tuple.</span><span class="sxs-lookup"><span data-stu-id="b1a95-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="b1a95-106">O modificador `C` indica que as operações são controláveis.</span><span class="sxs-lookup"><span data-stu-id="b1a95-106">The modifier `C` indicates that the operations are controllable.</span></span>

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="b1a95-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="b1a95-107">Input</span></span>

### <a name="curriedop--t---u--unit-ctl"></a><span data-ttu-id="b1a95-108">curriedOp : 'T-> 'U = [unidade](xref:microsoft.quantum.lang-ref.unit)> Ctl</span><span class="sxs-lookup"><span data-stu-id="b1a95-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="b1a95-109">Uma função que devolve as operações.</span><span class="sxs-lookup"><span data-stu-id="b1a95-109">A function which returns operations.</span></span>



## <a name="output--tu--unit-ctl"></a><span data-ttu-id="b1a95-110">Saída : ('T,'U) => [Unidade](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="b1a95-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="b1a95-111">Uma nova operação `op` tal que `op(t, u)` equivale `(curriedOp(t))(u)` a.</span><span class="sxs-lookup"><span data-stu-id="b1a95-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b1a95-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="b1a95-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b1a95-113">'T</span><span class="sxs-lookup"><span data-stu-id="b1a95-113">'T</span></span>

<span data-ttu-id="b1a95-114">O tipo do primeiro argumento de uma função curada.</span><span class="sxs-lookup"><span data-stu-id="b1a95-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="b1a95-115">'U</span><span class="sxs-lookup"><span data-stu-id="b1a95-115">'U</span></span>

<span data-ttu-id="b1a95-116">O tipo do segundo argumento de uma função curada.</span><span class="sxs-lookup"><span data-stu-id="b1a95-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="b1a95-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b1a95-117">See Also</span></span>

- [<span data-ttu-id="b1a95-118">Microsoft.Quantum.Canon.UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="b1a95-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)