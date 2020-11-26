---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyC
title: Aplicar operaçãoConditionalC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyC
qsharp.summary: ''
ms.openlocfilehash: 963a85e0e442592c01a2e70fa0dc02d6048d8be7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229040"
---
# <a name="applyconditionallyc-operation"></a>Aplicar operaçãoConditionalC

Espaço de nome: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)




```qsharp
operation ApplyConditionallyC<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl), nonEqualArg : 'U)) : Unit is Ctl
```


## <a name="input"></a>Entrada

### <a name="measurementresults--__invalidresult__"></a>medidasResultos: __inválido <Result>__[]




### <a name="resultsvalues--__invalidresult__"></a>resultados Valores: __inválido <Result>__[]




### <a name="onequalop--t--unit--is-ctl"></a>onEqualOp : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é CTL




### <a name="equalarg--t"></a>equalArg : 'T




### <a name="onnonequalop--u--unit--is-ctl"></a>onNonEqualOp : 'U = [> Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl




### <a name="nonequalarg--u"></a>nonEqualArg : 'U





## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T


### <a name="u"></a>'U

