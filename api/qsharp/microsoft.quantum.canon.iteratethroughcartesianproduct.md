---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: Operação IterateThroughCartesianProduct
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: a0aaa8ef6aa6798d31c810254c92820f8136800c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840269"
---
# <a name="iteratethroughcartesianproduct-operation"></a>Operação IterateThroughCartesianProduct

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma operação para cada índice no produto Cartesiano de várias gamas.

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a>Descrição

Iterativamente aplica uma operação para cada elemento do produto Cartesiano `0..(bounds[0] - 1)` `0..(bounds[1] - 1)` de, ..., `0..(bounds[Length(bounds) - 1] - 1)`

## <a name="input"></a>Entrada

### <a name="bounds--int"></a>limites : [Int](xref:microsoft.quantum.lang-ref.int)[]

Uma matriz que especifica as gamas a serem iteradas, com cada gama a ser especificada como um comprimento inteiro.


### <a name="op--int--unit"></a>op: [Int](xref:microsoft.quantum.lang-ref.int)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

Uma operação a ser convocada para cada elemento do produto cartesiano dado.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Exemplo

Dada uma `op` operação, os dois cortes seguintes são equivalentes:

```qsharp
IterateThroughCartesianProduct([3, 4, 5], op);
```

```qsharp
op([0, 0, 0]);
op([1, 0, 0]);
op([2, 0, 0]);
op([0, 1, 0]);
// ...
op([0, 3, 0]);
op([0, 0, 1]);
//
op([2, 3, 4]);
```

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.IterateThroughCartesianPower](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)