---
uid: Microsoft.Quantum.Diagnostics._iterateThroughCartesianPower
title: operação _iterateThroughCartesianPower
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _iterateThroughCartesianPower
qsharp.summary: Iterates a variable through a Cartesian product [ 0, bounds[0]-1 ] × [ 0, bounds[1]-1 ] × [ 0, bounds[Length(bounds)-1]-1 ] and calls op(arr) for every element of the Cartesian product
ms.openlocfilehash: 36666238b40d036e3f6a8949b22f5806216d71f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713142"
---
# <a name="_iteratethroughcartesianpower-operation"></a>operação _iterateThroughCartesianPower

Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacote: [](https://nuget.org/packages/)


Iterates uma variável através de um produto cartesiano [ 0, limites[0]-1 ] × [ 0, limites[1]-1 ] × [ 0, limites[Comprimento(limites)-1]-1 ] e chama op(arr) para cada elemento do produto cartesiano

```qsharp
operation _iterateThroughCartesianPower (length : Int, value : Int, op : (Int[] => Unit)) : Unit
```


## <a name="input"></a>Entrada

### <a name="length--int"></a>comprimento : [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="value--int"></a>valor : [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="op--int--unit"></a>op: [Int](xref:microsoft.quantum.lang-ref.int)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 





## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

