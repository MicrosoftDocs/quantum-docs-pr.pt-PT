---
uid: Microsoft.Quantum.Canon.Delay
title: Atrasar operação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delay
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: f9f0e5c3120eb69bd7431d52d6cde5e846ffbe4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716320"
---
# <a name="delay-operation"></a>Atrasar operação

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Aplica uma determinada operação com um atraso.

```qsharp
operation Delay<'T, 'U> (op : ('T => 'U), arg : 'T, aux : Unit) : 'U
```


## <a name="description"></a>Descrição

Dada a operação e uma entrada para essa operação, aplica a operação assim que for fornecida uma entrada adicional.
Em particular, a expressão `Delay(op, arg, _)` é uma operação que se aplica `op` quando é `arg` chamada.
A expressão `Delay(op,arg,_)` permite atrasar a aplicação de `op` .

## <a name="input"></a>Entrada

### <a name="op--t--u"></a>op : 'T => 'U 

Uma operação a ser aplicada.


### <a name="arg--t"></a>arg : 'T

A entrada à qual a operação é aplicada.


### <a name="aux--unit"></a>aux : [Unidade](xref:microsoft.quantum.lang-ref.unit)

Argumento usado para atrasar a aplicação de operação utilizando aplicação parcial.



## <a name="output--u"></a>Saída : 'U



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de entrada da operação a ser adiado.
### <a name="u"></a>'U

O tipo de retorno da operação a ser adiado.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.DelayC](xref:Microsoft.Quantum.Canon.DelayC)
- [Microsoft.Quantum.Canon.Delaya](xref:Microsoft.Quantum.Canon.DelayA)
- [Microsoft.Quantum.Canon.DelayCA](xref:Microsoft.Quantum.Canon.DelayCA)
- [Microsoft.Quantum.Canon.Adiado](xref:Microsoft.Quantum.Canon.Delayed)