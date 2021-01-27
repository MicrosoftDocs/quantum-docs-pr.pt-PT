---
uid: Microsoft.Quantum.MachineLearning.ApproximateInputEncoder
title: Função AproximadaInputEncoder
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApproximateInputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.
ms.openlocfilehash: 035c353c34362aa3486a7df9e7bb1bc95a6f63be
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856169"
---
# <a name="approximateinputencoder-function"></a><span data-ttu-id="23f3a-102">Função AproximadaInputEncoder</span><span class="sxs-lookup"><span data-stu-id="23f3a-102">ApproximateInputEncoder function</span></span>

<span data-ttu-id="23f3a-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="23f3a-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="23f3a-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="23f3a-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="23f3a-105">Dado um conjunto de coeficientes e uma tolerância, devolve uma operação de preparação do Estado que prepara cada coeficiente como a correspondente amplitude de um estado de base computacional, até à tolerância dada.</span><span class="sxs-lookup"><span data-stu-id="23f3a-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.</span></span>

```qsharp
function ApproximateInputEncoder (tolerance : Double, coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="23f3a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="23f3a-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="23f3a-107">tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="23f3a-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="23f3a-108">A tolerância de aproximação a ser utilizada na codificação dos coeficientes dados num estado de entrada.</span><span class="sxs-lookup"><span data-stu-id="23f3a-108">The approximation tolerance to be used in encoding the given coefficients into an input state.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="23f3a-109">coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="23f3a-109">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="23f3a-110">Os coeficientes devem ser codificados num estado de entrada.</span><span class="sxs-lookup"><span data-stu-id="23f3a-110">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="23f3a-111">Saída : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="23f3a-111">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="23f3a-112">Uma operação de preparação do Estado que prepara os coeficientes dados como um estado de entrada num dado registo.</span><span class="sxs-lookup"><span data-stu-id="23f3a-112">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>