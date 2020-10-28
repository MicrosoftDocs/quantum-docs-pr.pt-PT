---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: Rotação Tipo definido pelo utilizador
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: b0373f964b77f8ea561c6e96b11e476b42e7fc55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721770"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="96b2c-102">Rotação Tipo definido pelo utilizador</span><span class="sxs-lookup"><span data-stu-id="96b2c-102">RotationPhases user defined type</span></span>

<span data-ttu-id="96b2c-103">Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="96b2c-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="96b2c-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="96b2c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="96b2c-105">Fases para uma sequência de rotações de um único qubit em amplificação de amplitude.</span><span class="sxs-lookup"><span data-stu-id="96b2c-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="96b2c-106">Observações</span><span class="sxs-lookup"><span data-stu-id="96b2c-106">Remarks</span></span>

<span data-ttu-id="96b2c-107">O primeiro parâmetro é um conjunto de fases para reflexões, expressas como um produto de rotações de um único qubit.</span><span class="sxs-lookup"><span data-stu-id="96b2c-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="96b2c-108">G.H.</span><span class="sxs-lookup"><span data-stu-id="96b2c-108">[ G.H.</span></span> <span data-ttu-id="96b2c-109">Baixo, I.L.</span><span class="sxs-lookup"><span data-stu-id="96b2c-109">Low, I. L.</span></span> <span data-ttu-id="96b2c-110"> https://arxiv.org/abs/1707.05391Chuang, ].</span><span class="sxs-lookup"><span data-stu-id="96b2c-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>