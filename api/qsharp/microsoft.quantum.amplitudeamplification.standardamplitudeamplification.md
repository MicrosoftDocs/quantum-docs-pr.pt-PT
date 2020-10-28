---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification
title: Função StandardAmplitudeAmplificação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardAmplitudeAmplification
qsharp.summary: Standard Amplitude Amplification algorithm
ms.openlocfilehash: 18228d45c4df280b004c595a7b0f1e2a607b8b2c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721745"
---
# <a name="standardamplitudeamplification-function"></a><span data-ttu-id="6946f-102">Função StandardAmplitudeAmplificação</span><span class="sxs-lookup"><span data-stu-id="6946f-102">StandardAmplitudeAmplification function</span></span>

<span data-ttu-id="6946f-103">Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="6946f-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="6946f-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6946f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6946f-105">Algoritmo de amplificação de amplitude padrão</span><span class="sxs-lookup"><span data-stu-id="6946f-105">Standard Amplitude Amplification algorithm</span></span>

```qsharp
function StandardAmplitudeAmplification (nIterations : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="6946f-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6946f-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="6946f-107">niterações : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6946f-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6946f-108">Número de iterações $n$ de amplificação da amplitude</span><span class="sxs-lookup"><span data-stu-id="6946f-108">Number of iterations $n$ of amplitude amplification</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="6946f-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="6946f-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="6946f-110">Oráculo unitário $A dólar que prepara o estado de arranque</span><span class="sxs-lookup"><span data-stu-id="6946f-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="6946f-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6946f-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6946f-112">Índice para qubit de bandeira</span><span class="sxs-lookup"><span data-stu-id="6946f-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="6946f-113">Saída : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit)> Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="6946f-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="6946f-114">Uma operação que implementa o algoritmo quântico de amplificação de amplitude padrão</span><span class="sxs-lookup"><span data-stu-id="6946f-114">An operation that implements the standard amplitude amplification quantum algorithm</span></span>

## <a name="remarks"></a><span data-ttu-id="6946f-115">Observações</span><span class="sxs-lookup"><span data-stu-id="6946f-115">Remarks</span></span>

<span data-ttu-id="6946f-116">Este é o algoritmo de amplificação de amplitude padrão obtido por uma escolha de fases de reflexão `AmpAmpPhasesStandard` computacionalizadas por Assumindo que \start{align} A\ket {0} \_ {f}ket {0} \_ s= \lambda\ket {1} \_ f\ket{\text{target}} \_ s + \sqrt{1-\lambda^/2}ket {0} \_ f\cdots, \end{align} esta operação prepara o estado \start{align} \operatorname{AmpAmpByOracle}\ket {0} \_ {f}\ket {0} \_ s= \sin((2n+1)\sin^ {-1} (\lambda)\ket {1} \_ f\ket{\text{target}} \_ e é {0} \_ `flagQubit` `auxiliaryRegister` inicializado no estado $\ket {0} \_ f\ket {0} \_ a$.</span><span class="sxs-lookup"><span data-stu-id="6946f-116">This is the standard amplitude amplification algorithm obtained by a choice of reflection phases computed by `AmpAmpPhasesStandard` Assuming that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} this operation prepares the state \begin{align} \operatorname{AmpAmpByOracle}\ket{0}\_{f}\ket{0}\_s= \sin((2n+1)\sin^{-1}(\lambda))\ket{1}\_f\ket{\text{target}}\_s + \cdots\ket{0}\_f \end{align} In most cases, `flagQubit` and `auxiliaryRegister` is initialized in the state $\ket{0}\_f\ket{0}\_a$.</span></span>

## <a name="references"></a><span data-ttu-id="6946f-117">Referências</span><span class="sxs-lookup"><span data-stu-id="6946f-117">References</span></span>

- [<span data-ttu-id="6946f-118">*G. Brassard, P. Hoyer, M. Mosca, A. Tapp*</span><span class="sxs-lookup"><span data-stu-id="6946f-118"> *G. Brassard, P. Hoyer, M. Mosca, A. Tapp* </span></span>](https://arxiv.org/abs/quant-ph/0005055)