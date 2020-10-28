---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: Operação afirmaMeasurementProbability
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: ff0419706d825442492f82e564f1cce86f1b112f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712977"
---
# <a name="assertmeasurementprobability-operation"></a>Operação afirmaMeasurementProbability

Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacote: [](https://nuget.org/packages/)


Afirma que medir os qubits dado na dada base Pauli terá o resultado dado com a dada probabilidade, dentro de alguma tolerância.

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit
```


## <a name="input"></a>Entrada

### <a name="bases--pauli"></a>bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Um efeito de medição para afirmar a probabilidade de, expressa como um operador pauli multi-qubit.


### <a name="qubits--qubit"></a>qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Um registo para fazer a afirmação.


### <a name="result--__invalidresult__"></a>resultado : __inválido <Result>__

Um resultado esperado `Measure(bases, qubits)` de.


### <a name="prob--double"></a>prob : [Duplo](xref:microsoft.quantum.lang-ref.double)

A probabilidade com que o resultado é esperado.


### <a name="msg--string"></a>msg : [Corda](xref:microsoft.quantum.lang-ref.string)

Uma mensagem a ser reportada se a afirmação falhar.


### <a name="tol--double"></a>tol : [Duplo](xref:microsoft.quantum.lang-ref.double)





## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Note que as versões adjacentes e controladas desta operação não verificarão a condição.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Diagnostics.AssertMeasurement](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)