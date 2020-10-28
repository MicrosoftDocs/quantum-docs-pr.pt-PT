---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: Operação MeasureAllZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 4ac36a77b37f672859e61f3db89a43f4ca1fc93c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711073"
---
# <a name="measureallz-operation"></a>Operação MeasureAllZ

Espaço de nome: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)

Pacote: [](https://nuget.org/packages/)


Mede conjuntamente um registo de qubits na base Pauli Z.

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a>Descrição

Mede um registo de qubits na base $Z \otimes Z \otimes \cdots \otimes Z$ base, representando a paridade de todo o registo.

## <a name="input"></a>Entrada

### <a name="register--qubit"></a>registo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

O registo a medir.



## <a name="output--__invalidresult__"></a>Saída: __<Result> inválida__

O resultado da medição $Z \otimes Z \otimes \cdots \otimes Z$.