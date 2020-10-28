---
uid: Microsoft.Quantum.Simulation.PauliStringFromGenIdx
title: Função PauliStringFromGenIdx
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliStringFromGenIdx
qsharp.summary: Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: 33da4bc3d7e58b87aef75b453b6af09a51214923
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710541"
---
# <a name="paulistringfromgenidx-function"></a><span data-ttu-id="6e42c-102">Função PauliStringFromGenIdx</span><span class="sxs-lookup"><span data-stu-id="6e42c-102">PauliStringFromGenIdx function</span></span>

<span data-ttu-id="6e42c-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="6e42c-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="6e42c-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6e42c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6e42c-105">Extrai a corda Pauli e os seus índices qubit de um termo Pauli descrito por um `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="6e42c-105">Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliStringFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : (Pauli[], Int[])
```


## <a name="input"></a><span data-ttu-id="6e42c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6e42c-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="6e42c-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="6e42c-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="6e42c-108">`GeneratorIndex` tipo que codifica um termo Pauli.</span><span class="sxs-lookup"><span data-stu-id="6e42c-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--pauliint"></a><span data-ttu-id="6e42c-109">Saída :[(Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="6e42c-109">Output : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

<span data-ttu-id="6e42c-110">A cadeia Pauli do termo descrito por um `GeneratorIndex` , e índices para os qubits em que atua.</span><span class="sxs-lookup"><span data-stu-id="6e42c-110">The Pauli string of the term described by a `GeneratorIndex`, and indices to the qubits it acts on.</span></span>