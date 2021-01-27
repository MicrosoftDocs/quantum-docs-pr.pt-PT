---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimized0123Term
title: operação _JWOptimized0123Term
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimized0123Term
qsharp.summary: Applies time-evolution by a PQRS term described by a `GeneratorIndex`.
ms.openlocfilehash: 8b304ee99bf4ebfbe925285df9ee6a60775c86c4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845993"
---
# <a name="_jwoptimized0123term-operation"></a><span data-ttu-id="4b468-102">operação _JWOptimized0123Term</span><span class="sxs-lookup"><span data-stu-id="4b468-102">_JWOptimized0123Term operation</span></span>

<span data-ttu-id="4b468-103">Espaço de nome: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="4b468-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="4b468-104">Pacote: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="4b468-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="4b468-105">Aplica a evolução temporal por um termo PQRS descrito por um `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="4b468-105">Applies time-evolution by a PQRS term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimized0123Term (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4b468-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="4b468-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="4b468-107">termo : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="4b468-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="4b468-108">`GeneratorIndex` representando um termo PQRS.</span><span class="sxs-lookup"><span data-stu-id="4b468-108">`GeneratorIndex` representing a PQRS term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="4b468-109">stepSize : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4b468-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4b468-110">Duração da evolução do tempo.</span><span class="sxs-lookup"><span data-stu-id="4b468-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="4b468-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4b468-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4b468-112">Qubit que determina o sinal da evolução do tempo.</span><span class="sxs-lookup"><span data-stu-id="4b468-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="4b468-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4b468-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4b468-114">Qubits de Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="4b468-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4b468-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4b468-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

