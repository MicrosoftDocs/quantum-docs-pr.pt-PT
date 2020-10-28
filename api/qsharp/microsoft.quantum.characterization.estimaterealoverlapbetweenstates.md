---
uid: Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates
title: EstimativaRealOverlapBetweenStates operação
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateRealOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the real part of the overlap between the states prepared by each operation.
ms.openlocfilehash: 01631bcbff2bff26ddc1db4e42d90ac4f8380bd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714976"
---
# <a name="estimaterealoverlapbetweenstates-operation"></a><span data-ttu-id="27453-102">EstimativaRealOverlapBetweenStates operação</span><span class="sxs-lookup"><span data-stu-id="27453-102">EstimateRealOverlapBetweenStates operation</span></span>

<span data-ttu-id="27453-103">Espaço de nome: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="27453-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="27453-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="27453-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="27453-105">Tendo em conta duas operações que cada uma prepara cópias de um Estado, estima a parte real da sobreposição entre os Estados preparados por cada operação.</span><span class="sxs-lookup"><span data-stu-id="27453-105">Given two operations which each prepare copies of a state, estimates the real part of the overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateRealOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="27453-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="27453-106">Input</span></span>

### <a name="commonpreparation--qubit--unit-adj"></a><span data-ttu-id="27453-107">comunsPreparação : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj</span><span class="sxs-lookup"><span data-stu-id="27453-107">commonPreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="27453-108">Uma operação que prepara um estado de entrada fixo.</span><span class="sxs-lookup"><span data-stu-id="27453-108">An operation that prepares a fixed input state.</span></span>


### <a name="preparation1--qubit--unit-adj--ctl"></a><span data-ttu-id="27453-109">preparação1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = unidade> [Adj](xref:microsoft.quantum.lang-ref.unit) + Ctl</span><span class="sxs-lookup"><span data-stu-id="27453-109">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="27453-110">A primeira das duas operações de preparação do Estado a ser comparada.</span><span class="sxs-lookup"><span data-stu-id="27453-110">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit-adj--ctl"></a><span data-ttu-id="27453-111">preparação2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit)> Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="27453-111">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="27453-112">A segunda das duas operações de preparação do Estado deve ser comparada.</span><span class="sxs-lookup"><span data-stu-id="27453-112">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="27453-113">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="27453-113">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="27453-114">O número de qubits em que `commonPreparation` `preparation1` , e todos `preparation2` agem.</span><span class="sxs-lookup"><span data-stu-id="27453-114">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="27453-115">n Medidas : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="27453-115">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="27453-116">O número de medições a utilizar na estimativa da sobreposição.</span><span class="sxs-lookup"><span data-stu-id="27453-116">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="27453-117">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="27453-117">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="27453-118">Observações</span><span class="sxs-lookup"><span data-stu-id="27453-118">Remarks</span></span>

<span data-ttu-id="27453-119">Esta operação usa o teste Hadamard para encontrar a parte real de $$ \start{align} \braket{\psi V^{\dagger} U / \psi} \end{align} $$ where $\ket{\psi}$ é o estado preparado `commonPreparation` por, $U$ é a representação unitária da ação de `preparation1` , e onde $V$ corresponde a `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="27453-119">This operation uses the Hadamard test to find the real part of $$ \begin{align} \braket{\psi | V^{\dagger} U | \psi} \end{align} $$ where $\ket{\psi}$ is the state prepared by `commonPreparation`, $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="references"></a><span data-ttu-id="27453-120">Referências</span><span class="sxs-lookup"><span data-stu-id="27453-120">References</span></span>

- <span data-ttu-id="27453-121">Aharonov *et al.* [quant-ph/0511096](https://arxiv.org/abs/quant-ph/0511096).</span><span class="sxs-lookup"><span data-stu-id="27453-121">Aharonov *et al.* [quant-ph/0511096](https://arxiv.org/abs/quant-ph/0511096).</span></span>

## <a name="see-also"></a><span data-ttu-id="27453-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="27453-122">See Also</span></span>

- [<span data-ttu-id="27453-123">Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="27453-123">Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)
- [<span data-ttu-id="27453-124">Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="27453-124">Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)