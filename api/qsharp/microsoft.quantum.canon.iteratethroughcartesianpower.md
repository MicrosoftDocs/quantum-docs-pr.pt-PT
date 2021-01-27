---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: Operação IterateThroughCartesianPower
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 3a303d13c4a6f102dab92d814e24df9d90213fbe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840286"
---
# <a name="iteratethroughcartesianpower-operation"></a>Operação IterateThroughCartesianPower

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma operação para cada índice na potência cartesiana de uma gama de inteiros.

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a>Descrição

Iterativamente aplica uma operação para cada elemento de uma potência cartesiana da gama `0..(bound - 1)` .

## <a name="input"></a>Entrada

### <a name="power--int"></a>poder : [Int](xref:microsoft.quantum.lang-ref.int)

O poder cartesiano para o qual o alcance `0..(bound - 1)` deve ser elevado.


### <a name="bound--int"></a>vinculado : [Int](xref:microsoft.quantum.lang-ref.int)

Uma especificação da gama a ser iterada, dada como o comprimento da gama.


### <a name="op--int--unit"></a>op: [Int](xref:microsoft.quantum.lang-ref.int)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

Uma operação a ser convocada para cada elemento do poder cartesiano dado.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Exemplo

Dada uma `op` operação, os dois cortes seguintes são equivalentes:

```qsharp
IterateThroughCartesianPower(2, 3, op);
```

```qsharp
op([0, 0]);
op([1, 0]);
op([2, 0]);
op([0, 1]);
// ..
op([2, 2]);
```

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.IterateThroughCartesianProduct](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)