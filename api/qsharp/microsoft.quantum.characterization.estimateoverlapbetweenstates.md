---
uid: Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates
title: EstimativasOverlapBetweenStates operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.
ms.openlocfilehash: e083d6da13b0780905bf365c7a428ebc9666ce9e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839722"
---
# <a name="estimateoverlapbetweenstates-operation"></a><span data-ttu-id="118a2-102">EstimativasOverlapBetweenStates operação</span><span class="sxs-lookup"><span data-stu-id="118a2-102">EstimateOverlapBetweenStates operation</span></span>

<span data-ttu-id="118a2-103">Espaço de nome: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="118a2-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="118a2-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="118a2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="118a2-105">Tendo em conta duas operações que cada uma prepara cópias de um Estado, estima a sobreposição quadrada entre os Estados preparados por cada operação.</span><span class="sxs-lookup"><span data-stu-id="118a2-105">Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateOverlapBetweenStates (preparation1 : (Qubit[] => Unit is Adj), preparation2 : (Qubit[] => Unit is Adj), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="118a2-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="118a2-106">Input</span></span>

### <a name="preparation1--qubit--unit--is-adj"></a><span data-ttu-id="118a2-107">preparação1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="118a2-107">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="118a2-108">A primeira das duas operações de preparação do Estado a ser comparada.</span><span class="sxs-lookup"><span data-stu-id="118a2-108">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit--is-adj"></a><span data-ttu-id="118a2-109">preparação2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="118a2-109">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="118a2-110">A segunda das duas operações de preparação do Estado deve ser comparada.</span><span class="sxs-lookup"><span data-stu-id="118a2-110">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="118a2-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="118a2-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="118a2-112">O número de qubits em que `commonPreparation` `preparation1` , e todos `preparation2` agem.</span><span class="sxs-lookup"><span data-stu-id="118a2-112">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="118a2-113">n Medidas : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="118a2-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="118a2-114">O número de medições a utilizar na estimativa da sobreposição.</span><span class="sxs-lookup"><span data-stu-id="118a2-114">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="118a2-115">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="118a2-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="118a2-116">Observações</span><span class="sxs-lookup"><span data-stu-id="118a2-116">Remarks</span></span>

<span data-ttu-id="118a2-117">Esta operação utiliza o teste SWAP para encontrar $$ \start{align} \esquerda| \braket{00\cdots 0 | V^{\dagger} U | 00\cdots 0} \direita|^2 \end{align} $$ onde $U$ é a representação unitária da ação de `preparation1` , e onde $V$ corresponde a `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="118a2-117">This operation uses the SWAP test to find $$ \begin{align} \left| \braket{00\cdots 0 | V^{\dagger} U | 00\cdots 0} \right|^2 \end{align} $$ where $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="see-also"></a><span data-ttu-id="118a2-118">Consulte também</span><span class="sxs-lookup"><span data-stu-id="118a2-118">See Also</span></span>

- [<span data-ttu-id="118a2-119">Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="118a2-119">Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [<span data-ttu-id="118a2-120">Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="118a2-120">Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)