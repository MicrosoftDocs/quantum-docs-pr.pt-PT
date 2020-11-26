---
uid: Microsoft.Quantum.Canon.ApplyToMostCA
title: Aplicação Da OperaçãoMostCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostCA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 2ce76d2a86665fbfa5f5d91df23220c7c80981e3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208419"
---
# <a name="applytomostca-operation"></a>Aplicação Da OperaçãoMostCA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma operação a todos, menos ao último elemento de uma matriz.

```qsharp
operation ApplyToMostCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Most(targets))` .

## <a name="input"></a>Entrada

### <a name="op--t--unit--is-adj--ctl"></a>op : 'T[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl

Uma operação a ser aplicada.


### <a name="targets--t"></a>objetivos : 'T[]

Uma série de alvos, dos quais todos, menos o último, serão aplicados `op` a .



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de entrada da operação a aplicar.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyToMost](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [Microsoft.Quantum.Canon.ApplyToMostA](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [Microsoft.Quantum.Canon.ApplyToMostC](xref:Microsoft.Quantum.Canon.ApplyToMostC)