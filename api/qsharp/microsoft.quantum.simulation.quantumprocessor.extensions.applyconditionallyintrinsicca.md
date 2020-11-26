---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsicCA
title: Aplicar operação CÍtrina Desmedida
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsicCA
qsharp.summary: ''
ms.openlocfilehash: 2dd7a9b6e281c62470defa64685dc58872694468
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230196"
---
# <a name="applyconditionallyintrinsicca-operation"></a>Aplicar operação CÍtrina Desmedida

Espaço de nome: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)




```qsharp
operation ApplyConditionallyIntrinsicCA (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit is Ctl + Adj), onNonEqualOp : (Unit => Unit is Ctl + Adj)) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="measurementresults--__invalidresult__"></a>medidasResultos: __inválido <Result>__[]




### <a name="resultsvalues--__invalidresult__"></a>resultados Valores: __inválido <Result>__[]




### <a name="onequalop--unit--unit--is-adj--ctl"></a>onEqualOp [Unit](xref:microsoft.quantum.lang-ref.unit) : => [Unidade](xref:microsoft.quantum.lang-ref.unit) unidade é Adj + Ctl




### <a name="onnonequalop--unit--unit--is-adj--ctl"></a>onNonEqualOp : [Unidade](xref:microsoft.quantum.lang-ref.unit) unidade é => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl





## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

