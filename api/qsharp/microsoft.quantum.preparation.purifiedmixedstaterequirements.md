---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements
title: Função de Excrementos do Estado Despromoficados
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateRequirements
qsharp.summary: Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".
ms.openlocfilehash: 9b8861a4112c4e6c9db994339353c771a3de81a6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229992"
---
# <a name="purifiedmixedstaterequirements-function"></a><span data-ttu-id="0b6da-102">Função de Excrementos do Estado Despromoficados</span><span class="sxs-lookup"><span data-stu-id="0b6da-102">PurifiedMixedStateRequirements function</span></span>

<span data-ttu-id="0b6da-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="0b6da-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="0b6da-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0b6da-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0b6da-105">Devolve o número total de qubits que devem ser atribuídos para aplicar a operação devolvida por @"microsoft.quantum.preparation.purifiedmixedstate" .</span><span class="sxs-lookup"><span data-stu-id="0b6da-105">Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".</span></span>

```qsharp
function PurifiedMixedStateRequirements (targetError : Double, nCoefficients : Int) : Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
```


## <a name="input"></a><span data-ttu-id="0b6da-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="0b6da-106">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="0b6da-107">targetError : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0b6da-107">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0b6da-108">O erro do alvo $\epsilon$.</span><span class="sxs-lookup"><span data-stu-id="0b6da-108">The target error $\epsilon$.</span></span>


### <a name="ncoefficients--int"></a><span data-ttu-id="0b6da-109">nCoefficientes : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0b6da-109">nCoefficients : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0b6da-110">O número de coeficientes a especificar na preparação de um estado misto.</span><span class="sxs-lookup"><span data-stu-id="0b6da-110">The number of coefficients to be specified in preparing a mixed state.</span></span>



## <a name="output--mixedstatepreparationrequirements"></a><span data-ttu-id="0b6da-111">Saída : [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)</span><span class="sxs-lookup"><span data-stu-id="0b6da-111">Output : [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)</span></span>

<span data-ttu-id="0b6da-112">Uma descrição de quantos qubits são necessários no total, e para cada um dos registos de índice e lixo usados pela @"microsoft.quantum.preparation.purifiedmixedstate" função.</span><span class="sxs-lookup"><span data-stu-id="0b6da-112">A description of how many qubits are required in total, and for each of the index and garbage registers used by the @"microsoft.quantum.preparation.purifiedmixedstate" function.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b6da-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="0b6da-113">See Also</span></span>

- [<span data-ttu-id="0b6da-114">Microsoft.Quantum.Preparation.PurifiedMixedState</span><span class="sxs-lookup"><span data-stu-id="0b6da-114">Microsoft.Quantum.Preparation.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)