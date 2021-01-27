---
uid: Microsoft.Quantum.Canon.BoundA
title: Função BoundA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 3d0a5ba5d3d9c76289ed29e59a9c226358b83797
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844550"
---
# <a name="bounda-function"></a><span data-ttu-id="c5559-102">Função BoundA</span><span class="sxs-lookup"><span data-stu-id="c5559-102">BoundA function</span></span>

<span data-ttu-id="c5559-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c5559-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c5559-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c5559-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c5559-105">Dado um conjunto de operações agindo numa única entrada, produz uma nova operação que executa cada operação em sequência.</span><span class="sxs-lookup"><span data-stu-id="c5559-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="c5559-106">O modificador `A` indica que todas as operações na matriz são adjacentes.</span><span class="sxs-lookup"><span data-stu-id="c5559-106">The modifier `A` indicates that all operations in the array are adjointable.</span></span>

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="c5559-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="c5559-107">Input</span></span>

### <a name="operations--t--unit--is-adj"></a><span data-ttu-id="c5559-108">operações : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj[]</span><span class="sxs-lookup"><span data-stu-id="c5559-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj[]</span></span>

<span data-ttu-id="c5559-109">Uma sequência de operações a realizar numa dada entrada.</span><span class="sxs-lookup"><span data-stu-id="c5559-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj"></a><span data-ttu-id="c5559-110">Saída : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="c5559-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="c5559-111">Uma nova operação que executa cada operação em sequência na sua entrada.</span><span class="sxs-lookup"><span data-stu-id="c5559-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c5559-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="c5559-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c5559-113">'T</span><span class="sxs-lookup"><span data-stu-id="c5559-113">'T</span></span>

<span data-ttu-id="c5559-114">O alvo em que cada uma das operações na matriz atuam.</span><span class="sxs-lookup"><span data-stu-id="c5559-114">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="c5559-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c5559-115">Example</span></span>

<span data-ttu-id="c5559-116">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="c5559-116">The following are equivalent:</span></span>

```qsharp
let bound = BoundA([U, V]);
bound(x);
```

<span data-ttu-id="c5559-117">e</span><span class="sxs-lookup"><span data-stu-id="c5559-117">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="c5559-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c5559-118">See Also</span></span>

- [<span data-ttu-id="c5559-119">Microsoft.Quantum.Canon.Bound</span><span class="sxs-lookup"><span data-stu-id="c5559-119">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)