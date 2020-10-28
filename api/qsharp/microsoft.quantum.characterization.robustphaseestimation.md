---
uid: Microsoft.Quantum.Characterization.RobustPhaseEstimation
title: Operação RobustPhaseEstimation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: RobustPhaseEstimation
qsharp.summary: Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.
ms.openlocfilehash: d04ee578c0e6f916e9a4da451075b79e0630c70a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714937"
---
# <a name="robustphaseestimation-operation"></a><span data-ttu-id="35046-102">Operação RobustPhaseEstimation</span><span class="sxs-lookup"><span data-stu-id="35046-102">RobustPhaseEstimation operation</span></span>

<span data-ttu-id="35046-103">Espaço de nome: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="35046-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="35046-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="35046-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="35046-105">Executa o robusto algoritmo de estimativa de fase quântica não iterativa para um dado oráculo `U` e eigenstate, e fornece uma única estimativa real da fase com escala de variação no limite de Heisenberg.</span><span class="sxs-lookup"><span data-stu-id="35046-105">Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.</span></span>

```qsharp
operation RobustPhaseEstimation (bitsPrecision : Int, oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="35046-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="35046-106">Input</span></span>

### <a name="bitsprecision--int"></a><span data-ttu-id="35046-107">bitsPrecision : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="35046-107">bitsPrecision : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="35046-108">Isto fornece uma estimativa de $\phi$ com desvio padrão $\sigma \le 2\pi / 2^\text{bitsPrecision}$ usando uma série de consultas que escalam como $\sigma \le 10,7 \pi / \text{# de queries}$.</span><span class="sxs-lookup"><span data-stu-id="35046-108">This provides an estimate of $\phi$ with standard deviation $\sigma \le 2\pi / 2^\text{bitsPrecision}$ using a number of queries scaling like $\sigma \le 10.7 \pi / \text{# of queries}$.</span></span>


### <a name="oracle--discreteoracle"></a><span data-ttu-id="35046-109">oráculo : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="35046-109">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="35046-110">Uma operação que implementa $U^m$ para os poderes inteiros $m$.</span><span class="sxs-lookup"><span data-stu-id="35046-110">An operation implementing $U^m$ for given integer powers $m$.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="35046-111">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="35046-111">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="35046-112">Um registo quântico em que $U$ atua.</span><span class="sxs-lookup"><span data-stu-id="35046-112">A quantum register that $U$ acts on.</span></span> <span data-ttu-id="35046-113">Se armazena um eigenstate $\ket{\phi}$ de $U$, então $U\ket{\phi} = e^{i\phi} \ket{\phi}$ por $\phi\in(\pi,\pi]$ uma fase desconhecida.</span><span class="sxs-lookup"><span data-stu-id="35046-113">If it stores an eigenstate $\ket{\phi}$ of $U$, then $U\ket{\phi} = e^{i\phi} \ket{\phi}$ for $\phi\in(-\pi,\pi]$ an unknown phase.</span></span>



## <a name="output--double"></a><span data-ttu-id="35046-114">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="35046-114">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="35046-115">Observações</span><span class="sxs-lookup"><span data-stu-id="35046-115">Remarks</span></span>

<span data-ttu-id="35046-116">No limite de um grande número de consultas, Cramer-Rao limites inferiores para o desvio padrão da estimativa de $\phi$ satisfazer $\sigma \ge 2 \pi / \text{# de consultas}$.</span><span class="sxs-lookup"><span data-stu-id="35046-116">In the limit of a large number of queries, Cramer-Rao lower bounds for the standard deviation of the estimate of $\phi$ satisfy $\sigma \ge 2 \pi / \text{# of queries}$.</span></span>

## <a name="references"></a><span data-ttu-id="35046-117">Referências</span><span class="sxs-lookup"><span data-stu-id="35046-117">References</span></span>

- <span data-ttu-id="35046-118">Calibração Robusta de um Single-Qubit Gate-Set Universal através de Estimativa de Fase Robusta Shelby Kimmel, Guang Hao Low, Theodore J. Yoder https://arxiv.org/abs/1502.02677</span><span class="sxs-lookup"><span data-stu-id="35046-118">Robust Calibration of a Universal Single-Qubit Gate-Set via Robust Phase Estimation Shelby Kimmel, Guang Hao Low, Theodore J. Yoder https://arxiv.org/abs/1502.02677</span></span>