---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: Operação de Medida de Assert
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 3fbe000202abbd8a206b0c83dfa35f4546ea91cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202452"
---
# <a name="assertmeasurement-operation"></a>Operação de Medida de Assert

Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Afirma que medir os qubits dado na dada base Pauli terá sempre o resultado dado.

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="bases--pauli"></a>bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Um efeito de medição para afirmar a probabilidade de, expressa como um operador pauli multi-qubit.


### <a name="qubits--qubit"></a>qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Um registo para fazer a afirmação.


### <a name="result--__invalidresult__"></a>resultado : __inválido <Result>__

O resultado esperado de `Measure(bases, qubits)` .


### <a name="msg--string"></a>msg : [Corda](xref:microsoft.quantum.lang-ref.string)

Uma mensagem a ser reportada se a afirmação falhar.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Note que as versões adjacentes e controladas desta operação não verificarão a condição.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Diagnostics.AssertMeasurementProbability](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)