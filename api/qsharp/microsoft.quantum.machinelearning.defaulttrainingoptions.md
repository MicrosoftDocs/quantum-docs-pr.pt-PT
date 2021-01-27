---
uid: Microsoft.Quantum.MachineLearning.DefaultTrainingOptions
title: Função DeTrainingOptions padrão
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: DefaultTrainingOptions
qsharp.summary: Returns a default set of options for training classifiers.
ms.openlocfilehash: 474683ce5b9ec22bec686fb29d87728afe24d23a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856000"
---
# <a name="defaulttrainingoptions-function"></a><span data-ttu-id="3f835-102">Função DeTrainingOptions padrão</span><span class="sxs-lookup"><span data-stu-id="3f835-102">DefaultTrainingOptions function</span></span>

<span data-ttu-id="3f835-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="3f835-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="3f835-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="3f835-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="3f835-105">Devolve um conjunto predefinido de opções para classificadores de treino.</span><span class="sxs-lookup"><span data-stu-id="3f835-105">Returns a default set of options for training classifiers.</span></span>

```qsharp
function DefaultTrainingOptions () : Microsoft.Quantum.MachineLearning.TrainingOptions
```


## <a name="output--trainingoptions"></a><span data-ttu-id="3f835-106">Saída : [Opções de Formação](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="3f835-106">Output : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="3f835-107">Um conjunto razoável de opções de treino predefinidos para utilização quando os classificadores de treino.</span><span class="sxs-lookup"><span data-stu-id="3f835-107">A reasonable set of default training options for use when training classifiers.</span></span>

## <a name="example"></a><span data-ttu-id="3f835-108">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3f835-108">Example</span></span>

<span data-ttu-id="3f835-109">Para utilizar as opções predefinidos, mas com medições adicionais, utilize o `w/` operador:</span><span class="sxs-lookup"><span data-stu-id="3f835-109">To use the default options, but with additional measurements, use the `w/` operator:</span></span>

```qsharp
let options = DefaultTrainingOptions()
    w/ NMeasurements <- 1000000;
```