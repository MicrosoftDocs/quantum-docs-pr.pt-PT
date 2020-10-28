---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: Função Velocidadess De RotaçãoAsReflectionAs
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: d62a7584324c9467ccc759e4bed81acbceee719c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721756"
---
# <a name="rotationphasesasreflectionphases-function"></a><span data-ttu-id="2545d-102">Função Velocidadess De RotaçãoAsReflectionAs</span><span class="sxs-lookup"><span data-stu-id="2545d-102">RotationPhasesAsReflectionPhases function</span></span>

<span data-ttu-id="2545d-103">Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="2545d-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="2545d-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2545d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2545d-105">Converte fases especificadas como rotações de um único qubit para fases especificadas como reflexos parciais.</span><span class="sxs-lookup"><span data-stu-id="2545d-105">Converts phases specified as single-qubit rotations to phases specified as partial reflections.</span></span>

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="2545d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2545d-106">Input</span></span>

### <a name="rotphases--rotationphases"></a><span data-ttu-id="2545d-107">rotfases : [Velocidades de rotação](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span><span class="sxs-lookup"><span data-stu-id="2545d-107">rotPhases : [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span></span>

<span data-ttu-id="2545d-108">Matriz de rotações de um único qubit a converter em reflexos parciais.</span><span class="sxs-lookup"><span data-stu-id="2545d-108">Array of single-qubit rotations to be converted to partial reflections.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="2545d-109">Saída : [Fases de Reflexão](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="2545d-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="2545d-110">Uma operação que implementa fases especificadas como reflexos parciais.</span><span class="sxs-lookup"><span data-stu-id="2545d-110">An operation that implements phases specified as partial reflections.</span></span>

## <a name="references"></a><span data-ttu-id="2545d-111">Referências</span><span class="sxs-lookup"><span data-stu-id="2545d-111">References</span></span>

<span data-ttu-id="2545d-112">Usamos a convenção em</span><span class="sxs-lookup"><span data-stu-id="2545d-112">We use the convention in</span></span>

- <span data-ttu-id="2545d-113">[ *G.H. Low, I. L. Chuang*](https://arxiv.org/abs/1707.05391) por relacionar fases de rotação de um único qubit às fases do operador de reflexão.</span><span class="sxs-lookup"><span data-stu-id="2545d-113">[ *G.H. Low, I. L. Chuang* ](https://arxiv.org/abs/1707.05391) for relating single-qubit rotation phases to reflection operator phases.</span></span>