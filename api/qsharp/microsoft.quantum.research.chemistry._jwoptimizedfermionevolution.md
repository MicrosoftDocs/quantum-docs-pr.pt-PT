---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedFermionEvolution
title: operação _JWOptimizedFermionEvolution
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedFermionEvolution
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 5976b65d44c0e8597088dbaa6b85ffde634edcdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722795"
---
# <a name="_jwoptimizedfermionevolution-operation"></a><span data-ttu-id="5d4b4-102">operação _JWOptimizedFermionEvolution</span><span class="sxs-lookup"><span data-stu-id="5d4b4-102">_JWOptimizedFermionEvolution operation</span></span>

<span data-ttu-id="5d4b4-103">Espaço de nome: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="5d4b4-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="5d4b4-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5d4b4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5d4b4-105">Representa um gerador dinâmico como um conjunto de portões simulados e uma expansão na base JWOptimizada.</span><span class="sxs-lookup"><span data-stu-id="5d4b4-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.</span></span>

<span data-ttu-id="5d4b4-106">Consulte [a Modelação do Gerador Dinâmico](../libraries/data-structures#dynamical-generator-modeling) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="5d4b4-106">See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation _JWOptimizedFermionEvolution (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="5d4b4-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="5d4b4-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="5d4b4-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="5d4b4-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="5d4b4-109">Um índice gerador a ser representado como evolução unitária na base JWOptimizada.</span><span class="sxs-lookup"><span data-stu-id="5d4b4-109">A generator index to be represented as unitary evolution in the JWOptimized basis.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="5d4b4-110">stepSize : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5d4b4-110">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5d4b4-111">Um multiplicador sobre a duração da evolução temporal pelo termo referenciado em `generatorIndex` .</span><span class="sxs-lookup"><span data-stu-id="5d4b4-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="5d4b4-112">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5d4b4-112">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5d4b4-113">Qubit que determina o sinal da evolução do tempo.</span><span class="sxs-lookup"><span data-stu-id="5d4b4-113">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="5d4b4-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5d4b4-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5d4b4-115">Registo atuado pelo operador de evolução temporal.</span><span class="sxs-lookup"><span data-stu-id="5d4b4-115">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5d4b4-116">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5d4b4-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

