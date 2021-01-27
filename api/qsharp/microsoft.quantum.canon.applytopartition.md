---
uid: Microsoft.Quantum.Canon.ApplyToPartition
title: AplicarOperaçãoPartition
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartition
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts.
ms.openlocfilehash: a0dc3453e7501816132569869e858418d5f3f4e5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850545"
---
# <a name="applytopartition-operation"></a><span data-ttu-id="ebff7-102">AplicarOperaçãoPartition</span><span class="sxs-lookup"><span data-stu-id="ebff7-102">ApplyToPartition operation</span></span>

<span data-ttu-id="ebff7-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ebff7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ebff7-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ebff7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ebff7-105">Aplica um par de operações a uma determinada divisão de um registo em duas partes.</span><span class="sxs-lookup"><span data-stu-id="ebff7-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>

```qsharp
operation ApplyToPartition (op : ((Qubit[], Qubit[]) => Unit), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="ebff7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ebff7-106">Input</span></span>

### <a name="op--qubitqubit--unit"></a><span data-ttu-id="ebff7-107">op :[(Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = [unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="ebff7-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ebff7-108">O par de operações a aplicar à partição dada.</span><span class="sxs-lookup"><span data-stu-id="ebff7-108">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="ebff7-109">númeroOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ebff7-109">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ebff7-110">Número de qubits do alvo para colocar na primeira parte da partição.</span><span class="sxs-lookup"><span data-stu-id="ebff7-110">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="ebff7-111">Os qubits restantes constituem a segunda parte da partição.</span><span class="sxs-lookup"><span data-stu-id="ebff7-111">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="ebff7-112">alvo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ebff7-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ebff7-113">Um registo de qubits que estão a ser divididos e operados pela operação dada.</span><span class="sxs-lookup"><span data-stu-id="ebff7-113">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ebff7-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ebff7-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="ebff7-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ebff7-115">See Also</span></span>

- [<span data-ttu-id="ebff7-116">Microsoft.Quantum.Canon.ApplyToPartitionA</span><span class="sxs-lookup"><span data-stu-id="ebff7-116">Microsoft.Quantum.Canon.ApplyToPartitionA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionA)
- [<span data-ttu-id="ebff7-117">Microsoft.Quantum.Canon.ApplyToPartitionC</span><span class="sxs-lookup"><span data-stu-id="ebff7-117">Microsoft.Quantum.Canon.ApplyToPartitionC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionC)
- [<span data-ttu-id="ebff7-118">Microsoft.Quantum.Canon.ApplyToPartitionCA</span><span class="sxs-lookup"><span data-stu-id="ebff7-118">Microsoft.Quantum.Canon.ApplyToPartitionCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionCA)