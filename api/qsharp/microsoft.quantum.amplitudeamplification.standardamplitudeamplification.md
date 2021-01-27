---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification
title: Função StandardAmplitudeAmplificação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardAmplitudeAmplification
qsharp.summary: Standard Amplitude Amplification algorithm
ms.openlocfilehash: 984bfee89b6d79750228b8ca6aaf404f58aecd41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843930"
---
# <a name="standardamplitudeamplification-function"></a><span data-ttu-id="c8dfd-102">Função StandardAmplitudeAmplificação</span><span class="sxs-lookup"><span data-stu-id="c8dfd-102">StandardAmplitudeAmplification function</span></span>

<span data-ttu-id="c8dfd-103">Espaço de nome: [Microsoft.Quantum.AmplitudeAmplificação](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="c8dfd-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="c8dfd-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c8dfd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c8dfd-105">Algoritmo de amplificação de amplitude padrão</span><span class="sxs-lookup"><span data-stu-id="c8dfd-105">Standard Amplitude Amplification algorithm</span></span>

```qsharp
function StandardAmplitudeAmplification (nIterations : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="c8dfd-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c8dfd-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="c8dfd-107">niterações : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c8dfd-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c8dfd-108">Número de iterações $n$ de amplificação da amplitude</span><span class="sxs-lookup"><span data-stu-id="c8dfd-108">Number of iterations $n$ of amplitude amplification</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="c8dfd-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="c8dfd-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="c8dfd-110">Oráculo unitário $A dólar que prepara o estado de arranque</span><span class="sxs-lookup"><span data-stu-id="c8dfd-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="c8dfd-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c8dfd-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c8dfd-112">Índice para qubit de bandeira</span><span class="sxs-lookup"><span data-stu-id="c8dfd-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="c8dfd-113">Saída : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="c8dfd-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c8dfd-114">Uma operação que implementa o algoritmo quântico de amplificação de amplitude padrão</span><span class="sxs-lookup"><span data-stu-id="c8dfd-114">An operation that implements the standard amplitude amplification quantum algorithm</span></span>

## <a name="remarks"></a><span data-ttu-id="c8dfd-115">Observações</span><span class="sxs-lookup"><span data-stu-id="c8dfd-115">Remarks</span></span>

<span data-ttu-id="c8dfd-116">Este é o algoritmo de amplificação de amplitude padrão obtido por uma escolha de fases de reflexão `AmpAmpPhasesStandard` computacional computacionalmente assumindo que \start{align} A\ket {0} \_ {f}ket= {0} \_ \lambda\ket {1} \_ f\ket{\text{target}} \_ s + \sqrt{1-|\lambda|^2}ket {0} \_ f\5, \end{align} esta operação prepara o estado \start{align} \operatorname{AmpAmpByOracle}\ket {0} \_ {f}\ket {0} \_ s= \sin((2n+1)\sin^ {-1} (\lambda)\ket {1} \_ f\ket{\text{target}} \_ e é {0} \_ `flagQubit` `auxiliaryRegister` inicializado no estado $\ket {0} \_ f\ket {0} \_ a$.</span><span class="sxs-lookup"><span data-stu-id="c8dfd-116">This is the standard amplitude amplification algorithm obtained by a choice of reflection phases computed by `AmpAmpPhasesStandard` Assuming that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} this operation prepares the state \begin{align} \operatorname{AmpAmpByOracle}\ket{0}\_{f}\ket{0}\_s= \sin((2n+1)\sin^{-1}(\lambda))\ket{1}\_f\ket{\text{target}}\_s + \cdots\ket{0}\_f \end{align} In most cases, `flagQubit` and `auxiliaryRegister` is initialized in the state $\ket{0}\_f\ket{0}\_a$.</span></span>

## <a name="references"></a><span data-ttu-id="c8dfd-117">Referências</span><span class="sxs-lookup"><span data-stu-id="c8dfd-117">References</span></span>

- [<span data-ttu-id="c8dfd-118">*G. Brassard, P. Hoyer, M. Mosca, A. Tapp*</span><span class="sxs-lookup"><span data-stu-id="c8dfd-118"> *G. Brassard, P. Hoyer, M. Mosca, A. Tapp* </span></span>](https://arxiv.org/abs/quant-ph/0005055)