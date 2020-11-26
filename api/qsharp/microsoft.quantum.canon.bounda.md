---
uid: Microsoft.Quantum.Canon.BoundA
title: Função BoundA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 3132bf198e98dd1a2b433f36b000060e7e721865
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216953"
---
# <a name="bounda-function"></a><span data-ttu-id="7ecd8-102">Função BoundA</span><span class="sxs-lookup"><span data-stu-id="7ecd8-102">BoundA function</span></span>

<span data-ttu-id="7ecd8-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7ecd8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7ecd8-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7ecd8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7ecd8-105">Dado um conjunto de operações agindo numa única entrada, produz uma nova operação que executa cada operação em sequência.</span><span class="sxs-lookup"><span data-stu-id="7ecd8-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="7ecd8-106">O modificador `A` indica que todas as operações na matriz são adjacentes.</span><span class="sxs-lookup"><span data-stu-id="7ecd8-106">The modifier `A` indicates that all operations in the array are adjointable.</span></span>

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="7ecd8-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="7ecd8-107">Input</span></span>

### <a name="operations--t--unit--is-adj"></a><span data-ttu-id="7ecd8-108">operações : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj[]</span><span class="sxs-lookup"><span data-stu-id="7ecd8-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj[]</span></span>

<span data-ttu-id="7ecd8-109">Uma sequência de operações a realizar numa dada entrada.</span><span class="sxs-lookup"><span data-stu-id="7ecd8-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj"></a><span data-ttu-id="7ecd8-110">Saída : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="7ecd8-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="7ecd8-111">Uma nova operação que executa cada operação em sequência na sua entrada.</span><span class="sxs-lookup"><span data-stu-id="7ecd8-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7ecd8-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="7ecd8-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7ecd8-113">'T</span><span class="sxs-lookup"><span data-stu-id="7ecd8-113">'T</span></span>

<span data-ttu-id="7ecd8-114">O alvo em que cada uma das operações na matriz atuam.</span><span class="sxs-lookup"><span data-stu-id="7ecd8-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ecd8-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7ecd8-115">See Also</span></span>

- [<span data-ttu-id="7ecd8-116">Microsoft.Quantum.Canon.Bound</span><span class="sxs-lookup"><span data-stu-id="7ecd8-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)