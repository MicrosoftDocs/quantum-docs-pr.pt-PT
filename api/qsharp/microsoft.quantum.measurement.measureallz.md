---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: Operação MeasureAllZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 6c44ab6a7983697644071f0e3cf106e9825661ee
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227085"
---
# <a name="measureallz-operation"></a>Operação MeasureAllZ

Espaço de nome: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Mede conjuntamente um registo de qubits na base Pauli Z.

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a>Description

Mede um registo de qubits na base $Z \otimes Z \otimes \cdots \otimes Z$ base, representando a paridade de todo o registo.

## <a name="input"></a>Entrada

### <a name="register--qubit"></a>registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

O registo a medir.



## <a name="output--__invalidresult__"></a>Saída: __<Result> inválida__

O resultado da medição $Z \otimes Z \otimes \cdots \otimes Z$.