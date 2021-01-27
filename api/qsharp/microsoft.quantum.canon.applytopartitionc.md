---
uid: Microsoft.Quantum.Canon.ApplyToPartitionC
title: Aplicar a operação DoPartitionC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionC
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 43cf43fa2bf9c00a4096b39555b8f6080dd506d6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850532"
---
# <a name="applytopartitionc-operation"></a><span data-ttu-id="c1c6d-102">Aplicar a operação DoPartitionC</span><span class="sxs-lookup"><span data-stu-id="c1c6d-102">ApplyToPartitionC operation</span></span>

<span data-ttu-id="c1c6d-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c1c6d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c1c6d-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c1c6d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c1c6d-105">Aplica um par de operações a uma determinada divisão de um registo em duas partes.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>
<span data-ttu-id="c1c6d-106">O modificador `C` indica que a operação é controlável.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToPartitionC (op : ((Qubit[], Qubit[]) => Unit is Ctl), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="c1c6d-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="c1c6d-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-ctl"></a><span data-ttu-id="c1c6d-108">op :[(Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = [> Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span><span class="sxs-lookup"><span data-stu-id="c1c6d-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="c1c6d-109">O par de operações a aplicar à partição dada.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-109">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="c1c6d-110">númeroOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c1c6d-110">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c1c6d-111">Número de qubits do alvo para colocar na primeira parte da partição.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-111">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="c1c6d-112">Os qubits restantes constituem a segunda parte da partição.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-112">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="c1c6d-113">alvo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c1c6d-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c1c6d-114">Um registo de qubits que estão a ser divididos e operados pela operação dada.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-114">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c1c6d-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c1c6d-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="c1c6d-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c1c6d-116">See Also</span></span>

- [<span data-ttu-id="c1c6d-117">Microsoft.Quantum.Canon.ApplyToPartition</span><span class="sxs-lookup"><span data-stu-id="c1c6d-117">Microsoft.Quantum.Canon.ApplyToPartition</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartition)