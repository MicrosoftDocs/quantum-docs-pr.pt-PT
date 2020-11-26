---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: Função PauliBlockEncoding
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: b1df6d239e6ef061cf0a4784c652e9dd126991d5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230434"
---
# <a name="pauliblockencoding-function"></a><span data-ttu-id="1e480-102">Função PauliBlockEncoding</span><span class="sxs-lookup"><span data-stu-id="1e480-102">PauliBlockEncoding function</span></span>

<span data-ttu-id="1e480-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="1e480-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="1e480-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1e480-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1e480-105">Cria uma unidade de codificação de blocos para um Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="1e480-105">Creates a block-encoding unitary for a Hamiltonian.</span></span>

<span data-ttu-id="1e480-106">O hamiltoniano $H=\sum_{j}\alpha_j P_j$ é descrito por uma soma de termos Pauli $P_j$, cada um com coeficiente real $\alpha_j$.</span><span class="sxs-lookup"><span data-stu-id="1e480-106">The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.</span></span>

```qsharp
function PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a><span data-ttu-id="1e480-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="1e480-107">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="1e480-108">sistema gerador : [Sistema gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="1e480-108">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="1e480-109">Um `GeneratorSystem` que descreve $H$ como uma soma de termos Pauli</span><span class="sxs-lookup"><span data-stu-id="1e480-109">A `GeneratorSystem` that describes $H$ as a sum of Pauli terms</span></span>



## <a name="output--doubleblockencodingreflection"></a><span data-ttu-id="1e480-110">Saída : ([Duplo,](xref:microsoft.quantum.lang-ref.double)[BlockEncodingReflection)](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="1e480-110">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="1e480-111">Primeiro parâmetro</span><span class="sxs-lookup"><span data-stu-id="1e480-111">First parameter</span></span>

<span data-ttu-id="1e480-112">A norma única dos coeficientes $\alpha=\sum_{j}[alpha_j</span><span class="sxs-lookup"><span data-stu-id="1e480-112">The one-norm of coefficients $\alpha=\sum_{j}|\alpha_j|$.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="1e480-113">Segundo parâmetro</span><span class="sxs-lookup"><span data-stu-id="1e480-113">Second parameter</span></span>

<span data-ttu-id="1e480-114">Um `BlockEncodingReflection` $U de dólar unitário do Hamiltonian $H dólares.</span><span class="sxs-lookup"><span data-stu-id="1e480-114">A `BlockEncodingReflection` unitary $U$ of the Hamiltonian $H$.</span></span> <span data-ttu-id="1e480-115">Como este unitário satisfaz $U^2 = I$, é também uma reflexão.</span><span class="sxs-lookup"><span data-stu-id="1e480-115">As this unitary satisfies $U^2 = I$, it is also a reflection.</span></span>

## <a name="remarks"></a><span data-ttu-id="1e480-116">Observações</span><span class="sxs-lookup"><span data-stu-id="1e480-116">Remarks</span></span>

<span data-ttu-id="1e480-117">Isto obtém-se preparando e despreparando o estado $\sum_{j}sqrt{\alpha_j/\alpha}\ket{j}$, e construindo uma unidade unitária controlada por multiplicássi <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> e <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .</span><span class="sxs-lookup"><span data-stu-id="1e480-117">This is obtained by preparing and unpreparing the state $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, and constructing a multiply-controlled unitary <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> and <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator>.</span></span>