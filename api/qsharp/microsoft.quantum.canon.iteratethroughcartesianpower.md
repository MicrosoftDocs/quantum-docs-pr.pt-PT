---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: Operação IterateThroughCartesianPower
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 2883e7cb30633afe51d380befe806665207c5abd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206481"
---
# <a name="iteratethroughcartesianpower-operation"></a>Operação IterateThroughCartesianPower

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma operação para cada índice na potência cartesiana de uma gama de inteiros.

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a>Description

Iterativamente aplica uma operação para cada elemento de uma potência cartesiana da gama `0..(bound - 1)` .

## <a name="input"></a>Entrada

### <a name="power--int"></a>poder : [Int](xref:microsoft.quantum.lang-ref.int)

O poder cartesiano para o qual o alcance `0..(bound - 1)` deve ser elevado.


### <a name="bound--int"></a>vinculado : [Int](xref:microsoft.quantum.lang-ref.int)

Uma especificação da gama a ser iterada, dada como o comprimento da gama.


### <a name="op--int--unit"></a>op: [Int](xref:microsoft.quantum.lang-ref.int)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

Uma operação a ser convocada para cada elemento do poder cartesiano dado.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.IterateThroughCartesianProduct](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)