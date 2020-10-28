---
uid: Microsoft.Quantum.Canon.ApplyIfOneA
title: AplicarIfOneA operação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being one.
ms.openlocfilehash: 76c15aba6042c2801ecfe8470e82099c54ba3846
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718098"
---
# <a name="applyifonea-operation"></a>AplicarIfOneA operação

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Aplica uma operação contígua condicionada a um valor de resultado clássico sendo um.

```qsharp
operation ApplyIfOneA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit
```


## <a name="description"></a>Descrição

Dada a operação `op` e o valor do `result` resultado, aplica-se `op` ao se é `target` `result` `One` . Se, `Zero` nada acontecer ao `target` .
O `A` sufixo indica que a operação a aplicar é adjacente.

## <a name="input"></a>Entrada

### <a name="result--__invalidresult__"></a>resultado : __inválido <Result>__

Um resultado de medição que controla se a operação é aplicada ou não.


### <a name="op--t--unit-adj"></a>op : 'T = [Unit](xref:microsoft.quantum.lang-ref.unit) unidade> Adj

Uma operação a ser aplicada condicionalmente.


### <a name="target--t"></a>alvo : 'T

A entrada à qual a operação é aplicada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de entrada da operação a aplicar condicionalmente.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyIfOneC](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [Microsoft.Quantum.Canon.ApplyIfOnea](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [Microsoft.Quantum.Canon.ApplyIfOneCA](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)