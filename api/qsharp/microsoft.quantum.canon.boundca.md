---
uid: Microsoft.Quantum.Canon.BoundCA
title: Função BoundCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: d96d33781def10940479ba2eafdcc6711a0c05a5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716631"
---
# <a name="boundca-function"></a><span data-ttu-id="93dd8-102">Função BoundCA</span><span class="sxs-lookup"><span data-stu-id="93dd8-102">BoundCA function</span></span>

<span data-ttu-id="93dd8-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="93dd8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="93dd8-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="93dd8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="93dd8-105">Dado um conjunto de operações agindo numa única entrada, produz uma nova operação que executa cada operação em sequência.</span><span class="sxs-lookup"><span data-stu-id="93dd8-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="93dd8-106">O modificador `CA` indica que todas as operações na matriz são adjacentes e controláveis.</span><span class="sxs-lookup"><span data-stu-id="93dd8-106">The modifier `CA` indicates that all operations in the array are adjointable and controllable.</span></span>

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="93dd8-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="93dd8-107">Input</span></span>

### <a name="operations--t--unit-adj--ctl"></a><span data-ttu-id="93dd8-108">operações : 'T = [Unit](xref:microsoft.quantum.lang-ref.unit) unidade> Adj + CTL[]</span><span class="sxs-lookup"><span data-stu-id="93dd8-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl[]</span></span>

<span data-ttu-id="93dd8-109">Uma sequência de operações a realizar numa dada entrada.</span><span class="sxs-lookup"><span data-stu-id="93dd8-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-adj--ctl"></a><span data-ttu-id="93dd8-110">Saída : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)> Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="93dd8-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="93dd8-111">Uma nova operação que executa cada operação em sequência na sua entrada.</span><span class="sxs-lookup"><span data-stu-id="93dd8-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="93dd8-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="93dd8-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="93dd8-113">'T</span><span class="sxs-lookup"><span data-stu-id="93dd8-113">'T</span></span>

<span data-ttu-id="93dd8-114">O alvo em que cada uma das operações na matriz atuam.</span><span class="sxs-lookup"><span data-stu-id="93dd8-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="93dd8-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="93dd8-115">See Also</span></span>

- [<span data-ttu-id="93dd8-116">Microsoft.Quantum.Canon.Bound</span><span class="sxs-lookup"><span data-stu-id="93dd8-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)