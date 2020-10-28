---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizaçãoResult tipo definido pelo utilizador
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: c8aa91bbdc9e9e9bb4d110b470ff2041f9460a38
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724321"
---
# <a name="univariateoptimizationresult-user-defined-type"></a>UnivariateOptimizaçãoResult tipo definido pelo utilizador

Espaço de nome: [Microsoft.Quantum.Otimização](xref:Microsoft.Quantum.Optimization)

Pacote: [](https://nuget.org/packages/)


Representa o resultado da otimização de uma função univariada.

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a>Itens nomeados

### <a name="coordinate--double"></a>Coordenada : [Duplo](xref:microsoft.quantum.lang-ref.double)

Entrada na qual foi encontrado um ideal.
### <a name="value--double"></a>Valor : [Duplo](xref:microsoft.quantum.lang-ref.double)

Valor devolvido pela função no seu melhor.