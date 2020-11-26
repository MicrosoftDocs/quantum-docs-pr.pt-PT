---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: Função TargetStateReflectionOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: 65ad316a6ac986ebd0dc28b25859026a60aa3239
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191113"
---
# <a name="targetstatereflectionoracle-function"></a><span data-ttu-id="1f19c-102">Função TargetStateReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="1f19c-102">TargetStateReflectionOracle function</span></span>

<span data-ttu-id="1f19c-103">Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="1f19c-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="1f19c-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1f19c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1f19c-105">Constrói um `ReflectionOracle` estado-alvo marcado exclusivamente pelo qubit da bandeira.</span><span class="sxs-lookup"><span data-stu-id="1f19c-105">Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.</span></span>

<span data-ttu-id="1f19c-106">O estado-alvo tem um único qubit definido para 1, e todos os outros 0: $\ket {1} _f$.</span><span class="sxs-lookup"><span data-stu-id="1f19c-106">The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.</span></span>

```qsharp
function TargetStateReflectionOracle (idxFlagQubit : Int) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="input"></a><span data-ttu-id="1f19c-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="1f19c-107">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="1f19c-108">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1f19c-108">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1f19c-109">Índice para qubit de bandeira $f$ de oráculo.</span><span class="sxs-lookup"><span data-stu-id="1f19c-109">Index to flag qubit $f$ of oracle.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="1f19c-110">Saída : [ReflexãoOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="1f19c-110">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="1f19c-111">Um `ReflectionOracle` que reflete sobre o estado marcado por $\ket {1} _f$.</span><span class="sxs-lookup"><span data-stu-id="1f19c-111">A `ReflectionOracle` that reflects about the state marked by $\ket{1}_f$.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f19c-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1f19c-112">See Also</span></span>

- [<span data-ttu-id="1f19c-113">Microsoft.Quantum.Canon.ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="1f19c-113">Microsoft.Quantum.Canon.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Canon.ReflectionOracle)