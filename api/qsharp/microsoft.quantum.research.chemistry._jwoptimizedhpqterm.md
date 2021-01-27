---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedHpqTerm
title: operação _JWOptimizedHpqTerm
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedHpqTerm
qsharp.summary: Applies time-evolution by a PQ term described by a `GeneratorIndex`.
ms.openlocfilehash: b008315ded7cabc085e6d5da8f646e92914bf743
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854802"
---
# <a name="_jwoptimizedhpqterm-operation"></a><span data-ttu-id="f468d-102">operação _JWOptimizedHpqTerm</span><span class="sxs-lookup"><span data-stu-id="f468d-102">_JWOptimizedHpqTerm operation</span></span>

<span data-ttu-id="f468d-103">Espaço de nome: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f468d-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="f468d-104">Pacote: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f468d-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="f468d-105">Aplica a evolução temporal por um termo PQ descrito por um `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="f468d-105">Applies time-evolution by a PQ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedHpqTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f468d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f468d-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="f468d-107">termo : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="f468d-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="f468d-108">`GeneratorIndex` representando um termo PQ.</span><span class="sxs-lookup"><span data-stu-id="f468d-108">`GeneratorIndex` representing a PQ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="f468d-109">stepSize : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f468d-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f468d-110">Duração da evolução do tempo.</span><span class="sxs-lookup"><span data-stu-id="f468d-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="f468d-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f468d-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f468d-112">Qubit que determina o sinal da evolução do tempo.</span><span class="sxs-lookup"><span data-stu-id="f468d-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="f468d-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f468d-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f468d-114">Qubits de Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="f468d-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f468d-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f468d-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

