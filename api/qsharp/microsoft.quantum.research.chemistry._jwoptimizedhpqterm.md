---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedHpqTerm
title: operação _JWOptimizedHpqTerm
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedHpqTerm
qsharp.summary: Applies time-evolution by a PQ term described by a `GeneratorIndex`.
ms.openlocfilehash: 06680bac0f0a2854c3ee3036c67c635ed0caf206
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225980"
---
# <a name="_jwoptimizedhpqterm-operation"></a><span data-ttu-id="b15a2-102">operação _JWOptimizedHpqTerm</span><span class="sxs-lookup"><span data-stu-id="b15a2-102">_JWOptimizedHpqTerm operation</span></span>

<span data-ttu-id="b15a2-103">Espaço de nome: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="b15a2-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="b15a2-104">Pacote: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="b15a2-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="b15a2-105">Aplica a evolução temporal por um termo PQ descrito por um `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="b15a2-105">Applies time-evolution by a PQ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedHpqTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b15a2-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b15a2-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="b15a2-107">termo : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="b15a2-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="b15a2-108">`GeneratorIndex` representando um termo PQ.</span><span class="sxs-lookup"><span data-stu-id="b15a2-108">`GeneratorIndex` representing a PQ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="b15a2-109">stepSize : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b15a2-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b15a2-110">Duração da evolução do tempo.</span><span class="sxs-lookup"><span data-stu-id="b15a2-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="b15a2-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b15a2-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b15a2-112">Qubit que determina o sinal da evolução do tempo.</span><span class="sxs-lookup"><span data-stu-id="b15a2-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="b15a2-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b15a2-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b15a2-114">Qubits de Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="b15a2-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b15a2-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b15a2-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

