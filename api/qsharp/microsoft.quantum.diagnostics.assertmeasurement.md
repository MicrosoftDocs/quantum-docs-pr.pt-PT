---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: Operação de Medida de Assert
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 09024cd8cd6e713360dcf7f42f55941590f35883
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713033"
---
# <a name="assertmeasurement-operation"></a>Operação de Medida de Assert

Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacote: [](https://nuget.org/packages/)


Afirma que medir os qubits dado na dada base Pauli terá sempre o resultado dado.

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit
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