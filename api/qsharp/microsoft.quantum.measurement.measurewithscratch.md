---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: Medidas ComScratch
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: c42316a811e0e4a81c7f244c093a2be88fe5c733
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227068"
---
# <a name="measurewithscratch-operation"></a>Medidas ComScratch

Espaço de nome: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Mede o operador pauli dado utilizando um qubit de risco explícito para efetuar a medição.

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a>Entrada

### <a name="pauli--pauli"></a>pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Um operador de Pauli multi-qubit especificado como uma matriz de operadores pauli de um único qubit.


### <a name="target--qubit"></a>alvo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registo qubit a medir.



## <a name="output--__invalidresult__"></a>Saída: __<Result> inválida__

O resultado da medição do operador pauli no `target` registo.