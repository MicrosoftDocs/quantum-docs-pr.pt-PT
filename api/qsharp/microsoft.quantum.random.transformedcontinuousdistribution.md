---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: Função de distribuição dedestribuição dedesemcontinuas transformada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: b317eaaa0ff0180ea5d240464c96d1c6b59c9c70
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226269"
---
# <a name="transformedcontinuousdistribution-function"></a>Função de distribuição dedestribuição dedesemcontinuas transformada

Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Dada uma distribuição contínua, devolve uma nova distribuição que transforma o original por uma determinada função.

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>Entrada

### <a name="transform--double---double"></a>transformar : [Duplo](xref:microsoft.quantum.lang-ref.double) -> [Duplo](xref:microsoft.quantum.lang-ref.double)

Uma função que transforma variações da distribuição original à distribuição transformada.


### <a name="distribution--continuousdistribution"></a>distribuição : [Distribuição contínua](xref:Microsoft.Quantum.Random.ContinuousDistribution)

A distribuição original a ser transformada.



## <a name="output--continuousdistribution"></a>Saída : [Distribuição contínua](xref:Microsoft.Quantum.Random.ContinuousDistribution)

Uma nova distribuição relacionada com `distribution` a transformação dada `transform` por.