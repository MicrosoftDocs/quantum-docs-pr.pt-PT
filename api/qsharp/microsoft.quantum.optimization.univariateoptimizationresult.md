---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizaçãoResult tipo definido pelo utilizador
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: cc54c0035796aac86482e8a3a6896ceb197c7cfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854576"
---
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="788b6-102">UnivariateOptimizaçãoResult tipo definido pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="788b6-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="788b6-103">Espaço de nome: [Microsoft.Quantum.Otimização](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="788b6-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="788b6-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="788b6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="788b6-105">Representa o resultado da otimização de uma função univariada.</span><span class="sxs-lookup"><span data-stu-id="788b6-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="788b6-106">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="788b6-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="788b6-107">Coordenada : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="788b6-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="788b6-108">Entrada na qual foi encontrado um ideal.</span><span class="sxs-lookup"><span data-stu-id="788b6-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="788b6-109">Valor : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="788b6-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="788b6-110">Valor devolvido pela função no seu melhor.</span><span class="sxs-lookup"><span data-stu-id="788b6-110">Value returned by the function at its optimum.</span></span>