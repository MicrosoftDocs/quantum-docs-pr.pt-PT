---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsA
title: AplicaçãoSeriesOfOpsA operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint)
ms.openlocfilehash: 052cb52d4ee6500e60043ab7f808497058924afe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844654"
---
# <a name="applyseriesofopsa-operation"></a>AplicaçãoSeriesOfOpsA operação

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma lista de operações e os seus alvos sequencialmente numa matriz. (Adjacente)

```qsharp
operation ApplySeriesOfOpsA<'T> (listOfOps : ('T[] => Unit is Adj)[], targets : Int[][], register : 'T[]) : Unit is Adj
```


## <a name="input"></a>Entrada

### <a name="listofops--t--unit--is-adj"></a>listOfOps : 'T[] = [> Unidade](xref:microsoft.quantum.lang-ref.unit)  é Adj[]

Lista de ops, cada um tomando uma matriz 'T, a ser aplicado. São aplicados sequencialmente, o índice mais baixo primeiro.
Cada um deve ter um functor adjacente


### <a name="targets--int"></a>alvos : [Int](xref:microsoft.quantum.lang-ref.int)[][]

Matrizes aninhadas descrevendo os alvos da operação. Cada matriz deve conter uma lista de ints descrevendo os índices a serem usados.


### <a name="register--t"></a>registo : 'T[]

Registo qubit para ser agido.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T



## <a name="example"></a>Exemplo

O seguinte aplica-se Exp ([PauliX, PauliY], 0,5) a qubits 0, 1 // depois X a qubit 2 lets = [Exp[PauliX, PauliY], 0,5, _), ApplyToFirstQubitA(X, _)]; Deixar os índices = [0, 1], [2]]; AplicaçãoSeriesOfOpsA (ops, índices, qubitArray);

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)