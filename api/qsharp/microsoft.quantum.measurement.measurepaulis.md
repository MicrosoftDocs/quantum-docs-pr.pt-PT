---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: Medida OperaçãoPaulis
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 4faaf78f24fa28ae5e4f701b80d9297c910b975e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194224"
---
# <a name="measurepaulis-operation"></a>Medida OperaçãoPaulis

Espaço de nome: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada uma série de operadores de Pauli multi-qubit, mede cada um usando um dispositivo de medição especificado e, em seguida, devolve a matriz de resultados.

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a>Entrada

### <a name="paulis--pauli"></a>paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][ ]

Conjunto de operadores de Pauli multi-qubit para medir.


### <a name="target--qubit"></a>alvo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registe-se sobre os quais medir os operadores em determinadas empresas.


### <a name="gadget--pauliqubit--__invalidresult__"></a>gadget :[(Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __inválidos <Result>__ 

Funcionamento que efetua a medição de um determinado operador multi-qubit.



## <a name="output--__invalidresult__"></a>Saída: __<Result> inválido__[]

A matriz de resultados obtidos a partir da medição de cada elemento de `paulis` `target` .