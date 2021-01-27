---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation
title: AmplitudeAmplificaçãoFromStatePreparation function
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromStatePreparation
qsharp.summary: Amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: e64ad5ad4e975483f20f92c0b070dd6788ef296b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847443"
---
# <a name="amplitudeamplificationfromstatepreparation-function"></a>AmplitudeAmplificaçãoFromStatePreparation function

Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Amplificação de amplitude por oráculos para reflexões parciais.

```qsharp
function AmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrada

### <a name="phases--reflectionphases"></a>fases : [Fases de Reflexão](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Fases de reflexões parciais


### <a name="stateoracle--stateoracle"></a>stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

Oráculo unitário $A dólar que prepara o estado de arranque


### <a name="idxflagqubit--int"></a>idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)

Índice para qubit de bandeira



## <a name="output--qubit--unit--is-adj--ctl"></a>Saída : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl

Uma operação que implementa amplificação de amplitude por oráculos que são implementados por reflexões parciais.

## <a name="remarks"></a>Observações

Isto impõe condições mais rigorosas na forma dos estados de partida e alvo do que em `AmpAmpByReflectionPhases` .
Presume-se que o estado-alvo é marcado por $\ket {1} \_ f$.
Presume-se que \start{align} A\ket {0} \_ {f}\ket= {0} \_ \lambda\ket {1} \_ f\ket f\ket{\text{target}} \_ s + \sqrt{1-|\lambda|^2}\ket {0} \_ f\cdots, \end{align} Na maioria dos casos, `flagQubit` e são `auxiliaryRegister` inicializados no estado $\ket {0} \_ {f}ket {0} \_