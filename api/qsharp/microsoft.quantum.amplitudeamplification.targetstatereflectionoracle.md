---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: Função TargetStateReflectionOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: 4169ccf3e210e27f779311553b845ea04f2c7dc6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843897"
---
# <a name="targetstatereflectionoracle-function"></a><span data-ttu-id="4af38-102">Função TargetStateReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="4af38-102">TargetStateReflectionOracle function</span></span>

<span data-ttu-id="4af38-103">Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="4af38-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="4af38-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4af38-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4af38-105">Constrói um `ReflectionOracle` estado-alvo marcado exclusivamente pelo qubit da bandeira.</span><span class="sxs-lookup"><span data-stu-id="4af38-105">Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.</span></span>

<span data-ttu-id="4af38-106">O estado-alvo tem um único qubit definido para 1, e todos os outros 0: $\ket {1} _f$.</span><span class="sxs-lookup"><span data-stu-id="4af38-106">The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.</span></span>

```qsharp
function TargetStateReflectionOracle (idxFlagQubit : Int) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="input"></a><span data-ttu-id="4af38-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="4af38-107">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="4af38-108">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4af38-108">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4af38-109">Índice para qubit de bandeira $f$ de oráculo.</span><span class="sxs-lookup"><span data-stu-id="4af38-109">Index to flag qubit $f$ of oracle.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="4af38-110">Saída : [ReflexãoOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="4af38-110">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="4af38-111">Um `ReflectionOracle` que reflete sobre o estado marcado por $\ket {1} _f$.</span><span class="sxs-lookup"><span data-stu-id="4af38-111">A `ReflectionOracle` that reflects about the state marked by $\ket{1}_f$.</span></span>

## <a name="see-also"></a><span data-ttu-id="4af38-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4af38-112">See Also</span></span>

- [<span data-ttu-id="4af38-113">Microsoft.Quantum.Canon.ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="4af38-113">Microsoft.Quantum.Canon.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Canon.ReflectionOracle)