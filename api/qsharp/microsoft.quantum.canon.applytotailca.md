---
uid: Microsoft.Quantum.Canon.ApplyToTailCA
title: Aplicar operaçãoToTailCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailCA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 4c702a9d310adae7a4ec404f3cf12893547623b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841189"
---
# <a name="applytotailca-operation"></a>Aplicar operaçãoToTailCA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma operação ao último elemento de uma matriz.

```qsharp
operation ApplyToTailCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a>Descrição

Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Tail(targets))` .

## <a name="input"></a>Entrada

### <a name="op--t--unit--is-adj--ctl"></a>op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl

Uma operação a ser aplicada.


### <a name="targets--t"></a>objetivos : 'T[]

Uma série de alvos, dos quais o último será aplicado `op` .



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de entrada da operação a aplicar.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyToTail](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [Microsoft.Quantum.Canon.ApplyToTaila](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [Microsoft.Quantum.Canon.ApplyToTailC](xref:Microsoft.Quantum.Canon.ApplyToTailC)