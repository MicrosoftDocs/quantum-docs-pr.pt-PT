---
uid: Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier
title: Validar operação DesequentialClassifier
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidateSequentialClassifier
qsharp.summary: Validates a given sequential classifier against a given set of pre-labeled samples.
ms.openlocfilehash: 802f1045ea4086bd371d68018a481182cb75b209
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720443"
---
# <a name="validatesequentialclassifier-operation"></a><span data-ttu-id="c0ed7-102">Validar operação DesequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="c0ed7-102">ValidateSequentialClassifier operation</span></span>

<span data-ttu-id="c0ed7-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c0ed7-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="c0ed7-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c0ed7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c0ed7-105">Valida um determinado classificador sequencial contra um determinado conjunto de amostras pré-etiquetadas.</span><span class="sxs-lookup"><span data-stu-id="c0ed7-105">Validates a given sequential classifier against a given set of pre-labeled samples.</span></span>

```qsharp
operation ValidateSequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], tolerance : Double, nMeasurements : Int, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Microsoft.Quantum.MachineLearning.ValidationResults
```


## <a name="input"></a><span data-ttu-id="c0ed7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c0ed7-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="c0ed7-107">modelo : [SequencialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="c0ed7-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="c0ed7-108">O modelo sequencial a ser validado.</span><span class="sxs-lookup"><span data-stu-id="c0ed7-108">The sequential model to be validated.</span></span>


### <a name="samples--labeledsample"></a><span data-ttu-id="c0ed7-109">amostras : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span><span class="sxs-lookup"><span data-stu-id="c0ed7-109">samples : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span></span>

<span data-ttu-id="c0ed7-110">As amostras a utilizar para validar o modelo dado.</span><span class="sxs-lookup"><span data-stu-id="c0ed7-110">The samples to be used to validate the given model.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="c0ed7-111">tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c0ed7-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c0ed7-112">A tolerância de aproximação a utilizar na codificação de cada amostra como entrada para o classificador sequencial.</span><span class="sxs-lookup"><span data-stu-id="c0ed7-112">The approximation tolerance to use in encoding each sample as an input to the sequential classifier.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="c0ed7-113">n Medidas : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c0ed7-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c0ed7-114">O número de medições a utilizar na classificação de cada amostra.</span><span class="sxs-lookup"><span data-stu-id="c0ed7-114">The number of measurements to use in classifying each sample.</span></span>


### <a name="validationschedule--samplingschedule"></a><span data-ttu-id="c0ed7-115">validaçãoSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="c0ed7-115">validationSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="c0ed7-116">O calendário através do qual as amostras devem ser retiradas do conjunto de validação.</span><span class="sxs-lookup"><span data-stu-id="c0ed7-116">The schedule by which samples should be drawn from the validation set.</span></span>



## <a name="output--validationresults"></a><span data-ttu-id="c0ed7-117">Saída : [ValidaçõesResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)</span><span class="sxs-lookup"><span data-stu-id="c0ed7-117">Output : [ValidationResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)</span></span>

<span data-ttu-id="c0ed7-118">Os resultados da validação dada.</span><span class="sxs-lookup"><span data-stu-id="c0ed7-118">The results of the given validation.</span></span>