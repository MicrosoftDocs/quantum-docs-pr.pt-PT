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
# <a name="targetstatereflectionoracle-function"></a>Função TargetStateReflectionOracle

Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Constrói um `ReflectionOracle` estado-alvo marcado exclusivamente pelo qubit da bandeira.

O estado-alvo tem um único qubit definido para 1, e todos os outros 0: $\ket {1} _f$.

```qsharp
function TargetStateReflectionOracle (idxFlagQubit : Int) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="input"></a>Entrada

### <a name="idxflagqubit--int"></a>idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)

Índice para qubit de bandeira $f$ de oráculo.



## <a name="output--reflectionoracle"></a>Saída : [ReflexãoOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Um `ReflectionOracle` que reflete sobre o estado marcado por $\ket {1} _f$.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ReflectionOracle](xref:Microsoft.Quantum.Canon.ReflectionOracle)