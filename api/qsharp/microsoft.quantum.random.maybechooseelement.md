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
# <a name="maybechooseelement-operation"></a><span data-ttu-id="2098a-102">Talvez a operaçãoChooseElement</span><span class="sxs-lookup"><span data-stu-id="2098a-102">MaybeChooseElement operation</span></span>

<span data-ttu-id="2098a-103">Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="2098a-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="2098a-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="2098a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="2098a-105">Dada uma série de dados e uma distribuição sobre os seus índices, tenta escolher um elemento ao acaso.</span><span class="sxs-lookup"><span data-stu-id="2098a-105">Given an array of data and an a distribution over its indices, attempts to choose an element at random.</span></span>

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a><span data-ttu-id="2098a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2098a-106">Input</span></span>

### <a name="data--t"></a><span data-ttu-id="2098a-107">dados : 'T[]</span><span class="sxs-lookup"><span data-stu-id="2098a-107">data : 'T[]</span></span>

<span data-ttu-id="2098a-108">A matriz a partir da qual um elemento deve ser escolhido.</span><span class="sxs-lookup"><span data-stu-id="2098a-108">The array from which an element should be chosen.</span></span>


### <a name="indexdistribution--discretedistribution"></a><span data-ttu-id="2098a-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="2098a-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="2098a-110">Uma distribuição sobre os índices `data` de.</span><span class="sxs-lookup"><span data-stu-id="2098a-110">A distribution over the indices of `data`.</span></span>



## <a name="output--boolt"></a><span data-ttu-id="2098a-111">Saída :[(Bool](xref:microsoft.quantum.lang-ref.bool),'T)</span><span class="sxs-lookup"><span data-stu-id="2098a-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2098a-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="2098a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2098a-113">'T</span><span class="sxs-lookup"><span data-stu-id="2098a-113">'T</span></span>



## <a name="example"></a><span data-ttu-id="2098a-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="2098a-114">Example</span></span>

<span data-ttu-id="2098a-115">O seguinte corte Q# escolhe um elemento aleatoriamente a partir de uma matriz:</span><span class="sxs-lookup"><span data-stu-id="2098a-115">The following Q# snippet chooses an element at random from an array:</span></span>

```qsharp
let (succeeded, element) = MaybeChooseElement(
    data,
    DiscreteUniformDistribution(0, Length(data) - 1)
);
Fact(succeeded, "Index chosen by MaybeChooseElement was not valid.");
```