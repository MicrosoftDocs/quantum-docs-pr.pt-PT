---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyObliviousAmplitudeAmplification
title: Operação ApplyObliviousAmplitudeAmplification
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyObliviousAmplitudeAmplification
qsharp.summary: Oblivious amplitude amplification by specifying partial reflections.
ms.openlocfilehash: c171021272076cc3960307523e25c4493bb49c5a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845861"
---
# <a name="applyobliviousamplitudeamplification-operation"></a>Operação ApplyObliviousAmplitudeAmplification

Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Amplificação de amplitude alheia especificando reflexos parciais.

```qsharp
operation ApplyObliviousAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, auxiliaryRegister : Qubit[], systemRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="phases--reflectionphases"></a>fases : [Fases de Reflexão](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Fases de reflexões parciais


### <a name="startstatereflection--reflectionoracle"></a>startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Operador de reflexão sobre o estado inicial do registo auxiliar


### <a name="targetstatereflection--reflectionoracle"></a>targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Operador de reflexão sobre estado-alvo do registo auxiliar


### <a name="signaloracle--obliviousoracle"></a>signalOracle : [Óforo-do-diacle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

Oráculo unitário $O de$ de tipo `ObliviousOracle` que atua conjuntamente nos registos auxiliares e do sistema.


### <a name="auxiliaryregister--qubit"></a>AuxiliarRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registo auxiliar


### <a name="systemregister--qubit"></a>sistemaRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registo do sistema



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Dado um determinado estado de início auxiliar $\ket{\text{start}} \_ a$, um estado-alvo auxiliar específico $\ket{\text{target}} \_ a$, e qualquer estado do sistema $\ket{\psi} \_ s$, suponhamos que \start{align} O\ket{\text{start}} \_ a\ket{\psi} \_ s= \lambda\ket{\text{target}} \_ a U \ket{\psi} \_ s + \sqrt{1-|\lambda|^2}\ket{text{target} \_ a\cdot $U s
Através de uma sequência de reflexões sobre os estados de início e alvo no registo auxiliar intercalado por aplicações de `signalOracle` e seus adjacentes, a probabilidade de sucesso da aplicação de U pode ser alterada.

Na maioria dos casos, `auxiliaryRegister` é inicializado no estado $\ket{\text{start}} \_ a$.

## <a name="references"></a>Referências

Consulte

- [ *D.W. Berry, A.M. Childs, R. Cleve, R. Kothari, R.D. Somma*](https://arxiv.org/abs/1312.1414) para a versão padrão.
  Consulte
- [ *G.H. Low, I.L. Chuang*](https://arxiv.org/abs/1610.06546) para uma generalização a reflexões parciais.