---
uid: Microsoft.Quantum.Canon.ApplyToElementCA
title: Aplicação OperaçãoToElementCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementCA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 599a8afe1ab97b0ab0d6621cabd7707faaeddda3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717443"
---
# <a name="applytoelementca-operation"></a>Aplicação OperaçãoToElementCA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Aplica uma operação a um determinado elemento de uma matriz.

```qsharp
operation ApplyToElementCA<'T> (op : ('T => Unit is Adj + Ctl), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a>Descrição

Dada a `op` operação, `index` `targets` aplica-se um índice , e uma série de alvos `op(targets[index])` .

## <a name="input"></a>Entrada

### <a name="op--t--unit-adj--ctl"></a>op : 'T => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl

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
- [Microsoft.Quantum.Canon.ApplyToElementa](xref:Microsoft.Quantum.Canon.ApplyToElementA)