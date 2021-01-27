---
uid: Microsoft.Quantum.MachineLearning.NQubitsRequired
title: Função NQubitsRequired
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NQubitsRequired
qsharp.summary: Returns the number of qubits required to apply a given sequential classifier.
ms.openlocfilehash: 8f6c1bf3dfef3152a6ba8eada0980d6940724259
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854955"
---
# <a name="nqubitsrequired-function"></a><span data-ttu-id="0ac27-102">Função NQubitsRequired</span><span class="sxs-lookup"><span data-stu-id="0ac27-102">NQubitsRequired function</span></span>

<span data-ttu-id="0ac27-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="0ac27-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="0ac27-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="0ac27-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="0ac27-105">Devolve o número de qubits necessários para aplicar um determinado classificador sequencial.</span><span class="sxs-lookup"><span data-stu-id="0ac27-105">Returns the number of qubits required to apply a given sequential classifier.</span></span>

```qsharp
function NQubitsRequired (model : Microsoft.Quantum.MachineLearning.SequentialModel) : Int
```


## <a name="input"></a><span data-ttu-id="0ac27-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="0ac27-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="0ac27-107">modelo : [SequencialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="0ac27-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>





## <a name="output--int"></a><span data-ttu-id="0ac27-108">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0ac27-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0ac27-109">O tamanho mínimo de um registo no qual pode ser aplicado o classificador sequencial.</span><span class="sxs-lookup"><span data-stu-id="0ac27-109">The minimum size of a register on which the sequential classifier may be applied.</span></span>