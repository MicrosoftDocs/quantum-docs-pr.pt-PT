---
uid: Microsoft.Quantum.Canon.DelayC
title: Operação DelayC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayC
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: acb817c3322063353dc08c5d6f8c539391b3bf39
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716292"
---
# <a name="delayc-operation"></a>Operação DelayC

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Aplica uma determinada operação com um atraso.

```qsharp
operation DelayC<'T> (op : ('T => Unit is Ctl), arg : 'T, aux : Unit) : Unit
```


## <a name="description"></a>Descrição

Dada a operação e uma entrada para essa operação, aplica a operação assim que for fornecida uma entrada adicional.
Em particular, a expressão `Delay(op, arg, _)` é uma operação que se aplica `op` quando é `arg` chamada.
A expressão `Delay(op,arg,_)` permite atrasar a aplicação de `op` .

## <a name="input"></a>Entrada

### <a name="op--t--unit-ctl"></a>op : 'T => [Unidade](xref:microsoft.quantum.lang-ref.unit) Ctl

Uma operação a ser aplicada.


### <a name="arg--t"></a>arg : 'T

A entrada à qual a operação é aplicada.


### <a name="aux--unit"></a>aux : [Unidade](xref:microsoft.quantum.lang-ref.unit)

Argumento usado para atrasar a aplicação de operação utilizando aplicação parcial.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de entrada da operação a ser adiado.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.Delay](xref:Microsoft.Quantum.Canon.Delay)
- [Microsoft.Quantum.Canon.Adiado](xref:Microsoft.Quantum.Canon.Delayed)