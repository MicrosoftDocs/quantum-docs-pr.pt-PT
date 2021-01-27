---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyC
title: Aplicar operaçãoConditionalC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyC
qsharp.summary: ''
ms.openlocfilehash: 09496d384a70fa9fb6826304ce9909034297a118
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847860"
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

