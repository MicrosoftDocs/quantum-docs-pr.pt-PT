---
uid: Microsoft.Quantum.MachineLearning._UpdatedBias
title: função _UpdatedBias
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _UpdatedBias
qsharp.summary: Returns a bias value that leads to near-minimum misclassification score.
ms.openlocfilehash: 141edf6e425a060a995bfc181aefb1bcffdb128b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196706"
---
# <a name="_updatedbias-function"></a><span data-ttu-id="adb19-102">função _UpdatedBias</span><span class="sxs-lookup"><span data-stu-id="adb19-102">_UpdatedBias function</span></span>

<span data-ttu-id="adb19-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="adb19-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="adb19-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="adb19-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="adb19-105">Devolve um valor tendencioso que leva a uma pontuação de classificação quase mínima.</span><span class="sxs-lookup"><span data-stu-id="adb19-105">Returns a bias value that leads to near-minimum misclassification score.</span></span>

```qsharp
function _UpdatedBias (labeledProbabilities : (Double, Int)[], bias : Double, tolerance : Double) : Double
```


## <a name="input"></a><span data-ttu-id="adb19-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="adb19-106">Input</span></span>

### <a name="labeledprobabilities--doubleint"></a><span data-ttu-id="adb19-107">rotulagemProbabilidades :[(Duplo,](xref:microsoft.quantum.lang-ref.double)[Int](xref:microsoft.quantum.lang-ref.int))[]</span><span class="sxs-lookup"><span data-stu-id="adb19-107">labeledProbabilities : ([Double](xref:microsoft.quantum.lang-ref.double),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>




### <a name="bias--double"></a><span data-ttu-id="adb19-108">parcialidade : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="adb19-108">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="tolerance--double"></a><span data-ttu-id="adb19-109">tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="adb19-109">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--double"></a><span data-ttu-id="adb19-110">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="adb19-110">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

