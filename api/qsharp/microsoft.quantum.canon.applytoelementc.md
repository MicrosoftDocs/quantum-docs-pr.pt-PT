---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: Aplicação OperaçãoElementC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: c8d7841e3846ab435671f7959c724f987d8ad5a0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217582"
---
# <a name="applytoelementc-operation"></a>Aplicação OperaçãoElementC

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma operação a um determinado elemento de uma matriz.

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a>Description

Dada a `op` operação, `index` `targets` aplica-se um índice , e uma série de alvos `op(targets[index])` .

## <a name="input"></a>Entrada

### <a name="op--t--unit--is-ctl"></a>op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é CTL

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
- [Microsoft.Quantum.Canon.ApplyToElementa](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [Microsoft.Quantum.Canon.ApplyToElementCA](xref:Microsoft.Quantum.Canon.ApplyToElementCA)