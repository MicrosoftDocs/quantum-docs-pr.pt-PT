---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsCA
title: Aplicação FuncionamentoSeriesOfOpsCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsCA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint + Controlled)
ms.openlocfilehash: 9dd1343b3ebcc75592441f150eee822cfe83f9a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217888"
---
# <a name="applyseriesofopsca-operation"></a>Aplicação FuncionamentoSeriesOfOpsCA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma lista de operações e os seus alvos sequencialmente numa matriz. (Adjacente + Controlado)

```qsharp
operation ApplySeriesOfOpsCA<'T> (listOfOps : ('T[] => Unit is Adj + Ctl)[], targets : Int[][], register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="listofops--t--unit--is-adj--ctl"></a>listOfOps : 'T[] = [> Unit](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl[]

Lista de ops, cada um tomando uma matriz 'T, a ser aplicado. São aplicados sequencialmente, o índice mais baixo primeiro.
Cada um deve ter um functor adjacente e controlado.


### <a name="targets--int"></a>alvos : [Int](xref:microsoft.quantum.lang-ref.int)[][]

Matrizes aninhadas descrevendo os alvos da operação. Cada matriz deve conter uma lista de ints descrevendo os índices a serem usados.


### <a name="register--t"></a>registo : 'T[]

Registo qubit para ser agido.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T



## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)