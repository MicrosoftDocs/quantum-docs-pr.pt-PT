---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: Função FeatureRegisterSize
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 2754e901d74175c1841a38d795f5de02dabc9b8d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848430"
---
# <a name="featureregistersize-function"></a><span data-ttu-id="7f652-102">Função FeatureRegisterSize</span><span class="sxs-lookup"><span data-stu-id="7f652-102">FeatureRegisterSize function</span></span>

<span data-ttu-id="7f652-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="7f652-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="7f652-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="7f652-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="7f652-105">Devolve o número de qubits necessários para codificar um vetor de recurso específico.</span><span class="sxs-lookup"><span data-stu-id="7f652-105">Returns the number of qubits required to encode a particular feature vector.</span></span>

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a><span data-ttu-id="7f652-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="7f652-106">Input</span></span>

### <a name="sample--double"></a><span data-ttu-id="7f652-107">amostra : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="7f652-107">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="7f652-108">Um vetor de característica de amostra para ser codificado em um registo qubit.</span><span class="sxs-lookup"><span data-stu-id="7f652-108">A sample feature vector to be encoded into a qubit register.</span></span>



## <a name="output--int"></a><span data-ttu-id="7f652-109">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7f652-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7f652-110">O tamanho necessário para codificar `sample` num registo qubit, expresso em vários qubits.</span><span class="sxs-lookup"><span data-stu-id="7f652-110">The size required to encode `sample` into a qubit register, expressed as a number of qubits.</span></span>