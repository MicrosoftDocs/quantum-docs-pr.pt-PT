---
uid: Microsoft.Quantum.Canon.Bound
title: Função vinculada
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: 34ca2b79d0ee09bd3b5b5b3f0c0b20420d5b3882
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716701"
---
# <a name="bound-function"></a><span data-ttu-id="107f7-102">Função vinculada</span><span class="sxs-lookup"><span data-stu-id="107f7-102">Bound function</span></span>

<span data-ttu-id="107f7-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="107f7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="107f7-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="107f7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="107f7-105">Dado um conjunto de operações agindo numa única entrada, produz uma nova operação que executa cada operação em sequência.</span><span class="sxs-lookup"><span data-stu-id="107f7-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="107f7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="107f7-106">Input</span></span>

### <a name="operations--t--unit-"></a><span data-ttu-id="107f7-107">operações : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)> []</span><span class="sxs-lookup"><span data-stu-id="107f7-107">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="107f7-108">Uma sequência de operações a realizar numa dada entrada.</span><span class="sxs-lookup"><span data-stu-id="107f7-108">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="107f7-109">Saída : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="107f7-109">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="107f7-110">Uma nova operação que executa cada operação em sequência na sua entrada.</span><span class="sxs-lookup"><span data-stu-id="107f7-110">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="107f7-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="107f7-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="107f7-112">'T</span><span class="sxs-lookup"><span data-stu-id="107f7-112">'T</span></span>

<span data-ttu-id="107f7-113">O alvo em que cada uma das operações na matriz atuam.</span><span class="sxs-lookup"><span data-stu-id="107f7-113">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="107f7-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="107f7-114">See Also</span></span>

- [<span data-ttu-id="107f7-115">Microsoft.Quantum.Canon.BoundC</span><span class="sxs-lookup"><span data-stu-id="107f7-115">Microsoft.Quantum.Canon.BoundC</span></span>](xref:Microsoft.Quantum.Canon.BoundC)
- [<span data-ttu-id="107f7-116">Microsoft.Quantum.Canon.Bounda</span><span class="sxs-lookup"><span data-stu-id="107f7-116">Microsoft.Quantum.Canon.BoundA</span></span>](xref:Microsoft.Quantum.Canon.BoundA)
- [<span data-ttu-id="107f7-117">Microsoft.Quantum.Canon.BoundCA</span><span class="sxs-lookup"><span data-stu-id="107f7-117">Microsoft.Quantum.Canon.BoundCA</span></span>](xref:Microsoft.Quantum.Canon.BoundCA)