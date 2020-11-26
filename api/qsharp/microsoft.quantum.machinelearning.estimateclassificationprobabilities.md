---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbabilities
title: Operação De Classificação de Estimativas
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbabilities
qsharp.summary: Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.
ms.openlocfilehash: 1cd56f6a6483b00afb168f8d84301e73eae9af65
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211904"
---
# <a name="estimateclassificationprobabilities-operation"></a><span data-ttu-id="c3dcd-102">Operação De Classificação de Estimativas</span><span class="sxs-lookup"><span data-stu-id="c3dcd-102">EstimateClassificationProbabilities operation</span></span>

<span data-ttu-id="c3dcd-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c3dcd-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="c3dcd-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c3dcd-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="c3dcd-105">Dado um conjunto de amostras e um classificador sequencial, estima a probabilidade de classificação dessas amostras medindo repetidamente a saída do classificador em cada amostra.</span><span class="sxs-lookup"><span data-stu-id="c3dcd-105">Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.</span></span>

```qsharp
operation EstimateClassificationProbabilities (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Double[][], nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="c3dcd-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c3dcd-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="c3dcd-107">tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c3dcd-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c3dcd-108">A tolerância para permitir a codificação da amostra numa operação de preparação do Estado.</span><span class="sxs-lookup"><span data-stu-id="c3dcd-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="c3dcd-109">modelo : [SequencialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="c3dcd-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="c3dcd-110">O modelo sequencial a utilizar para estimar as probabilidades de classificação das amostras dadas.</span><span class="sxs-lookup"><span data-stu-id="c3dcd-110">The sequential model to be used to estimate the classification probabilities for the given samples.</span></span>


### <a name="samples--double"></a><span data-ttu-id="c3dcd-111">amostras : [Duplo](xref:microsoft.quantum.lang-ref.double)[][]</span><span class="sxs-lookup"><span data-stu-id="c3dcd-111">samples : [Double](xref:microsoft.quantum.lang-ref.double)[][]</span></span>

<span data-ttu-id="c3dcd-112">Uma variedade de vetores de características para cada amostra ser classificada.</span><span class="sxs-lookup"><span data-stu-id="c3dcd-112">An array of feature vectors for each sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="c3dcd-113">n Medidas : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c3dcd-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c3dcd-114">O número de medições a utilizar na estimativa da probabilidade de classificação.</span><span class="sxs-lookup"><span data-stu-id="c3dcd-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="c3dcd-115">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="c3dcd-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="c3dcd-116">Uma série de estimativas da probabilidade de classificação para cada amostra dada.</span><span class="sxs-lookup"><span data-stu-id="c3dcd-116">An array of estimates of the classification probability for each given sample.</span></span>