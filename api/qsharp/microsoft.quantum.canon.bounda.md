---
uid: Microsoft.Quantum.Canon.BoundA
title: Função BoundA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 40c112d0572dc4eebfc284c9ef29f43706e20c64
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716687"
---
# <a name="bounda-function"></a><span data-ttu-id="291b8-102">Função BoundA</span><span class="sxs-lookup"><span data-stu-id="291b8-102">BoundA function</span></span>

<span data-ttu-id="291b8-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="291b8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="291b8-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="291b8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="291b8-105">Dado um conjunto de operações agindo numa única entrada, produz uma nova operação que executa cada operação em sequência.</span><span class="sxs-lookup"><span data-stu-id="291b8-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="291b8-106">O modificador `A` indica que todas as operações na matriz são adjacentes.</span><span class="sxs-lookup"><span data-stu-id="291b8-106">The modifier `A` indicates that all operations in the array are adjointable.</span></span>

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="291b8-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="291b8-107">Input</span></span>

### <a name="operations--t--unit-adj"></a><span data-ttu-id="291b8-108">operações : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit)> Adj[]</span><span class="sxs-lookup"><span data-stu-id="291b8-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj[]</span></span>

<span data-ttu-id="291b8-109">Uma sequência de operações a realizar numa dada entrada.</span><span class="sxs-lookup"><span data-stu-id="291b8-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-adj"></a><span data-ttu-id="291b8-110">Saída : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit)> Adj</span><span class="sxs-lookup"><span data-stu-id="291b8-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="291b8-111">Uma nova operação que executa cada operação em sequência na sua entrada.</span><span class="sxs-lookup"><span data-stu-id="291b8-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="291b8-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="291b8-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="291b8-113">'T</span><span class="sxs-lookup"><span data-stu-id="291b8-113">'T</span></span>

<span data-ttu-id="291b8-114">O alvo em que cada uma das operações na matriz atuam.</span><span class="sxs-lookup"><span data-stu-id="291b8-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="291b8-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="291b8-115">See Also</span></span>

- [<span data-ttu-id="291b8-116">Microsoft.Quantum.Canon.Bound</span><span class="sxs-lookup"><span data-stu-id="291b8-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)