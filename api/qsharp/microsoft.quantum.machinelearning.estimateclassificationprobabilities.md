---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbabilities
title: Operação De Classificação de Estimativas
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbabilities
qsharp.summary: Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.
ms.openlocfilehash: eea503d042d6ffc241186c117a7c02ee72983b09
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847725"
---
# <a name="estimateclassificationprobabilities-operation"></a><span data-ttu-id="f4cb4-102">Operação De Classificação de Estimativas</span><span class="sxs-lookup"><span data-stu-id="f4cb4-102">EstimateClassificationProbabilities operation</span></span>

<span data-ttu-id="f4cb4-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="f4cb4-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="f4cb4-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="f4cb4-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="f4cb4-105">Dado um conjunto de amostras e um classificador sequencial, estima a probabilidade de classificação dessas amostras medindo repetidamente a saída do classificador em cada amostra.</span><span class="sxs-lookup"><span data-stu-id="f4cb4-105">Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.</span></span>

```qsharp
operation EstimateClassificationProbabilities (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Double[][], nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="f4cb4-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f4cb4-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="f4cb4-107">tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f4cb4-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f4cb4-108">A tolerância para permitir a codificação da amostra numa operação de preparação do Estado.</span><span class="sxs-lookup"><span data-stu-id="f4cb4-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="f4cb4-109">modelo : [SequencialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="f4cb4-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="f4cb4-110">O modelo sequencial a utilizar para estimar as probabilidades de classificação das amostras dadas.</span><span class="sxs-lookup"><span data-stu-id="f4cb4-110">The sequential model to be used to estimate the classification probabilities for the given samples.</span></span>


### <a name="samples--double"></a><span data-ttu-id="f4cb4-111">amostras : [Duplo](xref:microsoft.quantum.lang-ref.double)[][]</span><span class="sxs-lookup"><span data-stu-id="f4cb4-111">samples : [Double](xref:microsoft.quantum.lang-ref.double)[][]</span></span>

<span data-ttu-id="f4cb4-112">Uma variedade de vetores de características para cada amostra ser classificada.</span><span class="sxs-lookup"><span data-stu-id="f4cb4-112">An array of feature vectors for each sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="f4cb4-113">n Medidas : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f4cb4-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f4cb4-114">O número de medições a utilizar na estimativa da probabilidade de classificação.</span><span class="sxs-lookup"><span data-stu-id="f4cb4-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="f4cb4-115">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="f4cb4-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="f4cb4-116">Uma série de estimativas da probabilidade de classificação para cada amostra dada.</span><span class="sxs-lookup"><span data-stu-id="f4cb4-116">An array of estimates of the classification probability for each given sample.</span></span>