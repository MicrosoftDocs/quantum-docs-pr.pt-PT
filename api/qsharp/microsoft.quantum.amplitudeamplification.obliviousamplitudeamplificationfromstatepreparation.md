---
uid: Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation
title: Função de anulação da 20daplificação da 1.90da ção
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ObliviousAmplitudeAmplificationFromStatePreparation
qsharp.summary: Oblivious amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 873c436d4b8d8efc9dc61c2baba9b0e0f7f09fc2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845812"
---
# <a name="obliviousamplitudeamplificationfromstatepreparation-function"></a>Função de anulação da 20daplificação da 1.90da ção

Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Amplificação de amplitude alheia por oráculos para reflexões parciais.

```qsharp
function ObliviousAmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, idxFlagQubit : Int) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrada

### <a name="phases--reflectionphases"></a>fases : [Fases de Reflexão](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Fases de reflexões parciais


### <a name="startstateoracle--deterministicstateoracle"></a>startStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

Oráculo unitário $A$ que prepara estado de arranque auxiliar


### <a name="signaloracle--obliviousoracle"></a>signalOracle : [Óforo-do-diacle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

Oráculo unitário $O$ do tipo `ObliviousOracle` que atua conjuntamente no registo auxiliar e do sistema


### <a name="idxflagqubit--int"></a>idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)

Índice para registo de bandeira de um único qubit



## <a name="output--qubitqubit--unit--is-adj--ctl"></a>Saída :[(Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = [> Unit](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl

Uma operação que implementa amplificação de amplitude alheia baseada em reflexos parciais.

## <a name="remarks"></a>Observações

Isto impõe condições mais rigorosas sob a forma dos estados auxiliares de início e alvo do que em `AmpAmpObliviousByReflectionPhases` .
Presume-se que $A\ket {0} \_ f\ket {0} \_ a= \ket{\text{start}} \_ {fa}$ prepara o estado de início auxiliar $\ket{\text{start}} \_ {fa}$ da base computacional $\ket {0} \_ f\ket {0} $.
Presume-se que o estado-alvo é marcado por $\ket {1} \_ f$.
Presume-se que \start{align} O\ket{\text{start}} \_ {fa}\ket{\psi} \_ s= \lambda\ket {1} \_ f\ket f\ket{\text{anything}} \_ a\ket{text{target}} \_ u\ket\psi} \_ s + \sqrt{1-|\lambda|^2}ket {0} \_ \end{align} para alguns $U unitários$.