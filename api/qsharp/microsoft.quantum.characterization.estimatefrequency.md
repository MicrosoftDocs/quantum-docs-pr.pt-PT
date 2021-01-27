---
uid: Microsoft.Quantum.Characterization.EstimateFrequency
title: Estimativa OperaçãoFrequency
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequency
qsharp.summary: Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 1e044a08718e02d673edab1d6b9d16d7f09618dc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851890"
---
# <a name="estimatefrequency-operation"></a><span data-ttu-id="1b3e5-102">Estimativa OperaçãoFrequency</span><span class="sxs-lookup"><span data-stu-id="1b3e5-102">EstimateFrequency operation</span></span>

<span data-ttu-id="1b3e5-103">Espaço de nome: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="1b3e5-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="1b3e5-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1b3e5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1b3e5-105">Dada a preparação e medição, estima a frequência com que essa medição sucede (devoluções) `Zero` através da realização de um determinado número de ensaios.</span><span class="sxs-lookup"><span data-stu-id="1b3e5-105">Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.</span></span>

```qsharp
operation EstimateFrequency (preparation : (Qubit[] => Unit), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="1b3e5-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1b3e5-106">Input</span></span>

### <a name="preparation--qubit--unit"></a><span data-ttu-id="1b3e5-107">preparação: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="1b3e5-107">preparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="1b3e5-108">Uma operação $P$ que prepara um dado estado $\rho$ no seu registo de entradas.</span><span class="sxs-lookup"><span data-stu-id="1b3e5-108">An operation $P$ that prepares a given state $\rho$ on its input register.</span></span>


### <a name="measurement--qubit--__invalidresult__"></a><span data-ttu-id="1b3e5-109">medição: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="1b3e5-109">measurement : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __invalid<Result>__</span></span> 

<span data-ttu-id="1b3e5-110">Uma operação $M$ representando a medição de juros.</span><span class="sxs-lookup"><span data-stu-id="1b3e5-110">An operation $M$ representing the measurement of interest.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="1b3e5-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1b3e5-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1b3e5-112">O número de qubits em que a preparação e a medição de cada ato.</span><span class="sxs-lookup"><span data-stu-id="1b3e5-112">The number of qubits on which the preparation and measurement each act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="1b3e5-113">n Medidas : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1b3e5-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1b3e5-114">O número de vezes que a medição deve ser efetuada para estimar a frequência de juros.</span><span class="sxs-lookup"><span data-stu-id="1b3e5-114">The number of times that the measurement should be performed in order to estimate the frequency of interest.</span></span>



## <a name="output--double"></a><span data-ttu-id="1b3e5-115">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1b3e5-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1b3e5-116">Uma estimativa $\hat{p}$ da frequência com a qual $M(P(\ket{00 \cdots 0}\bra{00 \cdots 0})$ `Zero` devoluções, obtidas usando o estimador binomial imparcial $\hat{p} = \_ n{\uparrow} / \_ {{text{s}} onde $n \_ {\uparrow}$ é o número de `Zero` resultados observados.</span><span class="sxs-lookup"><span data-stu-id="1b3e5-116">An estimate $\hat{p}$ of the frequency with which $M(P(\ket{00 \cdots 0}\bra{00 \cdots 0}))$ returns `Zero`, obtained using the unbiased binomial estimator $\hat{p} = n\_{\uparrow} / n\_{\text{measurements}}$, where $n\_{\uparrow}$ is the number of `Zero` results observed.</span></span>

<span data-ttu-id="1b3e5-117">Isto é particularmente importante para as máquinas-alvo que respeitam as limitações físicas, de modo a que as probabilidades não possam ser medidas.</span><span class="sxs-lookup"><span data-stu-id="1b3e5-117">This is particularly important on target machines which respect physical limitations, such that probabilities cannot be measured.</span></span>