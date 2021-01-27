---
uid: Microsoft.Quantum.Canon.Bound
title: Função vinculada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: 041f654c14f6e926d60038fee698b2b829fab8b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841059"
---
# <a name="bound-function"></a><span data-ttu-id="8b404-102">Função vinculada</span><span class="sxs-lookup"><span data-stu-id="8b404-102">Bound function</span></span>

<span data-ttu-id="8b404-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8b404-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8b404-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8b404-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8b404-105">Dado um conjunto de operações agindo numa única entrada, produz uma nova operação que executa cada operação em sequência.</span><span class="sxs-lookup"><span data-stu-id="8b404-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="8b404-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8b404-106">Input</span></span>

### <a name="operations--t--unit-"></a><span data-ttu-id="8b404-107">operações : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)> []</span><span class="sxs-lookup"><span data-stu-id="8b404-107">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="8b404-108">Uma sequência de operações a realizar numa dada entrada.</span><span class="sxs-lookup"><span data-stu-id="8b404-108">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="8b404-109">Saída : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="8b404-109">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="8b404-110">Uma nova operação que executa cada operação em sequência na sua entrada.</span><span class="sxs-lookup"><span data-stu-id="8b404-110">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8b404-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="8b404-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8b404-112">'T</span><span class="sxs-lookup"><span data-stu-id="8b404-112">'T</span></span>

<span data-ttu-id="8b404-113">O alvo em que cada uma das operações na matriz atuam.</span><span class="sxs-lookup"><span data-stu-id="8b404-113">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="8b404-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8b404-114">Example</span></span>

<span data-ttu-id="8b404-115">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="8b404-115">The following are equivalent:</span></span>

```qsharp
let bound = Bound([U, V]);
bound(x);
```

<span data-ttu-id="8b404-116">e</span><span class="sxs-lookup"><span data-stu-id="8b404-116">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="8b404-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8b404-117">See Also</span></span>

- [<span data-ttu-id="8b404-118">Microsoft.Quantum.Canon.BoundC</span><span class="sxs-lookup"><span data-stu-id="8b404-118">Microsoft.Quantum.Canon.BoundC</span></span>](xref:Microsoft.Quantum.Canon.BoundC)
- [<span data-ttu-id="8b404-119">Microsoft.Quantum.Canon.Bounda</span><span class="sxs-lookup"><span data-stu-id="8b404-119">Microsoft.Quantum.Canon.BoundA</span></span>](xref:Microsoft.Quantum.Canon.BoundA)
- [<span data-ttu-id="8b404-120">Microsoft.Quantum.Canon.BoundCA</span><span class="sxs-lookup"><span data-stu-id="8b404-120">Microsoft.Quantum.Canon.BoundCA</span></span>](xref:Microsoft.Quantum.Canon.BoundCA)