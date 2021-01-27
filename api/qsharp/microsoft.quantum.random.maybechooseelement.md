---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: Talvez a operaçãoChooseElement
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 86a69110fc92a2b6238cc757c09185c9fbcdb035
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856120"
---
# <a name="maybechooseelement-operation"></a>Talvez a operaçãoChooseElement

Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Dada uma série de dados e uma distribuição sobre os seus índices, tenta escolher um elemento ao acaso.

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a>Entrada

### <a name="data--t"></a>dados : 'T[]

A matriz a partir da qual um elemento deve ser escolhido.


### <a name="indexdistribution--discretedistribution"></a>indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

Uma distribuição sobre os índices `data` de.



## <a name="output--boolt"></a>Saída :[(Bool](xref:microsoft.quantum.lang-ref.bool),'T)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T



## <a name="example"></a>Exemplo

O seguinte corte Q# escolhe um elemento aleatoriamente a partir de uma matriz:

```qsharp
let (succeeded, element) = MaybeChooseElement(
    data,
    DiscreteUniformDistribution(0, Length(data) - 1)
);
Fact(succeeded, "Index chosen by MaybeChooseElement was not valid.");
```