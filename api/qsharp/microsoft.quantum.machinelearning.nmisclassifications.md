---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: Função de classificações NMisclassificações
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: adc7042d6108c7ec72d13340633824d3eaf5e18e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853909"
---
# <a name="nmisclassifications-function"></a><span data-ttu-id="12e2f-102">Função de classificações NMisclassificações</span><span class="sxs-lookup"><span data-stu-id="12e2f-102">NMisclassifications function</span></span>

<span data-ttu-id="12e2f-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="12e2f-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="12e2f-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="12e2f-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="12e2f-105">Tendo em conta um conjunto de rótulos inferidos e um conjunto de etiquetas corretas, o número de índices em que cada conjunto de rótulos difere.</span><span class="sxs-lookup"><span data-stu-id="12e2f-105">Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.</span></span>

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a><span data-ttu-id="12e2f-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="12e2f-106">Input</span></span>

### <a name="proposed--int"></a><span data-ttu-id="12e2f-107">proposto : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="12e2f-107">proposed : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="actual--int"></a><span data-ttu-id="12e2f-108">real : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="12e2f-108">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--int"></a><span data-ttu-id="12e2f-109">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="12e2f-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="12e2f-110">O número de índices `idx` tal que `inferredLabels[idx] != actualLabels[idx]` . .</span><span class="sxs-lookup"><span data-stu-id="12e2f-110">The number of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>

## <a name="example"></a><span data-ttu-id="12e2f-111">Exemplo</span><span class="sxs-lookup"><span data-stu-id="12e2f-111">Example</span></span>

```qsharp
let nMisclassifications = NMisclassifications([1, 1, 0, 0], [0, 1, 1, 0]);
Message($"{nMisclassifications}"); // Will print 2.
```