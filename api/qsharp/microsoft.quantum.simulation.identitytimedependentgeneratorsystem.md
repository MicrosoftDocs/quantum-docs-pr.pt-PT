---
uid: Microsoft.Quantum.Simulation.IdentityTimeDependentGeneratorSystem
title: Função IdentityTimeDependentGeneratorSystem
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a time-dependent generator system consistent with the Hamiltonian `H(s) = 0`.
ms.openlocfilehash: d0c1ba6d7a3c3cbd62a15fec2154a05acb27a35c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225096"
---
# <a name="identitytimedependentgeneratorsystem-function"></a><span data-ttu-id="cc162-102">Função IdentityTimeDependentGeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="cc162-102">IdentityTimeDependentGeneratorSystem function</span></span>

<span data-ttu-id="cc162-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="cc162-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="cc162-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cc162-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cc162-105">Devolve um sistema gerador dependente do tempo consistente com o `H(s) = 0` Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="cc162-105">Returns a time-dependent generator system consistent with the Hamiltonian `H(s) = 0`.</span></span>

```qsharp
function IdentityTimeDependentGeneratorSystem () : Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
```


## <a name="output--timedependentgeneratorsystem"></a><span data-ttu-id="cc162-106">Saída : [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="cc162-106">Output : [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span></span>

<span data-ttu-id="cc162-107">Um sistema gerador dependente do tempo que representa a evolução sob o $H(s) Hamiltonian = 0$ para todos os $s$.</span><span class="sxs-lookup"><span data-stu-id="cc162-107">A time dependent generator system representing evolution under the Hamiltonian $H(s) = 0$ for all $s$.</span></span>