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
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="30a24-102">UnivariateOptimizaçãoResult tipo definido pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="30a24-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="30a24-103">Espaço de nome: [Microsoft.Quantum.Otimização](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="30a24-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="30a24-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="30a24-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="30a24-105">Representa o resultado da otimização de uma função univariada.</span><span class="sxs-lookup"><span data-stu-id="30a24-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="30a24-106">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="30a24-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="30a24-107">Coordenada : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="30a24-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="30a24-108">Entrada na qual foi encontrado um ideal.</span><span class="sxs-lookup"><span data-stu-id="30a24-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="30a24-109">Valor : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="30a24-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="30a24-110">Valor devolvido pela função no seu melhor.</span><span class="sxs-lookup"><span data-stu-id="30a24-110">Value returned by the function at its optimum.</span></span>