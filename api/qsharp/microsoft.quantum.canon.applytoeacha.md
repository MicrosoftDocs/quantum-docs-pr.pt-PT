---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: AplicarToachA operação
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 9819e78760caf6180edc5c2ca5e402060e3029a5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217803"
---
# <a name="applytoeacha-operation"></a>AplicarToachA operação

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma operação de um único qubit a cada elemento num registo.
O modificador `A` indica que a operação de um único qubit é adjacente.

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a>Entrada

### <a name="singleelementoperation--t--unit--is-adj"></a>singleElementOperação : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj

Operação a aplicar a cada qubit.


### <a name="register--t"></a>registo : 'T[]

Matriz de qubits para aplicar a operação dada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O alvo no qual a operação atua.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyToEach](xref:Microsoft.Quantum.Canon.ApplyToEach)