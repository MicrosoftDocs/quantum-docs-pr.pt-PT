---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification
title: Função StandardAmplitudeAmplificação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardAmplitudeAmplification
qsharp.summary: Standard Amplitude Amplification algorithm
ms.openlocfilehash: 18228d45c4df280b004c595a7b0f1e2a607b8b2c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721745"
---
# <a name="standardamplitudeamplification-function"></a>Função StandardAmplitudeAmplificação

Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)

Pacote: [](https://nuget.org/packages/)


Algoritmo de amplificação de amplitude padrão

```qsharp
function StandardAmplitudeAmplification (nIterations : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrada

### <a name="niterations--int"></a>niterações : [Int](xref:microsoft.quantum.lang-ref.int)

Número de iterações $n$ de amplificação da amplitude


### <a name="stateoracle--stateoracle"></a>stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

Oráculo unitário $A dólar que prepara o estado de arranque


### <a name="idxflagqubit--int"></a>idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)

Índice para qubit de bandeira



## <a name="output--qubit--unit-adj--ctl"></a>Saída : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit)> Adj + Ctl

Uma operação que implementa o algoritmo quântico de amplificação de amplitude padrão

## <a name="remarks"></a>Observações

Este é o algoritmo de amplificação de amplitude padrão obtido por uma escolha de fases de reflexão `AmpAmpPhasesStandard` computacionalizadas por Assumindo que \start{align} A\ket {0} \_ {f}ket {0} \_ s= \lambda\ket {1} \_ f\ket{\text{target}} \_ s + \sqrt{1-\lambda^/2}ket {0} \_ f\cdots, \end{align} esta operação prepara o estado \start{align} \operatorname{AmpAmpByOracle}\ket {0} \_ {f}\ket {0} \_ s= \sin((2n+1)\sin^ {-1} (\lambda)\ket {1} \_ f\ket{\text{target}} \_ e é {0} \_ `flagQubit` `auxiliaryRegister` inicializado no estado $\ket {0} \_ f\ket {0} \_ a$.

## <a name="references"></a>Referências

- [*G. Brassard, P. Hoyer, M. Mosca, A. Tapp*](https://arxiv.org/abs/quant-ph/0005055)