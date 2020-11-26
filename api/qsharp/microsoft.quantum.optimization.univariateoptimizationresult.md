---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizaçãoResult tipo definido pelo utilizador
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: 0bcdbda5586181f965297cb2a398d766f9c6fabb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194037"
---
# <a name="univariateoptimizationresult-user-defined-type"></a>UnivariateOptimizaçãoResult tipo definido pelo utilizador

Espaço de nome: [Microsoft.Quantum.Otimização](xref:Microsoft.Quantum.Optimization)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa o resultado da otimização de uma função univariada.

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a>Itens nomeados

### <a name="coordinate--double"></a>Coordenada : [Duplo](xref:microsoft.quantum.lang-ref.double)

Entrada na qual foi encontrado um ideal.
### <a name="value--double"></a>Valor : [Duplo](xref:microsoft.quantum.lang-ref.double)

Valor devolvido pela função no seu melhor.