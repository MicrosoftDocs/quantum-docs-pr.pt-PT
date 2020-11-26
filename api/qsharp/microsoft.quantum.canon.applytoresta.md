---
uid: Microsoft.Quantum.Canon.ApplyToRestA
title: Aplicar operaçãoTorestA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 34cb5071dd939d0831e39bb8f1670670ae1fad31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208312"
---
# <a name="applytoresta-operation"></a>Aplicar operaçãoTorestA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma operação a todos menos ao primeiro elemento de uma matriz.

```qsharp
operation ApplyToRestA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a>Description

Dada a operação `op` e uma série de alvos, `targets` aplica-se `op(Rest(targets))` .

## <a name="input"></a>Entrada

### <a name="op--t--unit--is-adj"></a>op : 'T[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj

Uma operação a ser aplicada.


### <a name="targets--t"></a>objetivos : 'T[]

Uma série de alvos, dos quais todos, menos o primeiro, serão aplicados `op` a .



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de entrada da operação a aplicar.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyTorest](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [Microsoft.Quantum.Canon.ApplyTorestC](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [Microsoft.Quantum.Canon.applyTorestCA](xref:Microsoft.Quantum.Canon.ApplyToRestCA)