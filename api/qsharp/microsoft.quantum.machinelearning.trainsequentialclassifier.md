---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifier
title: Operação TrainSequentialClassifier
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifier
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set.
ms.openlocfilehash: 12c4df59941b682d9de798e6585b59d1c34924dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711308"
---
# <a name="trainsequentialclassifier-operation"></a><span data-ttu-id="02364-102">Operação TrainSequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="02364-102">TrainSequentialClassifier operation</span></span>

<span data-ttu-id="02364-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="02364-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="02364-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="02364-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="02364-105">Dada a estrutura de um classificador sequencial, treina o classificador num determinado conjunto de treino rotulado.</span><span class="sxs-lookup"><span data-stu-id="02364-105">Given the structure of a sequential classifier, trains the classifier on a given labeled training set.</span></span>

```qsharp
operation TrainSequentialClassifier (models : Microsoft.Quantum.MachineLearning.SequentialModel[], samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a><span data-ttu-id="02364-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="02364-106">Input</span></span>

### <a name="models--sequentialmodel"></a><span data-ttu-id="02364-107">modelos : [SequencialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)[]</span><span class="sxs-lookup"><span data-stu-id="02364-107">models : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)[]</span></span>

<span data-ttu-id="02364-108">Uma série de modelos a utilizar como pontos de partida durante o treino.</span><span class="sxs-lookup"><span data-stu-id="02364-108">An array of models to be used as starting points during training.</span></span>


### <a name="samples--labeledsample"></a><span data-ttu-id="02364-109">amostras : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span><span class="sxs-lookup"><span data-stu-id="02364-109">samples : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span></span>

<span data-ttu-id="02364-110">Um conjunto de dados de formação rotulados que serão utilizados para realizar treinos.</span><span class="sxs-lookup"><span data-stu-id="02364-110">A set of labeled training data that will be used to perform training.</span></span>


### <a name="options--trainingoptions"></a><span data-ttu-id="02364-111">opções : [Opções de Formação](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="02364-111">options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="02364-112">Configuração a utilizar durante o treino; ver @"microsoft.quantum.machinelearning.trainingoptions" e para mais @"microsoft.quantum.machinelearning.defaulttrainingoptions" detalhes.</span><span class="sxs-lookup"><span data-stu-id="02364-112">Configuration to be used when training; see @"microsoft.quantum.machinelearning.trainingoptions" and @"microsoft.quantum.machinelearning.defaulttrainingoptions" for more details.</span></span>


### <a name="trainingschedule--samplingschedule"></a><span data-ttu-id="02364-113">trainingSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="02364-113">trainingSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="02364-114">Um calendário de amostragem a utilizar ao selecionar amostras dos dados de treino durante as etapas de treino.</span><span class="sxs-lookup"><span data-stu-id="02364-114">A sampling schedule to use when selecting samples from the training data during training steps.</span></span>


### <a name="validationschedule--samplingschedule"></a><span data-ttu-id="02364-115">validaçãoSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="02364-115">validationSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="02364-116">Um calendário de amostragem a utilizar ao selecionar amostras dos dados de treino ao selecionar qual ponto de partida resultou na melhor pontuação do classificador.</span><span class="sxs-lookup"><span data-stu-id="02364-116">A sampling schedule to use when selecting samples from the training data when selecting which start point resulted in the best classifier score.</span></span>



## <a name="output--sequentialmodelint"></a><span data-ttu-id="02364-117">Saída : ([SequencialModel,](xref:Microsoft.Quantum.MachineLearning.SequentialModel)[Int)](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="02364-117">Output : ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

- <span data-ttu-id="02364-118">Uma parametrização do classificador dado e um enviesamento entre as duas classes, correspondente ao melhor resultado de cada um dos pontos de partida dados.</span><span class="sxs-lookup"><span data-stu-id="02364-118">A parameterization of the given classifier and a bias between the two classes, together corresponding to the best result from each of the given start points.</span></span>
- <span data-ttu-id="02364-119">O número de falhas observadas no melhor modelo de classificador.</span><span class="sxs-lookup"><span data-stu-id="02364-119">The number of misses observed at the best classifier model.</span></span>

## <a name="see-also"></a><span data-ttu-id="02364-120">Consulte também</span><span class="sxs-lookup"><span data-stu-id="02364-120">See Also</span></span>

- [<span data-ttu-id="02364-121">Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel</span><span class="sxs-lookup"><span data-stu-id="02364-121">Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel</span></span>](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel)
- [<span data-ttu-id="02364-122">Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="02364-122">Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier</span></span>](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)