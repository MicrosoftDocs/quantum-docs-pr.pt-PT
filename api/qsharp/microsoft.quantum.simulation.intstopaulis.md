---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: Função IntsToPaulis
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 605257aa7ca39e457127e3c3459b5891145b1863
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709449"
---
# <a name="intstopaulis-function"></a><span data-ttu-id="94113-102">Função IntsToPaulis</span><span class="sxs-lookup"><span data-stu-id="94113-102">IntsToPaulis function</span></span>

<span data-ttu-id="94113-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="94113-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="94113-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="94113-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="94113-105">Converte uma variedade de inteiros para uma variedade de operadores Pauli de um único qubit.</span><span class="sxs-lookup"><span data-stu-id="94113-105">Converts an array of integers to an array of single-qubit Pauli operators.</span></span>

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="94113-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="94113-106">Input</span></span>

### <a name="ints--int"></a><span data-ttu-id="94113-107">ints : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="94113-107">ints : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="94113-108">Conjunto de inteiros na gama `0..3`  a converter para operadores Pauli.</span><span class="sxs-lookup"><span data-stu-id="94113-108">Array of integers in the range `0..3`  to be converted to Pauli operators.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="94113-109">Saída : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="94113-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="94113-110">Uma matriz `paulis` de operadores Pauli `Pauli[]` com o mesmo comprimento que tal que é igual ao elemento dado por `ints` `paulis[idxPauli]` `[PauliI, PauliX, PauliY, PauliZ]` `ints[idxPauli]` .</span><span class="sxs-lookup"><span data-stu-id="94113-110">An array `paulis` of Pauli operators `Pauli[]` the same length as `ints` such that `paulis[idxPauli]` is equal to the element of `[PauliI, PauliX, PauliY, PauliZ]` given by `ints[idxPauli]`.</span></span>