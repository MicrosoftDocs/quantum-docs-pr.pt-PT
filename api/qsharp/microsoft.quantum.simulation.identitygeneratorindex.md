---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: Função IdentidadeGeneratorIndex
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: d2af2dafaf75a68546cb3f16c04cf4c7ee50c6ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724542"
---
# <a name="identitygeneratorindex-function"></a><span data-ttu-id="eafbf-102">Função IdentidadeGeneratorIndex</span><span class="sxs-lookup"><span data-stu-id="eafbf-102">IdentityGeneratorIndex function</span></span>

<span data-ttu-id="eafbf-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="eafbf-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="eafbf-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eafbf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eafbf-105">Devolve um índice gerador consistente com o Hamiltonian zero, `H = 0` que corresponde à operação de evolução da identidade.</span><span class="sxs-lookup"><span data-stu-id="eafbf-105">Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.</span></span>

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="eafbf-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="eafbf-106">Input</span></span>

### <a name="idxterm--int"></a><span data-ttu-id="eafbf-107">idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eafbf-107">idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="eafbf-108">Esta entrada é ignorada e definida para a consistência com o tipo definido pelo <xref:microsoft.quantum.simulation.generatorsystem> utilizador.</span><span class="sxs-lookup"><span data-stu-id="eafbf-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.simulation.generatorsystem> user-defined type.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="eafbf-109">Saída : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="eafbf-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="eafbf-110">Um índice gerador que representa a evolução sob o $H Hamiltonian = 0$.</span><span class="sxs-lookup"><span data-stu-id="eafbf-110">A generator index representing evolution under the Hamiltonian $H = 0$.</span></span>