---
uid: Microsoft.Quantum.Characterization.EstimateFrequencyA
title: Estimativa OperaçãoFrequencyA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequencyA
qsharp.summary: Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: f12fc150de5bcea3d53ce88003c71976d8f2467f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204356"
---
# <a name="estimatefrequencya-operation"></a><span data-ttu-id="3bc49-102">Estimativa OperaçãoFrequencyA</span><span class="sxs-lookup"><span data-stu-id="3bc49-102">EstimateFrequencyA operation</span></span>

<span data-ttu-id="3bc49-103">Espaço de nome: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="3bc49-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="3bc49-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3bc49-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3bc49-105">Dada uma preparação que é adjacente e medição, estima a frequência com que essa medição sucede (devoluções) `Zero` através da realização de um determinado número de ensaios.</span><span class="sxs-lookup"><span data-stu-id="3bc49-105">Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.</span></span>

```qsharp
operation EstimateFrequencyA (preparation : (Qubit[] => Unit is Adj), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="3bc49-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3bc49-106">Input</span></span>

### <a name="preparation--qubit--unit--is-adj"></a><span data-ttu-id="3bc49-107">preparação: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="3bc49-107">preparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="3bc49-108">Uma operação contável $P$ que prepara um dado estado $\rho$ no seu registo de entrada.</span><span class="sxs-lookup"><span data-stu-id="3bc49-108">An adjointable operation $P$ that prepares a given state $\rho$ on its input register.</span></span>


### <a name="measurement--qubit--__invalidresult__"></a><span data-ttu-id="3bc49-109">medição: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="3bc49-109">measurement : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __invalid<Result>__</span></span> 

<span data-ttu-id="3bc49-110">Uma operação $M$ representando a medição de juros.</span><span class="sxs-lookup"><span data-stu-id="3bc49-110">An operation $M$ representing the measurement of interest.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="3bc49-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3bc49-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3bc49-112">O número de qubits em que a preparação e a medição de cada ato.</span><span class="sxs-lookup"><span data-stu-id="3bc49-112">The number of qubits on which the preparation and measurement each act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="3bc49-113">n Medidas : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3bc49-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3bc49-114">O número de vezes que a medição deve ser efetuada para estimar a frequência de juros.</span><span class="sxs-lookup"><span data-stu-id="3bc49-114">The number of times that the measurement should be performed in order to estimate the frequency of interest.</span></span>



## <a name="output--double"></a><span data-ttu-id="3bc49-115">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3bc49-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3bc49-116">Uma estimativa $\hat{p}$ da frequência com a qual $M(P(\ket{00 \cdots 0}\bra{00 \cdots 0})$ `Zero` devoluções, obtidas usando o estimador binomial imparcial $\hat{p} = \_ n{\uparrow} / \_ {{text{s}}}}}}}}}}}} onde $n \_ {\uparrow}$ é o número de `Zero` resultados observados.</span><span class="sxs-lookup"><span data-stu-id="3bc49-116">An estimate $\hat{p}$ of the frequency with which $M(P(\ket{00 \cdots 0}\bra{00 \cdots 0}))$ returns `Zero`, obtained using the unbiased binomial estimator $\hat{p} = n\_{\uparrow} / n\_{\text{measurements}}$, where $n\_{\uparrow}$ is the number of `Zero` results observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="3bc49-117">Observações</span><span class="sxs-lookup"><span data-stu-id="3bc49-117">Remarks</span></span>

<span data-ttu-id="3bc49-118">Para operações contíguas, certos pressupostos podem ser feitos tais como chamar a operação irá preparar os qubits exatamente para o mesmo estado, que permitem que as máquinas-alvo façam algumas otimizações de desempenho.</span><span class="sxs-lookup"><span data-stu-id="3bc49-118">For adjointable operations, certain assumptions can be made such like calling the operation will prepare the qubits to exactly the same state, which allow target machines to make some performance optimizations.</span></span>