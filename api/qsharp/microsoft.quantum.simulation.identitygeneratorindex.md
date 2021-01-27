---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: Função IdentidadeGeneratorIndex
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: b389ca1e0737463e6ccd5ce885b849c6b32d65d1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844330"
---
# <a name="identitygeneratorindex-function"></a><span data-ttu-id="f2f88-102">Função IdentidadeGeneratorIndex</span><span class="sxs-lookup"><span data-stu-id="f2f88-102">IdentityGeneratorIndex function</span></span>

<span data-ttu-id="f2f88-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="f2f88-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="f2f88-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f2f88-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f2f88-105">Devolve um índice gerador consistente com o Hamiltonian zero, `H = 0` que corresponde à operação de evolução da identidade.</span><span class="sxs-lookup"><span data-stu-id="f2f88-105">Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.</span></span>

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="f2f88-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f2f88-106">Input</span></span>

### <a name="idxterm--int"></a><span data-ttu-id="f2f88-107">idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f2f88-107">idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f2f88-108">Esta entrada é ignorada e definida para a consistência com o tipo definido pelo <xref:microsoft.quantum.simulation.generatorsystem> utilizador.</span><span class="sxs-lookup"><span data-stu-id="f2f88-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.simulation.generatorsystem> user-defined type.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="f2f88-109">Saída : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="f2f88-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="f2f88-110">Um índice gerador que representa a evolução sob o $H Hamiltonian = 0$.</span><span class="sxs-lookup"><span data-stu-id="f2f88-110">A generator index representing evolution under the Hamiltonian $H = 0$.</span></span>