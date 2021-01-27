---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexA
title: AplicaçãoToeachIndexA operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: fb278f217ac450ab48aa37b0035cd1bdd295d3e5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850835"
---
# <a name="applytoeachindexa-operation"></a>AplicaçãoToeachIndexA operação

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma operação de um único qubit a cada elemento indexado num registo.
O modificador `A` indica que a operação de um único qubit é adjacente.

```qsharp
operation ApplyToEachIndexA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a>Entrada

### <a name="singleelementoperation--intt--unit--is-adj"></a>singleElementOperation :[(Int](xref:microsoft.quantum.lang-ref.int),'T) = [> Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj

Operação a aplicar a cada qubit.


### <a name="register--t"></a>registo : 'T[]

Matriz de qubits para aplicar a operação dada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O alvo em que cada uma das operações atua.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyToEachIndex](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)