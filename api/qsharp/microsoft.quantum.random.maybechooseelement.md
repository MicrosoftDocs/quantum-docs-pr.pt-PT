---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: Talvez a operaçãoChooseElement
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 12640d9dc3aad301146eff7bcbbaae33d3ccd420
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722165"
---
# <a name="maybechooseelement-operation"></a>Talvez a operaçãoChooseElement

Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)

Pacote: [](https://nuget.org/packages/)


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

