---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZTerm
title: operação _JWOptimizedZTerm
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZTerm
qsharp.summary: Applies time-evolution by a Z term described by a `GeneratorIndex`.
ms.openlocfilehash: fe68295748759a25c52f8e3c2efbc7570c9dcc1c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848048"
---
# <a name="_jwoptimizedzterm-operation"></a><span data-ttu-id="69477-102">operação _JWOptimizedZTerm</span><span class="sxs-lookup"><span data-stu-id="69477-102">_JWOptimizedZTerm operation</span></span>

<span data-ttu-id="69477-103">Espaço de nome: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="69477-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="69477-104">Pacote: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="69477-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="69477-105">Aplica a evolução temporal por um termo Z descrito por um `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="69477-105">Applies time-evolution by a Z term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedZTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="69477-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="69477-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="69477-107">termo : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="69477-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="69477-108">`GeneratorIndex` representando um termo Z.</span><span class="sxs-lookup"><span data-stu-id="69477-108">`GeneratorIndex` representing a Z term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="69477-109">stepSize : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="69477-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="69477-110">Duração da evolução do tempo.</span><span class="sxs-lookup"><span data-stu-id="69477-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="69477-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="69477-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="69477-112">Qubit que determina o sinal da evolução do tempo.</span><span class="sxs-lookup"><span data-stu-id="69477-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="69477-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="69477-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="69477-114">Qubits de Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="69477-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="69477-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="69477-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

