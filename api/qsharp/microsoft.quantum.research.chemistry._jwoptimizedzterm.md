---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZTerm
title: operação _JWOptimizedZTerm
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZTerm
qsharp.summary: Applies time-evolution by a Z term described by a `GeneratorIndex`.
ms.openlocfilehash: 0b54bd7916ff8294501716365c11211b4654f5ad
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722792"
---
# <a name="_jwoptimizedzterm-operation"></a><span data-ttu-id="c150a-102">operação _JWOptimizedZTerm</span><span class="sxs-lookup"><span data-stu-id="c150a-102">_JWOptimizedZTerm operation</span></span>

<span data-ttu-id="c150a-103">Espaço de nome: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="c150a-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="c150a-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c150a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c150a-105">Aplica a evolução temporal por um termo Z descrito por um `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="c150a-105">Applies time-evolution by a Z term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedZTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c150a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c150a-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="c150a-107">termo : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="c150a-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="c150a-108">`GeneratorIndex` representando um termo Z.</span><span class="sxs-lookup"><span data-stu-id="c150a-108">`GeneratorIndex` representing a Z term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="c150a-109">stepSize : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c150a-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c150a-110">Duração da evolução do tempo.</span><span class="sxs-lookup"><span data-stu-id="c150a-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="c150a-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c150a-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c150a-112">Qubit que determina o sinal da evolução do tempo.</span><span class="sxs-lookup"><span data-stu-id="c150a-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="c150a-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c150a-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c150a-114">Qubits de Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="c150a-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c150a-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c150a-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

