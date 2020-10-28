---
uid: Microsoft.Quantum.MachineLearning.NQubitsRequired
title: Função NQubitsRequired
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NQubitsRequired
qsharp.summary: Returns the number of qubits required to apply a given sequential classifier.
ms.openlocfilehash: d7ed687e9c75ed7cc71917aa1cdf32a6fbb93106
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723576"
---
# <a name="nqubitsrequired-function"></a><span data-ttu-id="1b662-102">Função NQubitsRequired</span><span class="sxs-lookup"><span data-stu-id="1b662-102">NQubitsRequired function</span></span>

<span data-ttu-id="1b662-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="1b662-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="1b662-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1b662-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1b662-105">Devolve o número de qubits necessários para aplicar um determinado classificador sequencial.</span><span class="sxs-lookup"><span data-stu-id="1b662-105">Returns the number of qubits required to apply a given sequential classifier.</span></span>

```qsharp
function NQubitsRequired (model : Microsoft.Quantum.MachineLearning.SequentialModel) : Int
```


## <a name="input"></a><span data-ttu-id="1b662-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1b662-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="1b662-107">modelo : [SequencialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="1b662-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>





## <a name="output--int"></a><span data-ttu-id="1b662-108">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1b662-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1b662-109">O tamanho mínimo de um registo no qual pode ser aplicado o classificador sequencial.</span><span class="sxs-lookup"><span data-stu-id="1b662-109">The minimum size of a register on which the sequential classifier may be applied.</span></span>