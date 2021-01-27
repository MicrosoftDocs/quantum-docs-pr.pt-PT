---
uid: Microsoft.Quantum.Canon.BoundC
title: Função BoundC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 6b640c0dab14778336f42098e699e7e68cc726df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841034"
---
# <a name="boundc-function"></a><span data-ttu-id="89c28-102">Função BoundC</span><span class="sxs-lookup"><span data-stu-id="89c28-102">BoundC function</span></span>

<span data-ttu-id="89c28-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="89c28-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="89c28-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="89c28-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="89c28-105">Dado um conjunto de operações agindo numa única entrada, produz uma nova operação que executa cada operação em sequência.</span><span class="sxs-lookup"><span data-stu-id="89c28-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="89c28-106">O modificador `C` indica que todas as operações na matriz são controláveis.</span><span class="sxs-lookup"><span data-stu-id="89c28-106">The modifier `C` indicates that all operations in the array are controllable.</span></span>

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="89c28-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="89c28-107">Input</span></span>

### <a name="operations--t--unit--is-ctl"></a><span data-ttu-id="89c28-108">operações : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é CTL[]</span><span class="sxs-lookup"><span data-stu-id="89c28-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="89c28-109">Uma sequência de operações a realizar numa dada entrada.</span><span class="sxs-lookup"><span data-stu-id="89c28-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="89c28-110">Saída : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é CTL</span><span class="sxs-lookup"><span data-stu-id="89c28-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="89c28-111">Uma nova operação que executa cada operação em sequência na sua entrada.</span><span class="sxs-lookup"><span data-stu-id="89c28-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="89c28-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="89c28-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="89c28-113">'T</span><span class="sxs-lookup"><span data-stu-id="89c28-113">'T</span></span>

<span data-ttu-id="89c28-114">O alvo em que cada uma das operações na matriz atuam.</span><span class="sxs-lookup"><span data-stu-id="89c28-114">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="89c28-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="89c28-115">Example</span></span>

<span data-ttu-id="89c28-116">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="89c28-116">The following are equivalent:</span></span>

```qsharp
let bound = BoundC([U, V]);
bound(x);
```

<span data-ttu-id="89c28-117">e</span><span class="sxs-lookup"><span data-stu-id="89c28-117">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="89c28-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="89c28-118">See Also</span></span>

- [<span data-ttu-id="89c28-119">Microsoft.Quantum.Canon.Bound</span><span class="sxs-lookup"><span data-stu-id="89c28-119">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)