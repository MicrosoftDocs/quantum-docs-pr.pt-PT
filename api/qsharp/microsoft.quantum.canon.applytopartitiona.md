---
uid: Microsoft.Quantum.Canon.ApplyToPartitionA
title: Aplicar a operaçãoPartitionA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionA
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 79f8fbed1592670031b3348155cdd4000eadc1fb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208351"
---
# <a name="applytopartitiona-operation"></a><span data-ttu-id="513c5-102">Aplicar a operaçãoPartitionA</span><span class="sxs-lookup"><span data-stu-id="513c5-102">ApplyToPartitionA operation</span></span>

<span data-ttu-id="513c5-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="513c5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="513c5-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="513c5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="513c5-105">Aplica um par de operações a uma determinada divisão de um registo em duas partes.</span><span class="sxs-lookup"><span data-stu-id="513c5-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>
<span data-ttu-id="513c5-106">O modificador `A` indica que a operação é adjacente.</span><span class="sxs-lookup"><span data-stu-id="513c5-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToPartitionA (op : ((Qubit[], Qubit[]) => Unit is Adj), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="513c5-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="513c5-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-adj"></a><span data-ttu-id="513c5-108">op :[(Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = [> Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span><span class="sxs-lookup"><span data-stu-id="513c5-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="513c5-109">O par de operações a aplicar à partição dada.</span><span class="sxs-lookup"><span data-stu-id="513c5-109">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="513c5-110">númeroOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="513c5-110">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="513c5-111">Número de qubits do alvo para colocar na primeira parte da partição.</span><span class="sxs-lookup"><span data-stu-id="513c5-111">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="513c5-112">Os qubits restantes constituem a segunda parte da partição.</span><span class="sxs-lookup"><span data-stu-id="513c5-112">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="513c5-113">alvo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="513c5-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="513c5-114">Um registo de qubits que estão a ser divididos e operados pela operação dada.</span><span class="sxs-lookup"><span data-stu-id="513c5-114">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="513c5-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="513c5-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="513c5-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="513c5-116">See Also</span></span>

- [<span data-ttu-id="513c5-117">Microsoft.Quantum.Canon.ApplyToPartition</span><span class="sxs-lookup"><span data-stu-id="513c5-117">Microsoft.Quantum.Canon.ApplyToPartition</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartition)