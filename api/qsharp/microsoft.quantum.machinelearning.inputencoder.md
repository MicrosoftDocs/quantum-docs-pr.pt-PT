---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: Função InputEncoder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: 771cf01866498f4662864939e6946526c2b5827a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709754"
---
# <a name="inputencoder-function"></a><span data-ttu-id="79744-102">Função InputEncoder</span><span class="sxs-lookup"><span data-stu-id="79744-102">InputEncoder function</span></span>

<span data-ttu-id="79744-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="79744-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="79744-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="79744-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="79744-105">Dado um conjunto de coeficientes e uma tolerância, devolve uma operação de preparação do Estado que prepara cada coeficiente como a amplitude correspondente de um estado de base computacional.</span><span class="sxs-lookup"><span data-stu-id="79744-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.</span></span>

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="79744-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="79744-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="79744-107">coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="79744-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="79744-108">Os coeficientes devem ser codificados num estado de entrada.</span><span class="sxs-lookup"><span data-stu-id="79744-108">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="79744-109">Saída : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="79744-109">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="79744-110">Uma operação de preparação do Estado que prepara os coeficientes dados como um estado de entrada num dado registo.</span><span class="sxs-lookup"><span data-stu-id="79744-110">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>