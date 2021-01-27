---
uid: Microsoft.Quantum.Random.NormalDistribution
title: Função NormalDistribution
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: NormalDistribution
qsharp.summary: Returns a normal distribution with a given mean and variance.
ms.openlocfilehash: 733a2763dca6d75f81d538f63c3084331a8e1d51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814176"
---
# <a name="normaldistribution-function"></a><span data-ttu-id="3a2df-102">Função NormalDistribution</span><span class="sxs-lookup"><span data-stu-id="3a2df-102">NormalDistribution function</span></span>

<span data-ttu-id="3a2df-103">Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="3a2df-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="3a2df-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="3a2df-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="3a2df-105">Devolve uma distribuição normal com uma média e variação.</span><span class="sxs-lookup"><span data-stu-id="3a2df-105">Returns a normal distribution with a given mean and variance.</span></span>

```qsharp
function NormalDistribution (mean : Double, variance : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="3a2df-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3a2df-106">Input</span></span>

### <a name="mean--double"></a><span data-ttu-id="3a2df-107">média : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3a2df-107">mean : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="variance--double"></a><span data-ttu-id="3a2df-108">variação : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3a2df-108">variance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--continuousdistribution"></a><span data-ttu-id="3a2df-109">Saída : [Distribuição contínua](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="3a2df-109">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>



## <a name="example"></a><span data-ttu-id="3a2df-110">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3a2df-110">Example</span></span>

<span data-ttu-id="3a2df-111">Os seguintes recolhem 10 amostras da distribuição normal com a média 2 e o desvio padrão 0.1:</span><span class="sxs-lookup"><span data-stu-id="3a2df-111">The following draws 10 samples from the normal distribution with mean 2 and standard deviation 0.1:</span></span>

```qsharp
let samples = DrawMany(
    (NormalDistribution(2.0, PowD(0.1, 2.0)))::Sample,
    10, ()
);
```

## <a name="see-also"></a><span data-ttu-id="3a2df-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3a2df-112">See Also</span></span>

- [<span data-ttu-id="3a2df-113">Microsoft.Quantum.Random.StandardNormalDistribution</span><span class="sxs-lookup"><span data-stu-id="3a2df-113">Microsoft.Quantum.Random.StandardNormalDistribution</span></span>](xref:Microsoft.Quantum.Random.StandardNormalDistribution)