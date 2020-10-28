---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: Tipo definido pelo utilizador sequencialModel
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: a425d2155489384ca81ef1c00a5e842bcfb40ae7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722389"
---
# <a name="sequentialmodel-user-defined-type"></a><span data-ttu-id="7fac2-102">Tipo definido pelo utilizador sequencialModel</span><span class="sxs-lookup"><span data-stu-id="7fac2-102">SequentialModel user defined type</span></span>

<span data-ttu-id="7fac2-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="7fac2-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="7fac2-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7fac2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7fac2-105">Descreve um modelo de classificador quântico composto por uma sequência de rotações parametrizadas e controladas, uma atribuição de ângulos de rotação, e um enviesamento entre as duas classes reconhecidas pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="7fac2-105">Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.</span></span>

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a><span data-ttu-id="7fac2-106">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="7fac2-106">Named Items</span></span>

### <a name="structure--controlledrotation"></a><span data-ttu-id="7fac2-107">Estrutura : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="7fac2-107">Structure : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="7fac2-108">A sequência de rotações controladas usadas para classificar as entradas.</span><span class="sxs-lookup"><span data-stu-id="7fac2-108">The sequence of controlled rotations used to classify inputs.</span></span>
### <a name="parameters--double"></a><span data-ttu-id="7fac2-109">Parâmetros : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="7fac2-109">Parameters : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="7fac2-110">Uma atribuição de ângulos de rotação à estrutura de classificação dada.</span><span class="sxs-lookup"><span data-stu-id="7fac2-110">An assignment of rotation angles to the given classification structure.</span></span>
### <a name="bias--double"></a><span data-ttu-id="7fac2-111">Preconceito : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7fac2-111">Bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7fac2-112">O enviesamento entre as duas classes reconhecidas por este classificador.</span><span class="sxs-lookup"><span data-stu-id="7fac2-112">The bias between the two classes recognized by this classifier.</span></span>

## <a name="references"></a><span data-ttu-id="7fac2-113">Referências</span><span class="sxs-lookup"><span data-stu-id="7fac2-113">References</span></span>

- [<span data-ttu-id="7fac2-114">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="7fac2-114">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)