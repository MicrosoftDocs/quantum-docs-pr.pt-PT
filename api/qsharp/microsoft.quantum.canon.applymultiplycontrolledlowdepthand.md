---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: AplicarMultiplyControlledLowDepth E operação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 6900f9b0f014fba28ae73a70f180f3e4696900cd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717947"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a>AplicarMultiplyControlledLowDepth E operação

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Implementa um portão Toffoli controlado por vários controlos, assumindo que o qubit alvo é inicializado 0.  A operação adjacente pressupõe que o qubit-alvo será reposto para 0.  Requer uma profundidade Rz de 1, enquanto o número de qubits do ajudante são exponencials no número de qubits.

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a>Entrada

### <a name="controls--qubit"></a>controlos: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits de controlo


### <a name="target--qubit"></a>alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit alvo



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

