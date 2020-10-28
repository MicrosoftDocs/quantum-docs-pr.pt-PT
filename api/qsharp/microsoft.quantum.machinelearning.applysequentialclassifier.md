---
uid: Microsoft.Quantum.MachineLearning.ApplySequentialClassifier
title: Aplicação Funcionamento DeClassifier
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApplySequentialClassifier
qsharp.summary: Given the structure and parameterization of a sequential classifier, applies the classifier to a register of qubits.
ms.openlocfilehash: 1b4b4853491489f11f222507bb14b48e941e7859
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720550"
---
# <a name="applysequentialclassifier-operation"></a><span data-ttu-id="dbfe1-102">Aplicação Funcionamento DeClassifier</span><span class="sxs-lookup"><span data-stu-id="dbfe1-102">ApplySequentialClassifier operation</span></span>

<span data-ttu-id="dbfe1-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="dbfe1-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="dbfe1-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dbfe1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dbfe1-105">Dada a estrutura e parametrização de um classificador sequencial, aplica o classificador a um registo de qubits.</span><span class="sxs-lookup"><span data-stu-id="dbfe1-105">Given the structure and parameterization of a sequential classifier, applies the classifier to a register of qubits.</span></span>

```qsharp
operation ApplySequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="dbfe1-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="dbfe1-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="dbfe1-107">modelo : [SequencialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="dbfe1-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>




### <a name="qubits--qubit"></a><span data-ttu-id="dbfe1-108">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="dbfe1-108">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="dbfe1-109">Deve ser aplicado um registo-alvo ao qual o classificador deve ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="dbfe1-109">A target register to which the classifier should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dbfe1-110">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dbfe1-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

