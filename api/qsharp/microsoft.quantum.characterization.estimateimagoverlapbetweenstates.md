---
uid: Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates
title: EstimativaImagOverlapBetweenStates operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateImagOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the imaginary part of the overlap between the states prepared by each operation.
ms.openlocfilehash: f18ce43f9e5ebada4c5cc0aeff1538ac640c7390
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851876"
---
# <a name="estimateimagoverlapbetweenstates-operation"></a><span data-ttu-id="7a98d-102">EstimativaImagOverlapBetweenStates operação</span><span class="sxs-lookup"><span data-stu-id="7a98d-102">EstimateImagOverlapBetweenStates operation</span></span>

<span data-ttu-id="7a98d-103">Espaço de nome: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="7a98d-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="7a98d-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7a98d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7a98d-105">Tendo em conta duas operações que cada uma prepara cópias de um Estado, estima a parte imaginária da sobreposição entre os Estados preparados por cada operação.</span><span class="sxs-lookup"><span data-stu-id="7a98d-105">Given two operations which each prepare copies of a state, estimates the imaginary part of the overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateImagOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="7a98d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="7a98d-106">Input</span></span>

### <a name="commonpreparation--qubit--unit--is-adj"></a><span data-ttu-id="7a98d-107">comunsPreparação : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="7a98d-107">commonPreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="7a98d-108">Uma operação que prepara um estado de entrada fixo.</span><span class="sxs-lookup"><span data-stu-id="7a98d-108">An operation that prepares a fixed input state.</span></span>


### <a name="preparation1--qubit--unit--is-adj--ctl"></a><span data-ttu-id="7a98d-109">preparação1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="7a98d-109">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="7a98d-110">A primeira das duas operações de preparação do Estado a ser comparada.</span><span class="sxs-lookup"><span data-stu-id="7a98d-110">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit--is-adj--ctl"></a><span data-ttu-id="7a98d-111">preparação2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="7a98d-111">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="7a98d-112">A segunda das duas operações de preparação do Estado deve ser comparada.</span><span class="sxs-lookup"><span data-stu-id="7a98d-112">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="7a98d-113">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7a98d-113">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7a98d-114">O número de qubits em que `commonPreparation` `preparation1` , e todos `preparation2` agem.</span><span class="sxs-lookup"><span data-stu-id="7a98d-114">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="7a98d-115">n Medidas : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7a98d-115">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7a98d-116">O número de medições a utilizar na estimativa da sobreposição.</span><span class="sxs-lookup"><span data-stu-id="7a98d-116">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="7a98d-117">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7a98d-117">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="7a98d-118">Observações</span><span class="sxs-lookup"><span data-stu-id="7a98d-118">Remarks</span></span>

<span data-ttu-id="7a98d-119">Esta operação utiliza o teste Hadamard para encontrar a parte imaginária de $$ \start{align} \braket{\psi | V^{\dagger} U | \psi} \end{align} $$ where $\ket{\psi}$ é o estado preparado `commonPreparation` por, $U$ é a representação unitária da ação de `preparation1` , e onde $V$ corresponde a `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="7a98d-119">This operation uses the Hadamard test to find the imaginary part of $$ \begin{align} \braket{\psi | V^{\dagger} U | \psi} \end{align} $$ where $\ket{\psi}$ is the state prepared by `commonPreparation`, $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="references"></a><span data-ttu-id="7a98d-120">Referências</span><span class="sxs-lookup"><span data-stu-id="7a98d-120">References</span></span>

- <span data-ttu-id="7a98d-121">Aharonov *et al.* [quant-ph/0511096](https://arxiv.org/abs/quant-ph/0511096).</span><span class="sxs-lookup"><span data-stu-id="7a98d-121">Aharonov *et al.* [quant-ph/0511096](https://arxiv.org/abs/quant-ph/0511096).</span></span>

## <a name="see-also"></a><span data-ttu-id="7a98d-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7a98d-122">See Also</span></span>

- [<span data-ttu-id="7a98d-123">Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="7a98d-123">Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [<span data-ttu-id="7a98d-124">Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="7a98d-124">Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)