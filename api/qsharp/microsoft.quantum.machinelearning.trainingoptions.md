---
uid: Microsoft.Quantum.MachineLearning.TrainingOptions
title: FormaçãoOptions tipo definido pelo utilizador
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainingOptions
qsharp.summary: A collection of options to be used in training quantum classifiers.
ms.openlocfilehash: 280a3857aa7bc42f636a33f893d4f450e79b6a6a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196128"
---
# <a name="trainingoptions-user-defined-type"></a><span data-ttu-id="5d569-102">FormaçãoOptions tipo definido pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="5d569-102">TrainingOptions user defined type</span></span>

<span data-ttu-id="5d569-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="5d569-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="5d569-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="5d569-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="5d569-105">Uma coleção de opções a serem usadas no treino de classificadores quânticos.</span><span class="sxs-lookup"><span data-stu-id="5d569-105">A collection of options to be used in training quantum classifiers.</span></span>

```qsharp

newtype TrainingOptions = (LearningRate : Double, Tolerance : Double, MinibatchSize : Int, NMeasurements : Int, MaxEpochs : Int, MaxStalls : Int, StochasticRescaleFactor : Double, ScoringPeriod : Int, VerboseMessage : (String -> Unit));
```



## <a name="named-items"></a><span data-ttu-id="5d569-106">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="5d569-106">Named Items</span></span>

### <a name="learningrate--double"></a><span data-ttu-id="5d569-107">LearningRate : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5d569-107">LearningRate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5d569-108">A taxa de aprendizagem através da qual os gradientes devem ser redimensionados ao atualizar os parâmetros do modelo durante as etapas de treino.</span><span class="sxs-lookup"><span data-stu-id="5d569-108">The learning rate by which gradients should be rescaled when updating model parameters during training steps.</span></span>
### <a name="tolerance--double"></a><span data-ttu-id="5d569-109">Tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5d569-109">Tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5d569-110">A tolerância de aproximação a utilizar na preparação de amostras como estados quânticos.</span><span class="sxs-lookup"><span data-stu-id="5d569-110">The approximation tolerance to use when preparing samples as quantum states.</span></span>
### <a name="minibatchsize--int"></a><span data-ttu-id="5d569-111">MinibatchSize : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5d569-111">MinibatchSize : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5d569-112">O número de amostras a utilizar em cada minibatch de treino.</span><span class="sxs-lookup"><span data-stu-id="5d569-112">The number of samples to use in each training minibatch.</span></span>
### <a name="nmeasurements--int"></a><span data-ttu-id="5d569-113">NMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5d569-113">NMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5d569-114">O número de vezes para medir cada resultado de classificação para estimar a probabilidade de classificação.</span><span class="sxs-lookup"><span data-stu-id="5d569-114">The number of times to measure each classification result in order to estimate the classification probability.</span></span>
### <a name="maxepochs--int"></a><span data-ttu-id="5d569-115">MaxEpochs : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5d569-115">MaxEpochs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5d569-116">O número máximo de épocas para treinar cada modelo.</span><span class="sxs-lookup"><span data-stu-id="5d569-116">The maximum number of epochs to train each model for.</span></span>
### <a name="maxstalls--int"></a><span data-ttu-id="5d569-117">MaxStalls : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5d569-117">MaxStalls : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5d569-118">O número máximo de vezes que uma época de treino é permitida para parar (aproximadamente zero gradiente) antes de falhar.</span><span class="sxs-lookup"><span data-stu-id="5d569-118">The maximum number of times a training epoch is allowed to stall (approximately zero gradient) before failing.</span></span>
### <a name="stochasticrescalefactor--double"></a><span data-ttu-id="5d569-119">StochasticRescaleFactor : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5d569-119">StochasticRescaleFactor : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5d569-120">A quantidade para redimensionar os modelos paralisados antes de voltar a tentar uma atualização.</span><span class="sxs-lookup"><span data-stu-id="5d569-120">The amount to rescale stalled models by before retrying an update.</span></span>
### <a name="scoringperiod--int"></a><span data-ttu-id="5d569-121">PontuaçãoPeriod : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5d569-121">ScoringPeriod : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5d569-122">O número de passos de gradiente a tomar entre pontos de pontuação.</span><span class="sxs-lookup"><span data-stu-id="5d569-122">The number of gradient steps to be taken between scoring points.</span></span>
<span data-ttu-id="5d569-123">Para obter a melhor precisão, desa um.</span><span class="sxs-lookup"><span data-stu-id="5d569-123">For best accuracy, set to 1.</span></span>
### <a name="verbosemessage--string---unit"></a><span data-ttu-id="5d569-124">VerboseMessage : Unidade [de Cordas](xref:microsoft.quantum.lang-ref.string) -> [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5d569-124">VerboseMessage : [String](xref:microsoft.quantum.lang-ref.string) -> [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="5d569-125">Uma função que pode ser usada para fornecer feedback verboso.</span><span class="sxs-lookup"><span data-stu-id="5d569-125">A function that can be used to provide verbose feedback.</span></span>

## <a name="remarks"></a><span data-ttu-id="5d569-126">Observações</span><span class="sxs-lookup"><span data-stu-id="5d569-126">Remarks</span></span>

<span data-ttu-id="5d569-127">Este UDT não deve ser criado diretamente, mas deve ser especificado ligando e, em @"microsoft.quantum.machinelearning.defaulttrainingoptions" seguida, usando o `w/` operador para anular diferentes predefinições.</span><span class="sxs-lookup"><span data-stu-id="5d569-127">This UDT should not be created directly, but rather should be specified by calling @"microsoft.quantum.machinelearning.defaulttrainingoptions" and then using the `w/` operator to override different defaults.</span></span>

<span data-ttu-id="5d569-128">Por exemplo, utilizar 100.000 medições e, no máximo, 8 épocas de treino:</span><span class="sxs-lookup"><span data-stu-id="5d569-128">For example, to use 100,000 measurements and at most 8 training epochs:</span></span>

```Q#
let options = DefaultTrainingOptions()
              w/ NMeasurements <- 100000
              w/ MaxEpochs <- 8;
```

## <a name="references"></a><span data-ttu-id="5d569-129">Referências</span><span class="sxs-lookup"><span data-stu-id="5d569-129">References</span></span>

- [<span data-ttu-id="5d569-130">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="5d569-130">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)