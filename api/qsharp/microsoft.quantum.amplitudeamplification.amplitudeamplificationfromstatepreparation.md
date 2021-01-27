---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation
title: AmplitudeAmplificaçãoFromStatePreparation function
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromStatePreparation
qsharp.summary: Amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: e64ad5ad4e975483f20f92c0b070dd6788ef296b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847443"
---
# <a name="amplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="601e5-102">AmplitudeAmplificaçãoFromStatePreparation function</span><span class="sxs-lookup"><span data-stu-id="601e5-102">AmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="601e5-103">Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="601e5-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="601e5-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="601e5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="601e5-105">Amplificação de amplitude por oráculos para reflexões parciais.</span><span class="sxs-lookup"><span data-stu-id="601e5-105">Amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="601e5-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="601e5-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="601e5-107">fases : [Fases de Reflexão](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="601e5-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="601e5-108">Fases de reflexões parciais</span><span class="sxs-lookup"><span data-stu-id="601e5-108">Phases of partial reflections</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="601e5-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="601e5-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="601e5-110">Oráculo unitário $A dólar que prepara o estado de arranque</span><span class="sxs-lookup"><span data-stu-id="601e5-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="601e5-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="601e5-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="601e5-112">Índice para qubit de bandeira</span><span class="sxs-lookup"><span data-stu-id="601e5-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="601e5-113">Saída : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="601e5-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="601e5-114">Uma operação que implementa amplificação de amplitude por oráculos que são implementados por reflexões parciais.</span><span class="sxs-lookup"><span data-stu-id="601e5-114">An operation that implements amplitude amplification by oracles that are implemented by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="601e5-115">Observações</span><span class="sxs-lookup"><span data-stu-id="601e5-115">Remarks</span></span>

<span data-ttu-id="601e5-116">Isto impõe condições mais rigorosas na forma dos estados de partida e alvo do que em `AmpAmpByReflectionPhases` .</span><span class="sxs-lookup"><span data-stu-id="601e5-116">This imposes stricter conditions on form of the start and target states than in `AmpAmpByReflectionPhases`.</span></span>
<span data-ttu-id="601e5-117">Presume-se que o estado-alvo é marcado por $\ket {1} \_ f$.</span><span class="sxs-lookup"><span data-stu-id="601e5-117">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="601e5-118">Presume-se que \start{align} A\ket {0} \_ {f}\ket= {0} \_ \lambda\ket {1} \_ f\ket f\ket{\text{target}} \_ s + \sqrt{1-|\lambda|^2}\ket {0} \_ f\cdots, \end{align} Na maioria dos casos, `flagQubit` e são `auxiliaryRegister` inicializados no estado $\ket {0} \_ {f}ket {0} \_</span><span class="sxs-lookup"><span data-stu-id="601e5-118">It is assumed that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} In most cases, `flagQubit` and `auxiliaryRegister` are initialized in the state $\ket{0}\_{f}\ket{0}\_s$.</span></span>