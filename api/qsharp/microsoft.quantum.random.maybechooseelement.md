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
# <a name="maybechooseelement-operation"></a><span data-ttu-id="6c881-102">Talvez a operaçãoChooseElement</span><span class="sxs-lookup"><span data-stu-id="6c881-102">MaybeChooseElement operation</span></span>

<span data-ttu-id="6c881-103">Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="6c881-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="6c881-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6c881-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6c881-105">Dada uma série de dados e uma distribuição sobre os seus índices, tenta escolher um elemento ao acaso.</span><span class="sxs-lookup"><span data-stu-id="6c881-105">Given an array of data and an a distribution over its indices, attempts to choose an element at random.</span></span>

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a><span data-ttu-id="6c881-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6c881-106">Input</span></span>

### <a name="data--t"></a><span data-ttu-id="6c881-107">dados : 'T[]</span><span class="sxs-lookup"><span data-stu-id="6c881-107">data : 'T[]</span></span>

<span data-ttu-id="6c881-108">A matriz a partir da qual um elemento deve ser escolhido.</span><span class="sxs-lookup"><span data-stu-id="6c881-108">The array from which an element should be chosen.</span></span>


### <a name="indexdistribution--discretedistribution"></a><span data-ttu-id="6c881-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="6c881-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="6c881-110">Uma distribuição sobre os índices `data` de.</span><span class="sxs-lookup"><span data-stu-id="6c881-110">A distribution over the indices of `data`.</span></span>



## <a name="output--boolt"></a><span data-ttu-id="6c881-111">Saída :[(Bool](xref:microsoft.quantum.lang-ref.bool),'T)</span><span class="sxs-lookup"><span data-stu-id="6c881-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6c881-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="6c881-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6c881-113">'T</span><span class="sxs-lookup"><span data-stu-id="6c881-113">'T</span></span>

