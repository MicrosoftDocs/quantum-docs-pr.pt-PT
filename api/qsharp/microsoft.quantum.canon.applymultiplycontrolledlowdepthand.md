---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: AplicarMultiplyControlledLowDepth E operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 0ad4b6eabcbbb63751489dd92a13a6673c1ae6b1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841665"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a>AplicarMultiplyControlledLowDepth E operação

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implementa um portão Toffoli controlado por vários controlos, assumindo que o qubit alvo é inicializado 0.  A operação adjacente pressupõe que o qubit-alvo será reposto para 0.  Requer uma profundidade Rz de 1, enquanto o número de qubits do ajudante são exponencials no número de qubits.

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a>Entrada

### <a name="controls--qubit"></a>controlos: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits de controlo


### <a name="target--qubit"></a>alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit alvo



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

