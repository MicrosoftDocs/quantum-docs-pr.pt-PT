---
uid: Microsoft.Quantum.Canon.OperationPowC
title: Função OperationPowC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: f3c51410fb7c091385b64a1c4c99b3972d5055b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715690"
---
# <a name="operationpowc-function"></a><span data-ttu-id="bb0eb-102">Função OperationPowC</span><span class="sxs-lookup"><span data-stu-id="bb0eb-102">OperationPowC function</span></span>

<span data-ttu-id="bb0eb-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bb0eb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bb0eb-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bb0eb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bb0eb-105">Eleva uma operação a uma potência.</span><span class="sxs-lookup"><span data-stu-id="bb0eb-105">Raises an operation to a power.</span></span>
<span data-ttu-id="bb0eb-106">O modificador `C` indica que a operação é controlável.</span><span class="sxs-lookup"><span data-stu-id="bb0eb-106">The modifier `C` indicates that the operation is controllable.</span></span>

<span data-ttu-id="bb0eb-107">Ou seja, dada uma operação que representa um portão $U$, devolve uma nova operação $U^m$ por uma potência $m$.</span><span class="sxs-lookup"><span data-stu-id="bb0eb-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="bb0eb-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="bb0eb-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="bb0eb-109">op : 'T => [Unidade](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="bb0eb-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="bb0eb-110">Uma operação $U$ representando o portão a ser repetido.</span><span class="sxs-lookup"><span data-stu-id="bb0eb-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="bb0eb-111">poder : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bb0eb-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bb0eb-112">O número de vezes que $U$ deve ser repetido.</span><span class="sxs-lookup"><span data-stu-id="bb0eb-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit-ctl"></a><span data-ttu-id="bb0eb-113">Saída : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit)> Ctl</span><span class="sxs-lookup"><span data-stu-id="bb0eb-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="bb0eb-114">Uma nova operação que representa $U^m$, onde $m = \texttt{power}$.</span><span class="sxs-lookup"><span data-stu-id="bb0eb-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bb0eb-115">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="bb0eb-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bb0eb-116">'T</span><span class="sxs-lookup"><span data-stu-id="bb0eb-116">'T</span></span>

<span data-ttu-id="bb0eb-117">O tipo de operação a ser alimentada.</span><span class="sxs-lookup"><span data-stu-id="bb0eb-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb0eb-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="bb0eb-118">See Also</span></span>

- [<span data-ttu-id="bb0eb-119">Microsoft.Quantum.Canon.OperationPow</span><span class="sxs-lookup"><span data-stu-id="bb0eb-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)