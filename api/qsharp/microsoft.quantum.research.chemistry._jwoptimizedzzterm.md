---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZZTerm
title: operação _JWOptimizedZZTerm
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZZTerm
qsharp.summary: Applies time-evolution by a ZZ term described by a `GeneratorIndex`.
ms.openlocfilehash: 824918e06e54e31834019a396b310bbaa6beeb46
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722778"
---
# <a name="_jwoptimizedzzterm-operation"></a><span data-ttu-id="227be-102">operação _JWOptimizedZZTerm</span><span class="sxs-lookup"><span data-stu-id="227be-102">_JWOptimizedZZTerm operation</span></span>

<span data-ttu-id="227be-103">Espaço de nome: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="227be-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="227be-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="227be-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="227be-105">Aplica a evolução temporal por um termo ZZ descrito por a `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="227be-105">Applies time-evolution by a ZZ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedZZTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="227be-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="227be-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="227be-107">termo : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="227be-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="227be-108">`GeneratorIndex` representando um termo ZZ.</span><span class="sxs-lookup"><span data-stu-id="227be-108">`GeneratorIndex` representing a ZZ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="227be-109">stepSize : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="227be-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="227be-110">Duração da evolução do tempo.</span><span class="sxs-lookup"><span data-stu-id="227be-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="227be-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="227be-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="227be-112">Qubit que determina o sinal da evolução do tempo.</span><span class="sxs-lookup"><span data-stu-id="227be-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="227be-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="227be-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="227be-114">Qubits de Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="227be-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="227be-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="227be-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

