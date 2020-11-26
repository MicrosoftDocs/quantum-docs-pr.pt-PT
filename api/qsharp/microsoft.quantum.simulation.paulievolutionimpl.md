---
uid: Microsoft.Quantum.Simulation.PauliEvolutionImpl
title: Operação PauliEvolutionImpl
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.

  See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 868f3eef187e8e993127cfcab21e1574583ac845
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229142"
---
# <a name="paulievolutionimpl-operation"></a><span data-ttu-id="58caa-102">Operação PauliEvolutionImpl</span><span class="sxs-lookup"><span data-stu-id="58caa-102">PauliEvolutionImpl operation</span></span>

<span data-ttu-id="58caa-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="58caa-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="58caa-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="58caa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="58caa-105">Representa um gerador dinâmico como um conjunto de portões simulados e uma expansão na base Pauli.</span><span class="sxs-lookup"><span data-stu-id="58caa-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

<span data-ttu-id="58caa-106">Consulte [a Modelação do Gerador Dinâmico](/quantum/libraries/data-structures#dynamical-generator-modeling) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="58caa-106">See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation PauliEvolutionImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, delta : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="58caa-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="58caa-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="58caa-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="58caa-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="58caa-109">Um índice gerador a ser representado como evolução unitária na base Pauli.</span><span class="sxs-lookup"><span data-stu-id="58caa-109">A generator index to be represented as unitary evolution in the Pauli basis.</span></span>


### <a name="delta--double"></a><span data-ttu-id="58caa-110">delta : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="58caa-110">delta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="58caa-111">Um multiplicador sobre a duração da evolução temporal pelo termo referenciado em `generatorIndex` .</span><span class="sxs-lookup"><span data-stu-id="58caa-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="58caa-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="58caa-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="58caa-113">Registo atuado pelo operador de evolução temporal.</span><span class="sxs-lookup"><span data-stu-id="58caa-113">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="58caa-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="58caa-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

