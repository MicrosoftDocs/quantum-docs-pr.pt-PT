---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedFermionEvolution
title: operação _JWOptimizedFermionEvolution
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedFermionEvolution
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 62fbd27f703a17a547d94e61c7a4981230a4b251
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854831"
---
# <a name="_jwoptimizedfermionevolution-operation"></a><span data-ttu-id="89299-102">operação _JWOptimizedFermionEvolution</span><span class="sxs-lookup"><span data-stu-id="89299-102">_JWOptimizedFermionEvolution operation</span></span>

<span data-ttu-id="89299-103">Espaço de nome: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="89299-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="89299-104">Pacote: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="89299-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="89299-105">Representa um gerador dinâmico como um conjunto de portões simulados e uma expansão na base JWOptimizada.</span><span class="sxs-lookup"><span data-stu-id="89299-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.</span></span>

<span data-ttu-id="89299-106">Consulte [a Modelação do Gerador Dinâmico](../libraries/data-structures#dynamical-generator-modeling) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="89299-106">See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation _JWOptimizedFermionEvolution (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="89299-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="89299-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="89299-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="89299-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="89299-109">Um índice gerador a ser representado como evolução unitária na base JWOptimizada.</span><span class="sxs-lookup"><span data-stu-id="89299-109">A generator index to be represented as unitary evolution in the JWOptimized basis.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="89299-110">stepSize : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="89299-110">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="89299-111">Um multiplicador sobre a duração da evolução temporal pelo termo referenciado em `generatorIndex` .</span><span class="sxs-lookup"><span data-stu-id="89299-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="89299-112">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="89299-112">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="89299-113">Qubit que determina o sinal da evolução do tempo.</span><span class="sxs-lookup"><span data-stu-id="89299-113">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="89299-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="89299-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="89299-115">Registo atuado pelo operador de evolução temporal.</span><span class="sxs-lookup"><span data-stu-id="89299-115">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="89299-116">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="89299-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

