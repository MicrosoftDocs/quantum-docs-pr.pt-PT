---
uid: Microsoft.Quantum.Canon.ApplyToTailA
title: Aplicar operaçãoToTailA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 5ca22be7a38d466f9413977de663f10606171dea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841177"
---
# <a name="applytotaila-operation"></a>Aplicar operaçãoToTailA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma operação ao último elemento de uma matriz.

```qsharp
operation ApplyToTailA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a>Descrição

Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Tail(targets))` .

## <a name="input"></a>Entrada

### <a name="op--t--unit--is-adj"></a>op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj

Uma operação a ser aplicada.


### <a name="targets--t"></a>objetivos : 'T[]

Uma série de alvos, dos quais o último será aplicado `op` .



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de entrada da operação a aplicar.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyToTail](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [Microsoft.Quantum.Canon.ApplyToTailC](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [Microsoft.Quantum.Canon.ApplyToTailCA](xref:Microsoft.Quantum.Canon.ApplyToTailCA)