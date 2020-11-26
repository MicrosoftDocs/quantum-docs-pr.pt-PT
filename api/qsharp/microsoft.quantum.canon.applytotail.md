---
uid: Microsoft.Quantum.Canon.ApplyToTail
title: AplicarOperaçãoToTail
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTail
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 6754d41e63ea0357487fa2f62bd9209843a93347
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207977"
---
# <a name="applytotail-operation"></a>AplicarOperaçãoToTail

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma operação ao último elemento de uma matriz.

```qsharp
operation ApplyToTail<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a>Description

Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Tail(targets))` .

## <a name="input"></a>Entrada

### <a name="op--t--unit"></a>op : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

Uma operação a ser aplicada.


### <a name="targets--t"></a>objetivos : 'T[]

Uma série de alvos, dos quais o último será aplicado `op` .



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de entrada da operação a aplicar.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyToTaila](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [Microsoft.Quantum.Canon.ApplyToTailC](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [Microsoft.Quantum.Canon.ApplyToTailCA](xref:Microsoft.Quantum.Canon.ApplyToTailCA)