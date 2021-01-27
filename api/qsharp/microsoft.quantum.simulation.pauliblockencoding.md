---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: Função PauliBlockEncoding
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 2e37b40c60d19aa747114de988dddc19f0d7c50b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848011"
---
# <a name="pauliblockencoding-function"></a><span data-ttu-id="aa957-102">Função PauliBlockEncoding</span><span class="sxs-lookup"><span data-stu-id="aa957-102">PauliBlockEncoding function</span></span>

<span data-ttu-id="aa957-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="aa957-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="aa957-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aa957-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aa957-105">Cria uma unidade de codificação de blocos para um Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="aa957-105">Creates a block-encoding unitary for a Hamiltonian.</span></span>

<span data-ttu-id="aa957-106">O hamiltoniano $H=\sum_{j}\alpha_j P_j$ é descrito por uma soma de termos Pauli $P_j$, cada um com coeficiente real $\alpha_j$.</span><span class="sxs-lookup"><span data-stu-id="aa957-106">The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.</span></span>

```qsharp
function PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a><span data-ttu-id="aa957-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="aa957-107">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="aa957-108">sistema gerador : [Sistema gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="aa957-108">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="aa957-109">Um `GeneratorSystem` que descreve $H$ como uma soma de termos Pauli</span><span class="sxs-lookup"><span data-stu-id="aa957-109">A `GeneratorSystem` that describes $H$ as a sum of Pauli terms</span></span>



## <a name="output--doubleblockencodingreflection"></a><span data-ttu-id="aa957-110">Saída : ([Duplo,](xref:microsoft.quantum.lang-ref.double)[BlockEncodingReflection)](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="aa957-110">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="aa957-111">Primeiro parâmetro</span><span class="sxs-lookup"><span data-stu-id="aa957-111">First parameter</span></span>

<span data-ttu-id="aa957-112">A norma única dos coeficientes $\alpha=\sum_{j}|\alpha_j|$.</span><span class="sxs-lookup"><span data-stu-id="aa957-112">The one-norm of coefficients $\alpha=\sum_{j}|\alpha_j|$.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="aa957-113">Segundo parâmetro</span><span class="sxs-lookup"><span data-stu-id="aa957-113">Second parameter</span></span>

<span data-ttu-id="aa957-114">Um `BlockEncodingReflection` $U de dólar unitário do Hamiltonian $H dólares.</span><span class="sxs-lookup"><span data-stu-id="aa957-114">A `BlockEncodingReflection` unitary $U$ of the Hamiltonian $H$.</span></span> <span data-ttu-id="aa957-115">Como este unitário satisfaz $U^2 = I$, é também uma reflexão.</span><span class="sxs-lookup"><span data-stu-id="aa957-115">As this unitary satisfies $U^2 = I$, it is also a reflection.</span></span>

## <a name="remarks"></a><span data-ttu-id="aa957-116">Observações</span><span class="sxs-lookup"><span data-stu-id="aa957-116">Remarks</span></span>

<span data-ttu-id="aa957-117">Isto obtém-se preparando e despreparando o estado $\sum_{j}sqrt{\alpha_j/\alpha}\ket{j}$, e construindo uma unidade unitária controlada por multiplicássi <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> e <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .</span><span class="sxs-lookup"><span data-stu-id="aa957-117">This is obtained by preparing and unpreparing the state $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, and constructing a multiply-controlled unitary <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> and <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator>.</span></span>