---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections
title: AmplitudeAmplificaçãoFromPartialReflections função
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromPartialReflections
qsharp.summary: Amplitude amplification by partial reflections.
ms.openlocfilehash: fc7c2c0d05ea626f7f7e5d8ebf3ce5ecea61390b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721952"
---
# <a name="amplitudeamplificationfrompartialreflections-function"></a><span data-ttu-id="a9409-102">AmplitudeAmplificaçãoFromPartialReflections função</span><span class="sxs-lookup"><span data-stu-id="a9409-102">AmplitudeAmplificationFromPartialReflections function</span></span>

<span data-ttu-id="a9409-103">Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="a9409-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="a9409-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a9409-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a9409-105">Amplificação de amplitude por reflexos parciais.</span><span class="sxs-lookup"><span data-stu-id="a9409-105">Amplitude amplification by partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromPartialReflections (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="a9409-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a9409-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="a9409-107">fases : [Fases de Reflexão](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="a9409-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="a9409-108">Fases de reflexões parciais</span><span class="sxs-lookup"><span data-stu-id="a9409-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="a9409-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="a9409-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="a9409-110">Operador de reflexão sobre estado de início</span><span class="sxs-lookup"><span data-stu-id="a9409-110">Reflection operator about start state</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="a9409-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="a9409-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="a9409-112">Operador de reflexão sobre estado-alvo</span><span class="sxs-lookup"><span data-stu-id="a9409-112">Reflection operator about target state</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="a9409-113">Saída : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit)> Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="a9409-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="a9409-114">Uma operação que implementa amplificação de amplitude por reflexos parciais.</span><span class="sxs-lookup"><span data-stu-id="a9409-114">An operation that implements amplitude amplification by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="a9409-115">Observações</span><span class="sxs-lookup"><span data-stu-id="a9409-115">Remarks</span></span>

<span data-ttu-id="a9409-116">A amplificação da amplitude é um caso especial de amplificação de amplitude alheia onde não existem qubits de sistema e o oráculo alheio está definido para a identidade.</span><span class="sxs-lookup"><span data-stu-id="a9409-116">Amplitude amplification is a special case of oblivious amplitude amplification where there are no system qubits and the oblivious oracle is set to identity.</span></span>
<span data-ttu-id="a9409-117">Na maioria dos casos, `startQubits` é inicializado no estado $\ket{\text{start}} \_ 1$, que é o $-1$ eigenstate de `startStateReflection` .</span><span class="sxs-lookup"><span data-stu-id="a9409-117">In most cases, `startQubits` is initialized in the state $\ket{\text{start}}\_1$, which is the $-1$ eigenstate of `startStateReflection`.</span></span>