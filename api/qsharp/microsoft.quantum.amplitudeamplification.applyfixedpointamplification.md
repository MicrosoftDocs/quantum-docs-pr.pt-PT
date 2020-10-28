---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: Aplicação Operação DePosição Internacional
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: f506be7b2e3f65cf89694e30d79c04ec30d25035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721910"
---
# <a name="applyfixedpointamplification-operation"></a>Aplicação Operação DePosição Internacional

Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)

Pacote: [](https://nuget.org/packages/)


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