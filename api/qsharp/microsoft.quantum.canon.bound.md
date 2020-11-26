---
uid: Microsoft.Quantum.Canon.Bound
title: Função vinculada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: c12ce37054ddde1b98778888e90916c6e4725814
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207603"
---
# <a name="bound-function"></a><span data-ttu-id="20d68-102">Função vinculada</span><span class="sxs-lookup"><span data-stu-id="20d68-102">Bound function</span></span>

<span data-ttu-id="20d68-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="20d68-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="20d68-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="20d68-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="20d68-105">Dado um conjunto de operações agindo numa única entrada, produz uma nova operação que executa cada operação em sequência.</span><span class="sxs-lookup"><span data-stu-id="20d68-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="20d68-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="20d68-106">Input</span></span>

### <a name="operations--t--unit-"></a><span data-ttu-id="20d68-107">operações : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)> []</span><span class="sxs-lookup"><span data-stu-id="20d68-107">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="20d68-108">Uma sequência de operações a realizar numa dada entrada.</span><span class="sxs-lookup"><span data-stu-id="20d68-108">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="20d68-109">Saída : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="20d68-109">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="20d68-110">Uma nova operação que executa cada operação em sequência na sua entrada.</span><span class="sxs-lookup"><span data-stu-id="20d68-110">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="20d68-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="20d68-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="20d68-112">'T</span><span class="sxs-lookup"><span data-stu-id="20d68-112">'T</span></span>

<span data-ttu-id="20d68-113">O alvo em que cada uma das operações na matriz atuam.</span><span class="sxs-lookup"><span data-stu-id="20d68-113">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="20d68-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="20d68-114">See Also</span></span>

- [<span data-ttu-id="20d68-115">Microsoft.Quantum.Canon.BoundC</span><span class="sxs-lookup"><span data-stu-id="20d68-115">Microsoft.Quantum.Canon.BoundC</span></span>](xref:Microsoft.Quantum.Canon.BoundC)
- [<span data-ttu-id="20d68-116">Microsoft.Quantum.Canon.Bounda</span><span class="sxs-lookup"><span data-stu-id="20d68-116">Microsoft.Quantum.Canon.BoundA</span></span>](xref:Microsoft.Quantum.Canon.BoundA)
- [<span data-ttu-id="20d68-117">Microsoft.Quantum.Canon.BoundCA</span><span class="sxs-lookup"><span data-stu-id="20d68-117">Microsoft.Quantum.Canon.BoundCA</span></span>](xref:Microsoft.Quantum.Canon.BoundCA)