---
uid: Microsoft.Quantum.Canon.BoundC
title: Função BoundC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 04dca4ff317bf3cee053f7c3903112f4e05a3973
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716670"
---
# <a name="boundc-function"></a><span data-ttu-id="caa0c-102">Função BoundC</span><span class="sxs-lookup"><span data-stu-id="caa0c-102">BoundC function</span></span>

<span data-ttu-id="caa0c-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="caa0c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="caa0c-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="caa0c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="caa0c-105">Dado um conjunto de operações agindo numa única entrada, produz uma nova operação que executa cada operação em sequência.</span><span class="sxs-lookup"><span data-stu-id="caa0c-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="caa0c-106">O modificador `C` indica que todas as operações na matriz são controláveis.</span><span class="sxs-lookup"><span data-stu-id="caa0c-106">The modifier `C` indicates that all operations in the array are controllable.</span></span>

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="caa0c-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="caa0c-107">Input</span></span>

### <a name="operations--t--unit-ctl"></a><span data-ttu-id="caa0c-108">operações : 'T => [Unidade](xref:microsoft.quantum.lang-ref.unit) CTL][]</span><span class="sxs-lookup"><span data-stu-id="caa0c-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl[]</span></span>

<span data-ttu-id="caa0c-109">Uma sequência de operações a realizar numa dada entrada.</span><span class="sxs-lookup"><span data-stu-id="caa0c-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-ctl"></a><span data-ttu-id="caa0c-110">Saída : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit)> Ctl</span><span class="sxs-lookup"><span data-stu-id="caa0c-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="caa0c-111">Uma nova operação que executa cada operação em sequência na sua entrada.</span><span class="sxs-lookup"><span data-stu-id="caa0c-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="caa0c-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="caa0c-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="caa0c-113">'T</span><span class="sxs-lookup"><span data-stu-id="caa0c-113">'T</span></span>

<span data-ttu-id="caa0c-114">O alvo em que cada uma das operações na matriz atuam.</span><span class="sxs-lookup"><span data-stu-id="caa0c-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="caa0c-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="caa0c-115">See Also</span></span>

- [<span data-ttu-id="caa0c-116">Microsoft.Quantum.Canon.Bound</span><span class="sxs-lookup"><span data-stu-id="caa0c-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)