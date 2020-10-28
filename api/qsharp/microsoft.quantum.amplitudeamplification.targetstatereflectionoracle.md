---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: Função TargetStateReflectionOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: a6ed0397be57ef6f14a712749cc416e1fd98b71c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721728"
---
# <a name="targetstatereflectionoracle-function"></a><span data-ttu-id="b2f39-102">Função TargetStateReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="b2f39-102">TargetStateReflectionOracle function</span></span>

<span data-ttu-id="b2f39-103">Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="b2f39-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="b2f39-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b2f39-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b2f39-105">Constrói um `ReflectionOracle` estado-alvo marcado exclusivamente pelo qubit da bandeira.</span><span class="sxs-lookup"><span data-stu-id="b2f39-105">Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.</span></span>

<span data-ttu-id="b2f39-106">O estado-alvo tem um único qubit definido para 1, e todos os outros 0: $\ket {1} _f$.</span><span class="sxs-lookup"><span data-stu-id="b2f39-106">The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.</span></span>

```qsharp
function TargetStateReflectionOracle (idxFlagQubit : Int) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="input"></a><span data-ttu-id="b2f39-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="b2f39-107">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="b2f39-108">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b2f39-108">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b2f39-109">Índice para qubit de bandeira $f$ de oráculo.</span><span class="sxs-lookup"><span data-stu-id="b2f39-109">Index to flag qubit $f$ of oracle.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="b2f39-110">Saída : [ReflexãoOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="b2f39-110">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="b2f39-111">Um `ReflectionOracle` que reflete sobre o estado marcado por $\ket {1} _f$.</span><span class="sxs-lookup"><span data-stu-id="b2f39-111">A `ReflectionOracle` that reflects about the state marked by $\ket{1}_f$.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2f39-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b2f39-112">See Also</span></span>

- [<span data-ttu-id="b2f39-113">Microsoft.Quantum.Canon.ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="b2f39-113">Microsoft.Quantum.Canon.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Canon.ReflectionOracle)