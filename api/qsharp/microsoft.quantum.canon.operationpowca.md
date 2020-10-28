---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: Função OperationPowCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 753063452616747309e3e228ce8a702f4378c61f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715676"
---
# <a name="operationpowca-function"></a><span data-ttu-id="64d14-102">Função OperationPowCA</span><span class="sxs-lookup"><span data-stu-id="64d14-102">OperationPowCA function</span></span>

<span data-ttu-id="64d14-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="64d14-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="64d14-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="64d14-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="64d14-105">Eleva uma operação a uma potência.</span><span class="sxs-lookup"><span data-stu-id="64d14-105">Raises an operation to a power.</span></span>
<span data-ttu-id="64d14-106">O modificador `A` indica que a operação é controlável e adjacente.</span><span class="sxs-lookup"><span data-stu-id="64d14-106">The modifier `A` indicates that the operation is controllable and adjointable.</span></span>

<span data-ttu-id="64d14-107">Ou seja, dada uma operação que representa um portão $U$, devolve uma nova operação $U^m$ por uma potência $m$.</span><span class="sxs-lookup"><span data-stu-id="64d14-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="64d14-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="64d14-108">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="64d14-109">op : 'T = unidade> [Ctl](xref:microsoft.quantum.lang-ref.unit) + Adj</span><span class="sxs-lookup"><span data-stu-id="64d14-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="64d14-110">Uma operação $U$ representando o portão a ser repetido.</span><span class="sxs-lookup"><span data-stu-id="64d14-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="64d14-111">poder : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="64d14-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="64d14-112">O número de vezes que $U$ deve ser repetido.</span><span class="sxs-lookup"><span data-stu-id="64d14-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit-ctl--adj"></a><span data-ttu-id="64d14-113">Saída : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit)> Ctl + Adj</span><span class="sxs-lookup"><span data-stu-id="64d14-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="64d14-114">Uma nova operação que representa $U^m$, onde $m = \texttt{power}$.</span><span class="sxs-lookup"><span data-stu-id="64d14-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="64d14-115">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="64d14-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="64d14-116">'T</span><span class="sxs-lookup"><span data-stu-id="64d14-116">'T</span></span>

<span data-ttu-id="64d14-117">O tipo de operação a ser alimentada.</span><span class="sxs-lookup"><span data-stu-id="64d14-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="64d14-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="64d14-118">See Also</span></span>

- [<span data-ttu-id="64d14-119">Microsoft.Quantum.Canon.OperationPow</span><span class="sxs-lookup"><span data-stu-id="64d14-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)