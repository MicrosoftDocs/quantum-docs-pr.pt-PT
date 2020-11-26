---
uid: Microsoft.Quantum.Canon.ApplyIfZeroA
title: Aplicação OperaçãoIfZeroA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being zero.
ms.openlocfilehash: ab5b05791213da7c8bee5915764c342cb0bed851
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218500"
---
# <a name="applyifzeroa-operation"></a>Aplicação OperaçãoIfZeroA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma operação contígua condicionada a um valor de resultado clássico sendo zero.

```qsharp
operation ApplyIfZeroA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit is Adj
```


## <a name="description"></a>Description

Dada a operação `op` e o valor do `result` resultado, aplica-se `op` ao se é `target` `result` `Zero` . Se, `One` nada acontecer ao `target` .
O `A` sufixo indica que a operação a aplicar é adjacente.

## <a name="input"></a>Entrada

### <a name="result--__invalidresult__"></a>resultado : __inválido <Result>__

Um resultado de medição que controla se a operação é aplicada ou não.


### <a name="op--t--unit--is-adj"></a>op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj

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