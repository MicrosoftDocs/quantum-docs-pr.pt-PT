---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: operação _assertEqualOnBasisVector
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: 01b6d5aede102e47df86ea70d071d81eba1ade6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713156"
---
# <a name="_assertequalonbasisvector-operation"></a>operação _assertEqualOnBasisVector

Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacote: [](https://nuget.org/packages/)


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


### <a name="expectedu--qubit--unit-adj"></a>expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj

A operação de referência em $n$ qubits que a givenU deve ser comparada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

