---
uid: Microsoft.Quantum.Canon.ApplyIfOneCA
title: AplicarIfOneCA operação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being one.
ms.openlocfilehash: 973dd3c5f9f3e9ad03c0626a38779f499b7ce657
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718070"
---
# <a name="applyifoneca-operation"></a>AplicarIfOneCA operação

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Aplica uma operação unitária condicionada a um valor de resultado clássico sendo um.

```qsharp
operation ApplyIfOneCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit
```


## <a name="description"></a>Descrição

Dada a operação `op` e o valor do `result` resultado, aplica-se `op` ao se é `target` `result` `One` . Se, `Zero` nada acontecer ao `target` .
O `CA` sufixo indica que a operação a aplicar é unitária (controlável e adjacente).

## <a name="input"></a>Entrada

### <a name="result--__invalidresult__"></a>resultado : __inválido <Result>__

Um resultado de medição que controla se a operação é aplicada ou não.


### <a name="op--t--unit-adj--ctl"></a>op : 'T => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl

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