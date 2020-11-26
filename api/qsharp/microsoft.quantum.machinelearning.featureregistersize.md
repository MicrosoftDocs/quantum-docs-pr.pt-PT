---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: Função FeatureRegisterSize
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: bc5d5a23cfb431f9506b15bc404ab6955d1c2a35
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196417"
---
# <a name="featureregistersize-function"></a><span data-ttu-id="689ab-102">Função FeatureRegisterSize</span><span class="sxs-lookup"><span data-stu-id="689ab-102">FeatureRegisterSize function</span></span>

<span data-ttu-id="689ab-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="689ab-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="689ab-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="689ab-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="689ab-105">Devolve o número de qubits necessários para codificar um vetor de recurso específico.</span><span class="sxs-lookup"><span data-stu-id="689ab-105">Returns the number of qubits required to encode a particular feature vector.</span></span>

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a><span data-ttu-id="689ab-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="689ab-106">Input</span></span>

### <a name="sample--double"></a><span data-ttu-id="689ab-107">amostra : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="689ab-107">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="689ab-108">Um vetor de característica de amostra para ser codificado em um registo qubit.</span><span class="sxs-lookup"><span data-stu-id="689ab-108">A sample feature vector to be encoded into a qubit register.</span></span>



## <a name="output--int"></a><span data-ttu-id="689ab-109">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="689ab-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="689ab-110">O tamanho necessário para codificar `sample` num registo qubit, expresso em vários qubits.</span><span class="sxs-lookup"><span data-stu-id="689ab-110">The size required to encode `sample` into a qubit register, expressed as a number of qubits.</span></span>