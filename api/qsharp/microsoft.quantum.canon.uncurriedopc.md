---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: Função DeOpC nãocurried
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: 05df99dce8b167f32078ce256748647ceb94d0fe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851996"
---
# <a name="uncurriedopc-function"></a><span data-ttu-id="8687a-102">Função DeOpC nãocurried</span><span class="sxs-lookup"><span data-stu-id="8687a-102">UncurriedOpC function</span></span>

<span data-ttu-id="8687a-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8687a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8687a-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8687a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8687a-105">Dada a função que devolve as operações, devolve uma nova operação que toma ambas as entradas como tuple.</span><span class="sxs-lookup"><span data-stu-id="8687a-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="8687a-106">O modificador `C` indica que as operações são controláveis.</span><span class="sxs-lookup"><span data-stu-id="8687a-106">The modifier `C` indicates that the operations are controllable.</span></span>

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="8687a-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="8687a-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-ctl"></a><span data-ttu-id="8687a-108">curriedOp : 'T-> 'U = [unidade](xref:microsoft.quantum.lang-ref.unit) > é CTL</span><span class="sxs-lookup"><span data-stu-id="8687a-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="8687a-109">Uma função que devolve as operações.</span><span class="sxs-lookup"><span data-stu-id="8687a-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-ctl"></a><span data-ttu-id="8687a-110">Saída : ('T,'U) = [unidade](xref:microsoft.quantum.lang-ref.unit) > é CTL</span><span class="sxs-lookup"><span data-stu-id="8687a-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="8687a-111">Uma nova operação `op` tal que `op(t, u)` equivale `(curriedOp(t))(u)` a.</span><span class="sxs-lookup"><span data-stu-id="8687a-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8687a-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="8687a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8687a-113">'T</span><span class="sxs-lookup"><span data-stu-id="8687a-113">'T</span></span>

<span data-ttu-id="8687a-114">O tipo do primeiro argumento de uma função curada.</span><span class="sxs-lookup"><span data-stu-id="8687a-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="8687a-115">'U</span><span class="sxs-lookup"><span data-stu-id="8687a-115">'U</span></span>

<span data-ttu-id="8687a-116">O tipo do segundo argumento de uma função curada.</span><span class="sxs-lookup"><span data-stu-id="8687a-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="8687a-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8687a-117">See Also</span></span>

- [<span data-ttu-id="8687a-118">Microsoft.Quantum.Canon.UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="8687a-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)