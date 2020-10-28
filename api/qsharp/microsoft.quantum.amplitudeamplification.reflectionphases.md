---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: Tipo definido pelo utilizador ReflectionPhases
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: e0c7db6cd1aad636a34684958be117de1b9888f8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721815"
---
# <a name="reflectionphases-user-defined-type"></a><span data-ttu-id="03788-102">Tipo definido pelo utilizador ReflectionPhases</span><span class="sxs-lookup"><span data-stu-id="03788-102">ReflectionPhases user defined type</span></span>

<span data-ttu-id="03788-103">Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="03788-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="03788-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="03788-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="03788-105">Fases para uma sequência de reflexos parciais na amplificação da amplitude.</span><span class="sxs-lookup"><span data-stu-id="03788-105">Phases for a sequence of partial reflections in amplitude amplification.</span></span>

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a><span data-ttu-id="03788-106">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="03788-106">Named Items</span></span>

### <a name="aboutstart--double"></a><span data-ttu-id="03788-107">Sobre o Início: [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="03788-107">AboutStart : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="03788-108">Uma série de fases para reflexão sobre o estado inicial.</span><span class="sxs-lookup"><span data-stu-id="03788-108">An array of phases for reflection about the start state.</span></span>
### <a name="abouttarget--double"></a><span data-ttu-id="03788-109">Sobre oTarget : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="03788-109">AboutTarget : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="03788-110">Uma série de fases para reflexão sobre o estado alvo.</span><span class="sxs-lookup"><span data-stu-id="03788-110">An array of phases for reflection about the target state.</span></span>

## <a name="remarks"></a><span data-ttu-id="03788-111">Observações</span><span class="sxs-lookup"><span data-stu-id="03788-111">Remarks</span></span>

<span data-ttu-id="03788-112">Ambas as matrizes devem ter o mesmo comprimento.</span><span class="sxs-lookup"><span data-stu-id="03788-112">Both arrays must be of equal length.</span></span> <span data-ttu-id="03788-113">Note que em muitos casos, a primeira fase sobre o estado de início e última fase sobre o estado-alvo introduz uma mudança de fase global e pode ser definida para $0$.</span><span class="sxs-lookup"><span data-stu-id="03788-113">Note that in many cases, the first phase about the start state and last phase about the target state introduces a global phase shift and may be set to $0$.</span></span>