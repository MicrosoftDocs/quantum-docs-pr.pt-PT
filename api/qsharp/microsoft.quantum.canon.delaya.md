---
uid: Microsoft.Quantum.Canon.DelayA
title: Operação DelayA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 77c40633824ccd9250252804b08d7400936515dd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716295"
---
# <a name="delaya-operation"></a>Operação DelayA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Aplica uma determinada operação com um atraso.

```qsharp
operation DelayA<'T> (op : ('T => Unit is Adj), arg : 'T, aux : Unit) : Unit
```


## <a name="description"></a>Descrição

Dada a operação e uma entrada para essa operação, aplica a operação assim que for fornecida uma entrada adicional.
Em particular, a expressão `Delay(op, arg, _)` é uma operação que se aplica `op` quando é `arg` chamada.
A expressão `Delay(op,arg,_)` permite atrasar a aplicação de `op` .

## <a name="input"></a>Entrada

### <a name="op--t--unit-adj"></a>op : 'T = [Unit](xref:microsoft.quantum.lang-ref.unit) unidade> Adj

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