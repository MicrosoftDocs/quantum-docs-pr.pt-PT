---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: Operação EstimativaGradient
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: 79f4abdf131509d4948a3c114e631118329f88d8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211853"
---
# <a name="estimategradient-operation"></a><span data-ttu-id="c8b8b-102">Operação EstimativaGradient</span><span class="sxs-lookup"><span data-stu-id="c8b8b-102">EstimateGradient operation</span></span>

<span data-ttu-id="c8b8b-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c8b8b-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="c8b8b-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c8b8b-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="c8b8b-105">Estima o gradiente de formação para um classificador sequencial num determinado modelo e para uma determinada entrada codificada.</span><span class="sxs-lookup"><span data-stu-id="c8b8b-105">Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.</span></span>

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="c8b8b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c8b8b-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="c8b8b-107">modelo : [SequencialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="c8b8b-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="c8b8b-108">O modelo sequencial cujo gradiente deve ser estimado.</span><span class="sxs-lookup"><span data-stu-id="c8b8b-108">The sequential model whose gradient is to be estimated.</span></span>


### <a name="encodedinput--stategenerator"></a><span data-ttu-id="c8b8b-109">incodedInput : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="c8b8b-109">encodedInput : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="c8b8b-110">Uma entrada para o classificador sequencial, codificada numa operação de preparação do estado.</span><span class="sxs-lookup"><span data-stu-id="c8b8b-110">An input to the sequential classifier, encoded into a state preparation operation.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="c8b8b-111">n Medidas : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c8b8b-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c8b8b-112">O número de medições a utilizar na estimativa do gradiente.</span><span class="sxs-lookup"><span data-stu-id="c8b8b-112">The number of measurements to use in estimating the gradient.</span></span>



## <a name="output--double"></a><span data-ttu-id="c8b8b-113">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="c8b8b-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="c8b8b-114">Uma estimativa do gradiente de formação nos parâmetros de entrada e modelo dados.</span><span class="sxs-lookup"><span data-stu-id="c8b8b-114">An estimate of the training gradient at the given input and model parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="c8b8b-115">Observações</span><span class="sxs-lookup"><span data-stu-id="c8b8b-115">Remarks</span></span>

<span data-ttu-id="c8b8b-116">Esta operação utiliza um teste Hadamard e a técnica de mudança de parâmetros em conjunto para estimar o gradiente.</span><span class="sxs-lookup"><span data-stu-id="c8b8b-116">This operation uses a Hadamard test and the parameter shift technique together to estimate the gradient.</span></span>