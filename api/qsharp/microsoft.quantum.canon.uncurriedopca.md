---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: Função Não curadaopCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 45526c0202e417213aab3fe7819827588e794e23
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216392"
---
# <a name="uncurriedopca-function"></a><span data-ttu-id="8470c-102">Função Não curadaopCA</span><span class="sxs-lookup"><span data-stu-id="8470c-102">UncurriedOpCA function</span></span>

<span data-ttu-id="8470c-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8470c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8470c-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8470c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8470c-105">Dada a função que devolve as operações, devolve uma nova operação que toma ambas as entradas como tuple.</span><span class="sxs-lookup"><span data-stu-id="8470c-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="8470c-106">O modificador `CA` indica que as operações são controláveis e adjacentes.</span><span class="sxs-lookup"><span data-stu-id="8470c-106">The modifier `CA` indicates that the operations are controllable and adjointable.</span></span>

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="8470c-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="8470c-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj--ctl"></a><span data-ttu-id="8470c-108">curriedOp : 'T-> 'U = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="8470c-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="8470c-109">Uma função que devolve as operações.</span><span class="sxs-lookup"><span data-stu-id="8470c-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-adj--ctl"></a><span data-ttu-id="8470c-110">Saída : ('T,'U) = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="8470c-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="8470c-111">Uma nova operação `op` tal que `op(t, u)` equivale `(curriedOp(t))(u)` a.</span><span class="sxs-lookup"><span data-stu-id="8470c-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8470c-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="8470c-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8470c-113">'T</span><span class="sxs-lookup"><span data-stu-id="8470c-113">'T</span></span>

<span data-ttu-id="8470c-114">O tipo do primeiro argumento de uma função curada.</span><span class="sxs-lookup"><span data-stu-id="8470c-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="8470c-115">'U</span><span class="sxs-lookup"><span data-stu-id="8470c-115">'U</span></span>

<span data-ttu-id="8470c-116">O tipo do segundo argumento de uma função curada.</span><span class="sxs-lookup"><span data-stu-id="8470c-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="8470c-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8470c-117">See Also</span></span>

- [<span data-ttu-id="8470c-118">Microsoft.Quantum.Canon.UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="8470c-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)