---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: Tipo definido pelo utilizador ReflectionPhases
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: fc3642b76c6e01f0709e78ea42c9ea7237389afa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847170"
---
# <a name="reflectionphases-user-defined-type"></a><span data-ttu-id="e1801-102">Tipo definido pelo utilizador ReflectionPhases</span><span class="sxs-lookup"><span data-stu-id="e1801-102">ReflectionPhases user defined type</span></span>

<span data-ttu-id="e1801-103">Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="e1801-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="e1801-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e1801-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e1801-105">Fases para uma sequência de reflexos parciais na amplificação da amplitude.</span><span class="sxs-lookup"><span data-stu-id="e1801-105">Phases for a sequence of partial reflections in amplitude amplification.</span></span>

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a><span data-ttu-id="e1801-106">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="e1801-106">Named Items</span></span>

### <a name="aboutstart--double"></a><span data-ttu-id="e1801-107">Sobre o Início: [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="e1801-107">AboutStart : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="e1801-108">Uma série de fases para reflexão sobre o estado inicial.</span><span class="sxs-lookup"><span data-stu-id="e1801-108">An array of phases for reflection about the start state.</span></span>
### <a name="abouttarget--double"></a><span data-ttu-id="e1801-109">Sobre oTarget : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="e1801-109">AboutTarget : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="e1801-110">Uma série de fases para reflexão sobre o estado alvo.</span><span class="sxs-lookup"><span data-stu-id="e1801-110">An array of phases for reflection about the target state.</span></span>

## <a name="remarks"></a><span data-ttu-id="e1801-111">Observações</span><span class="sxs-lookup"><span data-stu-id="e1801-111">Remarks</span></span>

<span data-ttu-id="e1801-112">Ambas as matrizes devem ter o mesmo comprimento.</span><span class="sxs-lookup"><span data-stu-id="e1801-112">Both arrays must be of equal length.</span></span> <span data-ttu-id="e1801-113">Note que em muitos casos, a primeira fase sobre o estado de início e última fase sobre o estado-alvo introduz uma mudança de fase global e pode ser definida para $0$.</span><span class="sxs-lookup"><span data-stu-id="e1801-113">Note that in many cases, the first phase about the start state and last phase about the target state introduces a global phase shift and may be set to $0$.</span></span>