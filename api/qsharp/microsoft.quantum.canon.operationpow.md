---
uid: Microsoft.Quantum.Canon.OperationPow
title: Função OperationPow
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 5cf9017175f44a8a0b8f865624a6c312d25aded1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715774"
---
# <a name="operationpow-function"></a><span data-ttu-id="63c00-102">Função OperationPow</span><span class="sxs-lookup"><span data-stu-id="63c00-102">OperationPow function</span></span>

<span data-ttu-id="63c00-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="63c00-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="63c00-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="63c00-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="63c00-105">Eleva uma operação a uma potência.</span><span class="sxs-lookup"><span data-stu-id="63c00-105">Raises an operation to a power.</span></span>

<span data-ttu-id="63c00-106">Ou seja, dada uma operação que representa um portão $U$, devolve uma nova operação $U^m$ por uma potência $m$.</span><span class="sxs-lookup"><span data-stu-id="63c00-106">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="63c00-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="63c00-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="63c00-108">op : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="63c00-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="63c00-109">Uma operação $U$ representando o portão a ser repetido.</span><span class="sxs-lookup"><span data-stu-id="63c00-109">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="63c00-110">poder : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="63c00-110">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="63c00-111">O número de vezes que $U$ deve ser repetido.</span><span class="sxs-lookup"><span data-stu-id="63c00-111">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="63c00-112">Saída : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="63c00-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="63c00-113">Uma nova operação que representa $U^m$, onde $m = \texttt{power}$.</span><span class="sxs-lookup"><span data-stu-id="63c00-113">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="63c00-114">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="63c00-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="63c00-115">'T</span><span class="sxs-lookup"><span data-stu-id="63c00-115">'T</span></span>

<span data-ttu-id="63c00-116">O tipo de operação a ser alimentada.</span><span class="sxs-lookup"><span data-stu-id="63c00-116">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="63c00-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="63c00-117">See Also</span></span>

- [<span data-ttu-id="63c00-118">Microsoft.Quantum.Canon.OperationPowC</span><span class="sxs-lookup"><span data-stu-id="63c00-118">Microsoft.Quantum.Canon.OperationPowC</span></span>](xref:Microsoft.Quantum.Canon.OperationPowC)
- [<span data-ttu-id="63c00-119">Microsoft.Quantum.Canon.OperationPowa</span><span class="sxs-lookup"><span data-stu-id="63c00-119">Microsoft.Quantum.Canon.OperationPowA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowA)
- [<span data-ttu-id="63c00-120">Microsoft.Quantum.Canon.OperationPowCA</span><span class="sxs-lookup"><span data-stu-id="63c00-120">Microsoft.Quantum.Canon.OperationPowCA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowCA)