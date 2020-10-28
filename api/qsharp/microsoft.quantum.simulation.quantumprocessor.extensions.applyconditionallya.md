---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyA
title: Aplicar operaçãoConditionalA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyA
qsharp.summary: ''
ms.openlocfilehash: b6f7e7d6d51e531b0ec9e7e4f2f5772038421933
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710527"
---
# <a name="applyconditionallya-operation"></a>Aplicar operaçãoConditionalA

Espaço de nome: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Pacote: [](https://nuget.org/packages/)




```qsharp
operation ApplyConditionallyA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Adj), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a>Entrada

### <a name="measurementresults--__invalidresult__"></a>medidasResultos: __inválido <Result>__ []




### <a name="resultsvalues--__invalidresult__"></a>resultados Valores: __inválido <Result>__ []




### <a name="onequalop--t--unit-adj"></a>onEqualOp : 'T = [Unit](xref:microsoft.quantum.lang-ref.unit) unidade> Adj




### <a name="equalarg--t"></a>equalArg : 'T




### <a name="onnonequalop--u--unit-adj"></a>onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj




### <a name="nonequalarg--u"></a>nonEqualArg : 'U





## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T


### <a name="u"></a>'U

