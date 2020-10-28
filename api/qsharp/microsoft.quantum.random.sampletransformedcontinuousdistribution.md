---
uid: Microsoft.Quantum.Random.SampleTransformedContinuousDistribution
title: AmostraTransformeOperação de distribuição dedesdistribuição
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: SampleTransformedContinuousDistribution
qsharp.summary: Internal-only operation for sampling from transformed distributions. Should only be used via partial application.
ms.openlocfilehash: dc93022e53199cd8ef794da9c1590d6997a0fda1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723971"
---
# <a name="sampletransformedcontinuousdistribution-operation"></a><span data-ttu-id="35d04-102">AmostraTransformeOperação de distribuição dedesdistribuição</span><span class="sxs-lookup"><span data-stu-id="35d04-102">SampleTransformedContinuousDistribution operation</span></span>

<span data-ttu-id="35d04-103">Espaço de nome: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="35d04-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="35d04-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="35d04-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="35d04-105">Operação interna apenas para amostragem a partir de distribuição transformada.</span><span class="sxs-lookup"><span data-stu-id="35d04-105">Internal-only operation for sampling from transformed distributions.</span></span>
<span data-ttu-id="35d04-106">Só deve ser utilizado através de uma aplicação parcial.</span><span class="sxs-lookup"><span data-stu-id="35d04-106">Should only be used via partial application.</span></span>

```qsharp
operation SampleTransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Double
```


## <a name="input"></a><span data-ttu-id="35d04-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="35d04-107">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="35d04-108">transformar : [Duplo](xref:microsoft.quantum.lang-ref.double) -> [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="35d04-108">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="distribution--continuousdistribution"></a><span data-ttu-id="35d04-109">distribuição : [Distribuição contínua](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="35d04-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>





## <a name="output--double"></a><span data-ttu-id="35d04-110">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="35d04-110">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

