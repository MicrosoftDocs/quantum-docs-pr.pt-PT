---
uid: Microsoft.Quantum.Canon.ApplyIfZeroCA
title: Aplicação OperaçãoIfZeroCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being zero.
ms.openlocfilehash: 4baae1fe7d615cbbf01935b4eca05fe947ff296e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218466"
---
# <a name="applyifzeroca-operation"></a>Aplicação OperaçãoIfZeroCA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma operação unitária condicionada a um valor de resultado clássico ser zero.

```qsharp
operation ApplyIfZeroCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Dada a operação `op` e o valor do `result` resultado, aplica-se `op` ao se é `target` `result` `Zero` . Se, `One` nada acontecer ao `target` .
O `CA` sufixo indica que a operação a aplicar é unitária (controlável e adjacente).

## <a name="input"></a>Entrada

### <a name="result--__invalidresult__"></a>resultado : __inválido <Result>__

Um resultado de medição que controla se a operação é aplicada ou não.


### <a name="op--t--unit--is-adj--ctl"></a>op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl

Uma operação a ser aplicada condicionalmente.


### <a name="target--t"></a>alvo : 'T

A entrada à qual a operação é aplicada.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo de entrada da operação a aplicar condicionalmente.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyIfZeroC](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [Microsoft.Quantum.Canon.ApplyIfZeroA](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [Microsoft.Quantum.Canon.ApplyIfZeroCA](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)