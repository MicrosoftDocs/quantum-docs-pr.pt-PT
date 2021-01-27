---
uid: Microsoft.Quantum.Research.Characterization.RandomWalkPhaseEstimation
title: Operação RandomWalkPhaseEstimation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Characterization
qsharp.name: RandomWalkPhaseEstimation
qsharp.summary: Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.
ms.openlocfilehash: f9edafcce62c8b30a6bd52b7dbaa2df2c50c920d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846007"
---
# <a name="randomwalkphaseestimation-operation"></a><span data-ttu-id="295f7-102">Operação RandomWalkPhaseEstimation</span><span class="sxs-lookup"><span data-stu-id="295f7-102">RandomWalkPhaseEstimation operation</span></span>

<span data-ttu-id="295f7-103">Espaço de nome: [Microsoft.Quantum.Research.Characterization](xref:Microsoft.Quantum.Research.Characterization)</span><span class="sxs-lookup"><span data-stu-id="295f7-103">Namespace: [Microsoft.Quantum.Research.Characterization](xref:Microsoft.Quantum.Research.Characterization)</span></span>

<span data-ttu-id="295f7-104">Pacote: [Microsoft.Quantum.Research.Characterization](https://nuget.org/packages/Microsoft.Quantum.Research.Characterization)</span><span class="sxs-lookup"><span data-stu-id="295f7-104">Package: [Microsoft.Quantum.Research.Characterization](https://nuget.org/packages/Microsoft.Quantum.Research.Characterization)</span></span>


<span data-ttu-id="295f7-105">Executa a estimativa da fase iterativa usando uma caminhada aleatória até aproximadamente a inferência bayesiana sobre os resultados clássicos da medição de um dado oráculo e eigenstate.</span><span class="sxs-lookup"><span data-stu-id="295f7-105">Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.</span></span>

```qsharp
operation RandomWalkPhaseEstimation (initialMean : Double, initialStdDev : Double, nMeasurements : Int, maxMeasurements : Int, unwind : Int, oracle : Microsoft.Quantum.Oracles.ContinuousOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="295f7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="295f7-106">Input</span></span>

### <a name="initialmean--double"></a><span data-ttu-id="295f7-107">inicialMean : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="295f7-107">initialMean : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="295f7-108">Média da distribuição prévia normal inicial acima de $\phi$.</span><span class="sxs-lookup"><span data-stu-id="295f7-108">Mean of the initial normal prior distribution over $\phi$.</span></span>


### <a name="initialstddev--double"></a><span data-ttu-id="295f7-109">initialStdDev : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="295f7-109">initialStdDev : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="295f7-110">Desvio padrão da distribuição prévia normal inicial acima de $\phi$.</span><span class="sxs-lookup"><span data-stu-id="295f7-110">Standard deviation of the initial normal prior distribution over $\phi$.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="295f7-111">n Medidas : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="295f7-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="295f7-112">Número de medições a aceitar na estimativa posterior final.</span><span class="sxs-lookup"><span data-stu-id="295f7-112">Number of measurements to be accepted into the final posterior estimate.</span></span>


### <a name="maxmeasurements--int"></a><span data-ttu-id="295f7-113">maxMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="295f7-113">maxMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="295f7-114">Número total de medições que podem ser efetuadas antes da operação ser considerada como tendo falhado.</span><span class="sxs-lookup"><span data-stu-id="295f7-114">Total number of measurements than can be taken before the operation is considered to have failed.</span></span>


### <a name="unwind--int"></a><span data-ttu-id="295f7-115">desenrolar : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="295f7-115">unwind : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="295f7-116">Número de resultados para esquecer quando os controlos de consistência falham.</span><span class="sxs-lookup"><span data-stu-id="295f7-116">Number of results to forget when consistency checks fail.</span></span>


### <a name="oracle--continuousoracle"></a><span data-ttu-id="295f7-117">oráculo : [Continuarocle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span><span class="sxs-lookup"><span data-stu-id="295f7-117">oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span></span>

<span data-ttu-id="295f7-118">Uma operação que representa um $U$ unitário de tal forma que $U(t)\ket{\phi} = e^{i t \phi}\ket{\phi}$ para eigenstates $\ket{\phi}$ com fase desconhecida $\phi \in \mathbb{R}+$.</span><span class="sxs-lookup"><span data-stu-id="295f7-118">An operation representing a unitary $U$ such that $U(t)\ket{\phi} = e^{i t \phi}\ket{\phi}$ for eigenstates $\ket{\phi}$ with unknown phase $\phi \in \mathbb{R}^+$.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="295f7-119">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="295f7-119">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="295f7-120">Um registo em que $U$ atua.</span><span class="sxs-lookup"><span data-stu-id="295f7-120">A register that $U$ acts on.</span></span>



## <a name="output--double"></a><span data-ttu-id="295f7-121">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="295f7-121">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="295f7-122">A estimativa final $\hat{\phi} \mathrel{:=} \expect[\phi]$ , onde a expectativa é superior ao posterior dado todos os dados aceites.</span><span class="sxs-lookup"><span data-stu-id="295f7-122">The final estimate $\hat{\phi} \mathrel{:=} \expect[\phi]$ , where the expectation is over the posterior given all accepted data.</span></span>

## <a name="remarks"></a><span data-ttu-id="295f7-123">Observações</span><span class="sxs-lookup"><span data-stu-id="295f7-123">Remarks</span></span>

### <a name="iterative-phase-estimation-and-eigenstates"></a><span data-ttu-id="295f7-124">Estimativa de Fase Iterativa e Estados Eigen</span><span class="sxs-lookup"><span data-stu-id="295f7-124">Iterative Phase Estimation and Eigenstates</span></span>

<span data-ttu-id="295f7-125">Em geral, o registo de entradas `eigenstate` não precisa de ser um eigenstate $\ket{\phi}$ de $U$, mas pode ser uma superposição sobre eigenstates.</span><span class="sxs-lookup"><span data-stu-id="295f7-125">In general, the input register `eigenstate` need not be an eigenstate $\ket{\phi}$ of $U$, but can be a superposition over eigenstates.</span></span> <span data-ttu-id="295f7-126">Suponha que o estado de entrada é dado por \start{align} \ket{\psi} & = \soma \_ {j} \alpha \_ j \ket{\phi \_ j}, \end{align} onde $ \{ \alpha \_ j $ \} são coeficientes complexos tais que $\sum \_ j |\alpha \_ j|^2 = 1$ e onde $U\ket{\phi \_ j} = \phi \_ j\ket{\phi \_ j}$.</span><span class="sxs-lookup"><span data-stu-id="295f7-126">Suppose that the input state is given by \begin{align} \ket{\psi} & = \sum\_{j} \alpha\_j \ket{\phi\_j}, \end{align} where $\{\alpha\_j\}$ are complex coefficients such that $\sum\_j |\alpha\_j|^2 = 1$ and where $U\ket{\phi\_j} = \phi\_j\ket{\phi\_j}$.</span></span>

<span data-ttu-id="295f7-127">Em seguida, a realização de estimativas de fase iterativas irá eventualmente convergir para um único eigenstate, como descrito no guia de [desenvolvimento](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates).</span><span class="sxs-lookup"><span data-stu-id="295f7-127">Then, performing iterative phase estimation will eventually converge to a single eigenstate, as described in the [development guide](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates).</span></span>

### <a name="experiment-design"></a><span data-ttu-id="295f7-128">Design de experiências</span><span class="sxs-lookup"><span data-stu-id="295f7-128">Experiment Design</span></span>

<span data-ttu-id="295f7-129">Os tempos de medição $t$ e os ângulos de inversão $\theta$ `oracle` passados são escolhidos de acordo com o *palpite de partícula heurístico*, \start{align} \theta \sim \Pr(\phi),\quad t \approx \frac {1} {\variance{\phi}}</span><span class="sxs-lookup"><span data-stu-id="295f7-129">The measurement times $t$ and inversion angles $\theta$ passed to `oracle` are chosen according to the *particle guess heuristic*, \begin{align} \theta \sim \Pr(\phi),\quad t \approx \frac{1}{\variance{\phi}}.</span></span>
<span data-ttu-id="295f7-130">\end{align} Este heurístico é ótimo para reduzir a variação posterior esperada na estimativa de fase iterativa sob o pressuposto de um prior normal.</span><span class="sxs-lookup"><span data-stu-id="295f7-130">\end{align} This heuristic is optimal for reducing the expected posterior variance in iterative phase estimation under the assumption of a normal prior.</span></span>

### <a name="optimality"></a><span data-ttu-id="295f7-131">Optimalidade</span><span class="sxs-lookup"><span data-stu-id="295f7-131">Optimality</span></span>

<span data-ttu-id="295f7-132">Esta operação aproxima o estimador ideal para a fase $\phi$, tal como avaliado com a perda quadrática $L(\phi, \hat{\phi}) \mathrel{:=} (\phi - \hat{\phi})^2$.</span><span class="sxs-lookup"><span data-stu-id="295f7-132">This operation approximates the optimal estimator for the phase $\phi$, as evaluated using the quadratic loss $L(\phi, \hat{\phi}) \mathrel{:=} (\phi - \hat{\phi})^2$.</span></span>

<span data-ttu-id="295f7-133">Consulte [a Estimativa da Fase Bayesiana](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) para obter mais detalhes sobre as estatísticas da estimativa da fase iterativa.</span><span class="sxs-lookup"><span data-stu-id="295f7-133">See [Bayesian Phase Estimation](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) for more details on the statistics of iterative phase estimation.</span></span>

## <a name="references"></a><span data-ttu-id="295f7-134">Referências</span><span class="sxs-lookup"><span data-stu-id="295f7-134">References</span></span>

- <span data-ttu-id="295f7-135">Ferrie *et al.* 2011 [doi:10/tfx,](https://doi.org/10.1007/s11128-012-0407-6) [arXiv:1110.3067](https://arxiv.org/abs/1110.3067).</span><span class="sxs-lookup"><span data-stu-id="295f7-135">Ferrie *et al.* 2011 [doi:10/tfx](https://doi.org/10.1007/s11128-012-0407-6), [arXiv:1110.3067](https://arxiv.org/abs/1110.3067).</span></span>
- <span data-ttu-id="295f7-136">Wiebe *et al.* 2013 [doi:10/tf3](https://doi.org/10.1103/PhysRevLett.112.190501), [arXiv:1309.0876](https://arxiv.org/abs/1309.0876)</span><span class="sxs-lookup"><span data-stu-id="295f7-136">Wiebe *et al.* 2013 [doi:10/tf3](https://doi.org/10.1103/PhysRevLett.112.190501), [arXiv:1309.0876](https://arxiv.org/abs/1309.0876)</span></span>
- <span data-ttu-id="295f7-137">Wiebe e Granade 2018 *(em preparação)*.</span><span class="sxs-lookup"><span data-stu-id="295f7-137">Wiebe and Granade 2018 *(in preparation)*.</span></span>