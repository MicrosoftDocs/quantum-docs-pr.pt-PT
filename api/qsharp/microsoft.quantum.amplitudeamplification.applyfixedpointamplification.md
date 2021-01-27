---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: Aplicação Operação DePosição Internacional
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: fa19c3bb06ae91a2fa18acb6f853020830e749f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847222"
---
# <a name="applyfixedpointamplification-operation"></a>Aplicação Operação DePosição Internacional

Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


algoritmo de amplificação da amplitude Fixed-Point

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="statepreporacle--stateoracle"></a>EstadoPrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

Oráculo unitário que prepara o estado de partida.


### <a name="startqubits--qubit"></a>startQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registo de qubits



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Os bits de arranque devem estar no estado $\ket{0 \cdots 0}$. Esta operação itera sobre uma série de consultas em poderes de $2$ até que um número máximo de consultas seja alcançado, ou o estado alvo é encontrado.