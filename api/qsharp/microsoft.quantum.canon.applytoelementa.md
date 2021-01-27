---
uid: Microsoft.Quantum.Canon.ApplyToElementA
title: Aplicação OperaçãoToElementA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 57d870c7fbd099212b13f75bd85e57c046280d73
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850756"
---
# <a name="applytoelementa-operation"></a>Aplicação OperaçãoToElementA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma operação a um determinado elemento de uma matriz.

```qsharp
operation ApplyToElementA<'T> (op : ('T => Unit is Adj), index : Int, targets : 'T[]) : Unit is Adj
```


## <a name="description"></a>Descrição

Dada a `op` operação, `index` `targets` aplica-se um índice , e uma série de alvos `op(targets[index])` .

## <a name="input"></a>Entrada

### <a name="op--t--unit--is-adj"></a>op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj

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