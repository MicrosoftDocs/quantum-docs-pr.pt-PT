---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: Medida OperaçãoPaulis
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 1bc14ec8e7c608d1195a03a354c71e870594f86d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853774"
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