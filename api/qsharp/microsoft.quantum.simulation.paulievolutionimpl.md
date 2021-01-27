---
uid: Microsoft.Quantum.Simulation.PauliEvolutionImpl
title: Operação PauliEvolutionImpl
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.

  See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 1c588c225cb7c91830e986c7eca9b9fafd445d4e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847934"
---
# <a name="paulievolutionimpl-operation"></a><span data-ttu-id="ff18f-102">Operação PauliEvolutionImpl</span><span class="sxs-lookup"><span data-stu-id="ff18f-102">PauliEvolutionImpl operation</span></span>

<span data-ttu-id="ff18f-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="ff18f-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="ff18f-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ff18f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ff18f-105">Representa um gerador dinâmico como um conjunto de portões simulados e uma expansão na base Pauli.</span><span class="sxs-lookup"><span data-stu-id="ff18f-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.</span></span>

<span data-ttu-id="ff18f-106">Consulte [a Modelação do Gerador Dinâmico](/quantum/libraries/data-structures#dynamical-generator-modeling) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="ff18f-106">See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation PauliEvolutionImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, delta : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ff18f-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="ff18f-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="ff18f-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="ff18f-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="ff18f-109">Um índice gerador a ser representado como evolução unitária na base Pauli.</span><span class="sxs-lookup"><span data-stu-id="ff18f-109">A generator index to be represented as unitary evolution in the Pauli basis.</span></span>


### <a name="delta--double"></a><span data-ttu-id="ff18f-110">delta : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ff18f-110">delta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ff18f-111">Um multiplicador sobre a duração da evolução temporal pelo termo referenciado em `generatorIndex` .</span><span class="sxs-lookup"><span data-stu-id="ff18f-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="ff18f-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ff18f-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ff18f-113">Registo atuado pelo operador de evolução temporal.</span><span class="sxs-lookup"><span data-stu-id="ff18f-113">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ff18f-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ff18f-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

