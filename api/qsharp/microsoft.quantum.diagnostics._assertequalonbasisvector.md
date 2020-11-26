---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: operação _assertEqualOnBasisVector
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: d8f2195f75de49918032053dc8d1fa4fb4eba840
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213774"
---
# <a name="_assertequalonbasisvector-operation"></a>operação _assertEqualOnBasisVector

Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Verifica se o resultado da aplicação de duas operações `givenU` e de um estado de base é o `expectedU` mesmo. O estado de base é descrito por `basis` parâmetro.
Consulte <xref:microsoft.quantum.extensions.fliptobasis> a função para mais detalhes sobre esta descrição.

```qsharp
operation _assertEqualOnBasisVector (basis : Int[], givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Entrada

### <a name="basis--int"></a>base : [Int](xref:microsoft.quantum.lang-ref.int)[]

Estado de base especificado por um ID de base de um único qubit (0 <= id <= 3) para cada um dos $n$ qubits.


### <a name="givenu--qubit--unit"></a>givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

Operação a $n dólares qubits a serem verificados.


### <a name="expectedu--qubit--unit--is-adj"></a>expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [> Unit](xref:microsoft.quantum.lang-ref.unit)  é Adj

A operação de referência em $n$ qubits que a givenU deve ser comparada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

