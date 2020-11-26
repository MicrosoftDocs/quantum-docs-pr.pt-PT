---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: Operação de Qualificação de Estimativas
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: 9d127bba9624e178fbdb631a1249efe5fc2be3b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196468"
---
# <a name="estimateclassificationprobability-operation"></a><span data-ttu-id="ea4bb-102">Operação de Qualificação de Estimativas</span><span class="sxs-lookup"><span data-stu-id="ea4bb-102">EstimateClassificationProbability operation</span></span>

<span data-ttu-id="ea4bb-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="ea4bb-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="ea4bb-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="ea4bb-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="ea4bb-105">Dada uma amostra e um classificador sequencial, estima a probabilidade de classificação dessa amostra medindo repetidamente a saída do classificador na amostra dada.</span><span class="sxs-lookup"><span data-stu-id="ea4bb-105">Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.</span></span>

```qsharp
operation EstimateClassificationProbability (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, sample : Double[], nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="ea4bb-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ea4bb-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="ea4bb-107">tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ea4bb-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ea4bb-108">A tolerância para permitir a codificação da amostra numa operação de preparação do Estado.</span><span class="sxs-lookup"><span data-stu-id="ea4bb-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="ea4bb-109">modelo : [SequencialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="ea4bb-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="ea4bb-110">O modelo sequencial a utilizar para estimar a probabilidade de classificação para a amostra dada.</span><span class="sxs-lookup"><span data-stu-id="ea4bb-110">The sequential model to be used to estimate the classification probability for the given sample.</span></span>


### <a name="sample--double"></a><span data-ttu-id="ea4bb-111">amostra : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="ea4bb-111">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="ea4bb-112">O vetor de recurso para a amostra ser classificado.</span><span class="sxs-lookup"><span data-stu-id="ea4bb-112">The feature vector for the sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="ea4bb-113">n Medidas : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ea4bb-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ea4bb-114">O número de medições a utilizar na estimativa da probabilidade de classificação.</span><span class="sxs-lookup"><span data-stu-id="ea4bb-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="ea4bb-115">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ea4bb-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ea4bb-116">Uma estimativa da probabilidade de classificação para a amostra dada.</span><span class="sxs-lookup"><span data-stu-id="ea4bb-116">An estimate of the classification probability for the given sample.</span></span>