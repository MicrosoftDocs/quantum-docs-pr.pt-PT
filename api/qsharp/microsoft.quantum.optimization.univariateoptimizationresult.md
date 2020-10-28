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
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="98599-102">UnivariateOptimizaçãoResult tipo definido pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="98599-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="98599-103">Espaço de nome: [Microsoft.Quantum.Otimização](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="98599-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="98599-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="98599-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="98599-105">Representa o resultado da otimização de uma função univariada.</span><span class="sxs-lookup"><span data-stu-id="98599-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="98599-106">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="98599-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="98599-107">Coordenada : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="98599-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="98599-108">Entrada na qual foi encontrado um ideal.</span><span class="sxs-lookup"><span data-stu-id="98599-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="98599-109">Valor : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="98599-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="98599-110">Valor devolvido pela função no seu melhor.</span><span class="sxs-lookup"><span data-stu-id="98599-110">Value returned by the function at its optimum.</span></span>