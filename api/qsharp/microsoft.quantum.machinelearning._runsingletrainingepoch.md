---
uid: Microsoft.Quantum.MachineLearning._RunSingleTrainingEpoch
title: operação _RunSingleTrainingEpoch
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _RunSingleTrainingEpoch
qsharp.summary: Perform one epoch of sequential classifier training on a subset of data samples.
ms.openlocfilehash: a8ae35fdd6c4e219444e7d6f7587ea31603b9999
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856191"
---
# <a name="_runsingletrainingepoch-operation"></a><span data-ttu-id="88ead-102">operação _RunSingleTrainingEpoch</span><span class="sxs-lookup"><span data-stu-id="88ead-102">_RunSingleTrainingEpoch operation</span></span>

<span data-ttu-id="88ead-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="88ead-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="88ead-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="88ead-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="88ead-105">Realizar uma época de treino de classificador sequencial num subconjunto de amostras de dados.</span><span class="sxs-lookup"><span data-stu-id="88ead-105">Perform one epoch of sequential classifier training on a subset of data samples.</span></span>

```qsharp
operation _RunSingleTrainingEpoch (encodedSamples : (Microsoft.Quantum.MachineLearning.LabeledSample, Microsoft.Quantum.MachineLearning.StateGenerator)[], schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, periodScore : Int, options : Microsoft.Quantum.MachineLearning.TrainingOptions, model : Microsoft.Quantum.MachineLearning.SequentialModel, nPreviousBestMisses : Int) : (Int, Microsoft.Quantum.MachineLearning.SequentialModel)
```


## <a name="input"></a><span data-ttu-id="88ead-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="88ead-106">Input</span></span>

### <a name="encodedsamples--labeledsamplestategenerator"></a><span data-ttu-id="88ead-107">quartos codificados :[(LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator))[]</span><span class="sxs-lookup"><span data-stu-id="88ead-107">encodedSamples : ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator))[]</span></span>




### <a name="schedule--samplingschedule"></a><span data-ttu-id="88ead-108">calendário : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="88ead-108">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>




### <a name="periodscore--int"></a><span data-ttu-id="88ead-109">periodScore : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="88ead-109">periodScore : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="88ead-110">O número de passos de gradiente a tomar entre pontos de pontuação.</span><span class="sxs-lookup"><span data-stu-id="88ead-110">The number of gradient steps to be taken between scoring points.</span></span>
<span data-ttu-id="88ead-111">Para obter a melhor precisão, desa um.</span><span class="sxs-lookup"><span data-stu-id="88ead-111">For best accuracy, set to 1.</span></span>


### <a name="options--trainingoptions"></a><span data-ttu-id="88ead-112">opções : [Opções de Formação](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="88ead-112">options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="88ead-113">Opções a serem usadas no treino.</span><span class="sxs-lookup"><span data-stu-id="88ead-113">Options to be used in training.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="88ead-114">modelo : [SequencialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="88ead-114">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="88ead-115">O modelo sequencial a ser treinado.</span><span class="sxs-lookup"><span data-stu-id="88ead-115">The sequential model to be trained.</span></span>


### <a name="npreviousbestmisses--int"></a><span data-ttu-id="88ead-116">nPreviousBestMisses : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="88ead-116">nPreviousBestMisses : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="88ead-117">O melhor número de classificações erradas observadas em épocas anteriores.</span><span class="sxs-lookup"><span data-stu-id="88ead-117">The best number of misclassifications observed in previous epochs.</span></span>



## <a name="output--intsequentialmodel"></a><span data-ttu-id="88ead-118">Saída : ([Int,](xref:microsoft.quantum.lang-ref.int)[SequencialModel)](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="88ead-118">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))</span></span>

- <span data-ttu-id="88ead-119">O menor número de desclassificações observadas nesta época.</span><span class="sxs-lookup"><span data-stu-id="88ead-119">The smallest number of misclassifications observed through to this epoch.</span></span>
- <span data-ttu-id="88ead-120">O novo melhor modelo sequencial encontrado.</span><span class="sxs-lookup"><span data-stu-id="88ead-120">The new best sequential model found.</span></span>