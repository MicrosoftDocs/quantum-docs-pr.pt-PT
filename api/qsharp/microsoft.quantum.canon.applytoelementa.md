---
uid: Microsoft.Quantum.Canon.ApplyToElementA
title: Aplicação OperaçãoToElementA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: f34089c2a45de281507cb79bde8a8cb9d2fefe47
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717485"
---
# <a name="applytoelementa-operation"></a>Aplicação OperaçãoToElementA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Aplica uma operação a um determinado elemento de uma matriz.

```qsharp
operation ApplyToElementA<'T> (op : ('T => Unit is Adj), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a>Descrição

Dada a `op` operação, `index` `targets` aplica-se um índice , e uma série de alvos `op(targets[index])` .

## <a name="input"></a>Entrada

### <a name="op--t--unit-adj"></a>op : 'T = [Unit](xref:microsoft.quantum.lang-ref.unit) unidade> Adj

Uma operação a ser aplicada.


### <a name="index--int"></a>índice : [Int](xref:microsoft.quantum.lang-ref.int)

Um índice na matriz de alvos.


### <a name="targets--t"></a>objetivos : 'T[]

Uma série de possíveis alvos para `op` .



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de entrada da operação a aplicar.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyToElement](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [Microsoft.Quantum.Canon.ApplyToElementC](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [Microsoft.Quantum.Canon.ApplyToElementCA](xref:Microsoft.Quantum.Canon.ApplyToElementCA)