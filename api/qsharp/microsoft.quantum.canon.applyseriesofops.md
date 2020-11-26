---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: Aplicação FuncionaMento DeSeriesOfOps
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: b8810e7d31689046e72905195a3a25ef80fc8d67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218007"
---
# <a name="applyseriesofops-operation"></a>Aplicação FuncionaMento DeSeriesOfOps

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma lista de operações e os seus alvos sequencialmente numa matriz.

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="listofops--t--unit-"></a>listOfOps : 'T[] = [unidade](xref:microsoft.quantum.lang-ref.unit)> []

Lista de ops, cada um tomando uma matriz 'T, a ser aplicado. São aplicados sequencialmente, o índice mais baixo primeiro.


### <a name="targets--int"></a>alvos : [Int](xref:microsoft.quantum.lang-ref.int)[][]

Matrizes aninhadas descrevendo os alvos da operação. Cada matriz deve conter uma lista de ints descrevendo os índices a serem usados.


### <a name="register--t"></a>registo : 'T[]

Registo qubit para ser agido.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T



## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)