---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: Aplicar operação ToHead
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 35f19cbb1090e974e18f338239764c9c8b854116
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217344"
---
# <a name="applytohead-operation"></a>Aplicar operação ToHead

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma operação ao primeiro elemento de uma matriz.

```qsharp
operation ApplyToHead<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a>Description

Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Head(targets))` .

## <a name="input"></a>Entrada

### <a name="op--t--unit"></a>op : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

Uma operação a ser aplicada.


### <a name="targets--t"></a>objetivos : 'T[]

Uma série de alvos, dos quais o primeiro será aplicado `op` .



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de entrada da operação a aplicar.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyToHeada](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [Microsoft.Quantum.Canon.ApplyToHeadc](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [Microsoft.Quantum.Canon.ApplyToHeadCA](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)