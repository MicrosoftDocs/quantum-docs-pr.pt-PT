---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimized0123Term
title: operação _JWOptimized0123Term
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimized0123Term
qsharp.summary: Applies time-evolution by a PQRS term described by a `GeneratorIndex`.
ms.openlocfilehash: 9d04a866323112944aa922fafdf6fd397851277d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226099"
---
# <a name="_jwoptimized0123term-operation"></a><span data-ttu-id="cf7ca-102">operação _JWOptimized0123Term</span><span class="sxs-lookup"><span data-stu-id="cf7ca-102">_JWOptimized0123Term operation</span></span>

<span data-ttu-id="cf7ca-103">Espaço de nome: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="cf7ca-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="cf7ca-104">Pacote: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="cf7ca-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="cf7ca-105">Aplica a evolução temporal por um termo PQRS descrito por um `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="cf7ca-105">Applies time-evolution by a PQRS term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimized0123Term (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="cf7ca-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="cf7ca-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="cf7ca-107">termo : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="cf7ca-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="cf7ca-108">`GeneratorIndex` representando um termo PQRS.</span><span class="sxs-lookup"><span data-stu-id="cf7ca-108">`GeneratorIndex` representing a PQRS term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="cf7ca-109">stepSize : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cf7ca-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cf7ca-110">Duração da evolução do tempo.</span><span class="sxs-lookup"><span data-stu-id="cf7ca-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="cf7ca-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cf7ca-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="cf7ca-112">Qubit que determina o sinal da evolução do tempo.</span><span class="sxs-lookup"><span data-stu-id="cf7ca-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="cf7ca-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cf7ca-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="cf7ca-114">Qubits de Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="cf7ca-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cf7ca-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cf7ca-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

