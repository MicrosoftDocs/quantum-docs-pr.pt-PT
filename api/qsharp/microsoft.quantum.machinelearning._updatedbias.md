---
uid: Microsoft.Quantum.MachineLearning._UpdatedBias
title: função _UpdatedBias
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _UpdatedBias
qsharp.summary: Returns a bias value that leads to near-minimum misclassification score.
ms.openlocfilehash: 41a51d8a6a8af299ce3e84b727336b098a3d1160
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844433"
---
# <a name="_updatedbias-function"></a><span data-ttu-id="6ec7b-102">função _UpdatedBias</span><span class="sxs-lookup"><span data-stu-id="6ec7b-102">_UpdatedBias function</span></span>

<span data-ttu-id="6ec7b-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="6ec7b-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="6ec7b-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="6ec7b-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="6ec7b-105">Devolve um valor tendencioso que leva a uma pontuação de classificação quase mínima.</span><span class="sxs-lookup"><span data-stu-id="6ec7b-105">Returns a bias value that leads to near-minimum misclassification score.</span></span>

```qsharp
function _UpdatedBias (labeledProbabilities : (Double, Int)[], bias : Double, tolerance : Double) : Double
```


## <a name="input"></a><span data-ttu-id="6ec7b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6ec7b-106">Input</span></span>

### <a name="labeledprobabilities--doubleint"></a><span data-ttu-id="6ec7b-107">rotulagemProbabilidades :[(Duplo,](xref:microsoft.quantum.lang-ref.double)[Int](xref:microsoft.quantum.lang-ref.int))[]</span><span class="sxs-lookup"><span data-stu-id="6ec7b-107">labeledProbabilities : ([Double](xref:microsoft.quantum.lang-ref.double),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>




### <a name="bias--double"></a><span data-ttu-id="6ec7b-108">parcialidade : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6ec7b-108">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="tolerance--double"></a><span data-ttu-id="6ec7b-109">tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6ec7b-109">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--double"></a><span data-ttu-id="6ec7b-110">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6ec7b-110">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

