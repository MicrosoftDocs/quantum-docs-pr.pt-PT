---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: função _IdentityTimeDependentGeneratorSystem
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 960842f50353c01362f90eb38d979fb7c4f15d9a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857992"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a><span data-ttu-id="ef377-102">função _IdentityTimeDependentGeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="ef377-102">_IdentityTimeDependentGeneratorSystem function</span></span>

<span data-ttu-id="ef377-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="ef377-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="ef377-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ef377-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ef377-105">Devolve um sistema gerador consistente com o `H(s) = 0` Hamiltonian, onde está um parâmetro de `s` agenda.</span><span class="sxs-lookup"><span data-stu-id="ef377-105">Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.</span></span>

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="ef377-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ef377-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="ef377-107">horário : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ef377-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ef377-108">Esta entrada é ignorada e definida para a consistência com o tipo definido pelo <xref:microsoft.quantum.canon.timedependentgeneratorsystem> utilizador.</span><span class="sxs-lookup"><span data-stu-id="ef377-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.canon.timedependentgeneratorsystem> user-defined type.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="ef377-109">Saída : [Sistema Gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="ef377-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="ef377-110">Um sistema gerador que representa a evolução sob o $H(s) Hamiltonian = 0$ para todos os $s$.</span><span class="sxs-lookup"><span data-stu-id="ef377-110">A generator system representing evolution under the Hamiltonian $H(s) = 0$ for all $s$.</span></span>