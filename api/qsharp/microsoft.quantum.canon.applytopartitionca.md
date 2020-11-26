---
uid: Microsoft.Quantum.Canon.ApplyToPartitionCA
title: Aplicação OperaçãoPartitionCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionCA
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: b33670a91af5cbf280fdda0e57ddbbf8c9013e91
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208313"
---
# <a name="applytopartitionca-operation"></a><span data-ttu-id="74ba7-102">Aplicação OperaçãoPartitionCA</span><span class="sxs-lookup"><span data-stu-id="74ba7-102">ApplyToPartitionCA operation</span></span>

<span data-ttu-id="74ba7-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="74ba7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="74ba7-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="74ba7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="74ba7-105">Aplica um par de operações a uma determinada divisão de um registo em duas partes.</span><span class="sxs-lookup"><span data-stu-id="74ba7-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>
<span data-ttu-id="74ba7-106">O modificador `CA` indica que a operação é controlável e adjacente.</span><span class="sxs-lookup"><span data-stu-id="74ba7-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToPartitionCA (op : ((Qubit[], Qubit[]) => Unit is Ctl + Adj), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="74ba7-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="74ba7-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="74ba7-108">op :[(Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = [> Unit](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="74ba7-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="74ba7-109">O par de operações a aplicar à partição dada.</span><span class="sxs-lookup"><span data-stu-id="74ba7-109">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="74ba7-110">númeroOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="74ba7-110">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="74ba7-111">Número de qubits do alvo para colocar na primeira parte da partição.</span><span class="sxs-lookup"><span data-stu-id="74ba7-111">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="74ba7-112">Os qubits restantes constituem a segunda parte da partição.</span><span class="sxs-lookup"><span data-stu-id="74ba7-112">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="74ba7-113">alvo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="74ba7-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="74ba7-114">Um registo de qubits que estão a ser divididos e operados pela operação dada.</span><span class="sxs-lookup"><span data-stu-id="74ba7-114">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="74ba7-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="74ba7-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="74ba7-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="74ba7-116">See Also</span></span>

- [<span data-ttu-id="74ba7-117">Microsoft.Quantum.Canon.ApplyToPartition</span><span class="sxs-lookup"><span data-stu-id="74ba7-117">Microsoft.Quantum.Canon.ApplyToPartition</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartition)