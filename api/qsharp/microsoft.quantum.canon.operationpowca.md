---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: Função OperationPowCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 32de77cbd54cc8eeb8c4a967fd046dca709cd9ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205648"
---
# <a name="operationpowca-function"></a><span data-ttu-id="dee30-102">Função OperationPowCA</span><span class="sxs-lookup"><span data-stu-id="dee30-102">OperationPowCA function</span></span>

<span data-ttu-id="dee30-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dee30-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dee30-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dee30-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dee30-105">Eleva uma operação a uma potência.</span><span class="sxs-lookup"><span data-stu-id="dee30-105">Raises an operation to a power.</span></span>
<span data-ttu-id="dee30-106">O modificador `A` indica que a operação é controlável e adjacente.</span><span class="sxs-lookup"><span data-stu-id="dee30-106">The modifier `A` indicates that the operation is controllable and adjointable.</span></span>

<span data-ttu-id="dee30-107">Ou seja, dada uma operação que representa um portão $U$, devolve uma nova operação $U^m$ por uma potência $m$.</span><span class="sxs-lookup"><span data-stu-id="dee30-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="dee30-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="dee30-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="dee30-109">op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="dee30-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="dee30-110">Uma operação $U$ representando o portão a ser repetido.</span><span class="sxs-lookup"><span data-stu-id="dee30-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="dee30-111">poder : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dee30-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dee30-112">O número de vezes que $U$ deve ser repetido.</span><span class="sxs-lookup"><span data-stu-id="dee30-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit--is-adj--ctl"></a><span data-ttu-id="dee30-113">Saída : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="dee30-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="dee30-114">Uma nova operação que representa $U^m$, onde $m = \texttt{power}$.</span><span class="sxs-lookup"><span data-stu-id="dee30-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="dee30-115">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="dee30-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dee30-116">'T</span><span class="sxs-lookup"><span data-stu-id="dee30-116">'T</span></span>

<span data-ttu-id="dee30-117">O tipo de operação a ser alimentada.</span><span class="sxs-lookup"><span data-stu-id="dee30-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="dee30-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="dee30-118">See Also</span></span>

- [<span data-ttu-id="dee30-119">Microsoft.Quantum.Canon.OperationPow</span><span class="sxs-lookup"><span data-stu-id="dee30-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)