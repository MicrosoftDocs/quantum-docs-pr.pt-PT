---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionally
title: Aplicar operação condicional
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionally
qsharp.summary: ''
ms.openlocfilehash: fe623b240e35ee88f673b6e90db6307ef701d049
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710538"
---
# <a name="applyconditionally-operation"></a>Aplicar operação condicional

Espaço de nome: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Pacote: [](https://nuget.org/packages/)




```qsharp
operation ApplyConditionally<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit), equalArg : 'T), (onNonEqualOp : ('U => Unit), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a>Entrada

### <a name="measurementresults--__invalidresult__"></a>medidasResultos: __inválido <Result>__ []




### <a name="resultsvalues--__invalidresult__"></a>resultados Valores: __inválido <Result>__ []




### <a name="onequalop--t--unit"></a>onEqualOp : 'T = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 




### <a name="equalarg--t"></a>equalArg : 'T




### <a name="onnonequalop--u--unit"></a>onNonEqualOp : 'U = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 




### <a name="nonequalarg--u"></a>nonEqualArg : 'U





## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T


### <a name="u"></a>'U

