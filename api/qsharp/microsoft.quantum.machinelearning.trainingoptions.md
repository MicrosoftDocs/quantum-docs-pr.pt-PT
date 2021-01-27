---
uid: Microsoft.Quantum.MachineLearning.TrainingOptions
title: FormaçãoOptions tipo definido pelo utilizador
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainingOptions
qsharp.summary: A collection of options to be used in training quantum classifiers.
ms.openlocfilehash: 762d6853910832c6d4cda522c0c5df706d1ed195
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842768"
---
# <a name="trainingoptions-user-defined-type"></a><span data-ttu-id="085b0-102">FormaçãoOptions tipo definido pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="085b0-102">TrainingOptions user defined type</span></span>

<span data-ttu-id="085b0-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="085b0-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="085b0-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="085b0-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="085b0-105">Uma coleção de opções a serem usadas no treino de classificadores quânticos.</span><span class="sxs-lookup"><span data-stu-id="085b0-105">A collection of options to be used in training quantum classifiers.</span></span>

```qsharp

newtype TrainingOptions = (LearningRate : Double, Tolerance : Double, MinibatchSize : Int, NMeasurements : Int, MaxEpochs : Int, MaxStalls : Int, StochasticRescaleFactor : Double, ScoringPeriod : Int, VerboseMessage : (String -> Unit));
```



## <a name="named-items"></a><span data-ttu-id="085b0-106">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="085b0-106">Named Items</span></span>

### <a name="learningrate--double"></a><span data-ttu-id="085b0-107">LearningRate : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="085b0-107">LearningRate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="085b0-108">A taxa de aprendizagem através da qual os gradientes devem ser redimensionados ao atualizar os parâmetros do modelo durante as etapas de treino.</span><span class="sxs-lookup"><span data-stu-id="085b0-108">The learning rate by which gradients should be rescaled when updating model parameters during training steps.</span></span>
### <a name="tolerance--double"></a><span data-ttu-id="085b0-109">Tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="085b0-109">Tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="085b0-110">A tolerância de aproximação a utilizar na preparação de amostras como estados quânticos.</span><span class="sxs-lookup"><span data-stu-id="085b0-110">The approximation tolerance to use when preparing samples as quantum states.</span></span>
### <a name="minibatchsize--int"></a><span data-ttu-id="085b0-111">MinibatchSize : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="085b0-111">MinibatchSize : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="085b0-112">O número de amostras a utilizar em cada minibatch de treino.</span><span class="sxs-lookup"><span data-stu-id="085b0-112">The number of samples to use in each training minibatch.</span></span>
### <a name="nmeasurements--int"></a><span data-ttu-id="085b0-113">NMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="085b0-113">NMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="085b0-114">O número de vezes para medir cada resultado de classificação para estimar a probabilidade de classificação.</span><span class="sxs-lookup"><span data-stu-id="085b0-114">The number of times to measure each classification result in order to estimate the classification probability.</span></span>
### <a name="maxepochs--int"></a><span data-ttu-id="085b0-115">MaxEpochs : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="085b0-115">MaxEpochs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="085b0-116">O número máximo de épocas para treinar cada modelo.</span><span class="sxs-lookup"><span data-stu-id="085b0-116">The maximum number of epochs to train each model for.</span></span>
### <a name="maxstalls--int"></a><span data-ttu-id="085b0-117">MaxStalls : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="085b0-117">MaxStalls : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="085b0-118">O número máximo de vezes que uma época de treino é permitida para parar (aproximadamente zero gradiente) antes de falhar.</span><span class="sxs-lookup"><span data-stu-id="085b0-118">The maximum number of times a training epoch is allowed to stall (approximately zero gradient) before failing.</span></span>
### <a name="stochasticrescalefactor--double"></a><span data-ttu-id="085b0-119">StochasticRescaleFactor : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="085b0-119">StochasticRescaleFactor : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="085b0-120">A quantidade para redimensionar os modelos paralisados antes de voltar a tentar uma atualização.</span><span class="sxs-lookup"><span data-stu-id="085b0-120">The amount to rescale stalled models by before retrying an update.</span></span>
### <a name="scoringperiod--int"></a><span data-ttu-id="085b0-121">PontuaçãoPeriod : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="085b0-121">ScoringPeriod : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="085b0-122">O número de passos de gradiente a tomar entre pontos de pontuação.</span><span class="sxs-lookup"><span data-stu-id="085b0-122">The number of gradient steps to be taken between scoring points.</span></span>
<span data-ttu-id="085b0-123">Para obter a melhor precisão, desa um.</span><span class="sxs-lookup"><span data-stu-id="085b0-123">For best accuracy, set to 1.</span></span>
### <a name="verbosemessage--string---unit"></a><span data-ttu-id="085b0-124">VerboseMessage : Unidade [de Cordas](xref:microsoft.quantum.lang-ref.string) -> [](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="085b0-124">VerboseMessage : [String](xref:microsoft.quantum.lang-ref.string) -> [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="085b0-125">Uma função que pode ser usada para fornecer feedback verboso.</span><span class="sxs-lookup"><span data-stu-id="085b0-125">A function that can be used to provide verbose feedback.</span></span>

## <a name="remarks"></a><span data-ttu-id="085b0-126">Observações</span><span class="sxs-lookup"><span data-stu-id="085b0-126">Remarks</span></span>

<span data-ttu-id="085b0-127">Este UDT não deve ser criado diretamente, mas deve ser especificado ligando e, em @"microsoft.quantum.machinelearning.defaulttrainingoptions" seguida, usando o `w/` operador para anular diferentes predefinições.</span><span class="sxs-lookup"><span data-stu-id="085b0-127">This UDT should not be created directly, but rather should be specified by calling @"microsoft.quantum.machinelearning.defaulttrainingoptions" and then using the `w/` operator to override different defaults.</span></span>

<span data-ttu-id="085b0-128">Por exemplo, utilizar 100.000 medições e, no máximo, 8 épocas de treino:</span><span class="sxs-lookup"><span data-stu-id="085b0-128">For example, to use 100,000 measurements and at most 8 training epochs:</span></span>

```qsharp
let options = DefaultTrainingOptions()
              w/ NMeasurements <- 100000
              w/ MaxEpochs <- 8;
```

## <a name="references"></a><span data-ttu-id="085b0-129">Referências</span><span class="sxs-lookup"><span data-stu-id="085b0-129">References</span></span>

- [<span data-ttu-id="085b0-130">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="085b0-130">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)