---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: Operação IterateThroughCartesianProduct
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: e4fc71f6f707639f6f89eece8546ec2fb434a15a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716040"
---
# <a name="iteratethroughcartesianproduct-operation"></a>Operação IterateThroughCartesianProduct

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


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



## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.IterateThroughCartesianPower](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)