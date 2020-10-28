---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: Operação de Qualificação de Estimativas
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: 79e40bc4bc0954dc6742307122609950bf22ec71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709771"
---
# <a name="estimateclassificationprobability-operation"></a><span data-ttu-id="53af6-102">Operação de Qualificação de Estimativas</span><span class="sxs-lookup"><span data-stu-id="53af6-102">EstimateClassificationProbability operation</span></span>

<span data-ttu-id="53af6-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="53af6-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="53af6-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="53af6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="53af6-105">Dada uma amostra e um classificador sequencial, estima a probabilidade de classificação dessa amostra medindo repetidamente a saída do classificador na amostra dada.</span><span class="sxs-lookup"><span data-stu-id="53af6-105">Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.</span></span>

```qsharp
operation EstimateClassificationProbability (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, sample : Double[], nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="53af6-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="53af6-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="53af6-107">tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="53af6-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="53af6-108">A tolerância para permitir a codificação da amostra numa operação de preparação do Estado.</span><span class="sxs-lookup"><span data-stu-id="53af6-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="53af6-109">modelo : [SequencialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="53af6-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="53af6-110">O modelo sequencial a utilizar para estimar a probabilidade de classificação para a amostra dada.</span><span class="sxs-lookup"><span data-stu-id="53af6-110">The sequential model to be used to estimate the classification probability for the given sample.</span></span>


### <a name="sample--double"></a><span data-ttu-id="53af6-111">amostra : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="53af6-111">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="53af6-112">O vetor de recurso para a amostra ser classificado.</span><span class="sxs-lookup"><span data-stu-id="53af6-112">The feature vector for the sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="53af6-113">n Medidas : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="53af6-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="53af6-114">O número de medições a utilizar na estimativa da probabilidade de classificação.</span><span class="sxs-lookup"><span data-stu-id="53af6-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="53af6-115">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="53af6-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="53af6-116">Uma estimativa da probabilidade de classificação para a amostra dada.</span><span class="sxs-lookup"><span data-stu-id="53af6-116">An estimate of the classification probability for the given sample.</span></span>