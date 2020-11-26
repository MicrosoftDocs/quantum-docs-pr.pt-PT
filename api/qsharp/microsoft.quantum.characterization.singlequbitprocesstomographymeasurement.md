---
uid: Microsoft.Quantum.Characterization.SingleQubitProcessTomographyMeasurement
title: Operação singleQubitProcessTomographyMeasurement
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: SingleQubitProcessTomographyMeasurement
qsharp.summary: Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.
ms.openlocfilehash: 3756040df8e34ecee1e968428b08387e0096ab7b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204203"
---
# <a name="singlequbitprocesstomographymeasurement-operation"></a><span data-ttu-id="6bb60-102">Operação singleQubitProcessTomographyMeasurement</span><span class="sxs-lookup"><span data-stu-id="6bb60-102">SingleQubitProcessTomographyMeasurement operation</span></span>

<span data-ttu-id="6bb60-103">Espaço de nome: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="6bb60-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="6bb60-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6bb60-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6bb60-105">Realiza uma medição de tomografia de processo de um único qubit na base Pauli, dado um determinado canal de interesse.</span><span class="sxs-lookup"><span data-stu-id="6bb60-105">Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.</span></span>

```qsharp
operation SingleQubitProcessTomographyMeasurement (preparation : Pauli, measurement : Pauli, channel : (Qubit => Unit)) : Result
```


## <a name="input"></a><span data-ttu-id="6bb60-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6bb60-106">Input</span></span>

### <a name="preparation--pauli"></a><span data-ttu-id="6bb60-107">preparação : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="6bb60-107">preparation : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="6bb60-108">O elemento base Pauli $P$ em que um qubit deve ser preparado.</span><span class="sxs-lookup"><span data-stu-id="6bb60-108">The Pauli basis element $P$ in which a qubit is to be prepared.</span></span>


### <a name="measurement--pauli"></a><span data-ttu-id="6bb60-109">medição : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="6bb60-109">measurement : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="6bb60-110">O elemento base Pauli $Q$ em que um qubit deve ser medido.</span><span class="sxs-lookup"><span data-stu-id="6bb60-110">The Pauli basis element $Q$ in which a qubit is to be measured.</span></span>


### <a name="channel--qubit--unit"></a><span data-ttu-id="6bb60-111">canal : [Unidade Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6bb60-111">channel : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6bb60-112">Um único canal qubit $\Lambda$ cujo comportamento está a ser estimado com tomografia de processo.</span><span class="sxs-lookup"><span data-stu-id="6bb60-112">A single qubit channel $\Lambda$ whose behavior is being estimated with process tomography.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="6bb60-113">Saída: __<Result> inválida__</span><span class="sxs-lookup"><span data-stu-id="6bb60-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="6bb60-114">O Resultado `Zero` com probabilidade $$ \begin{align} \Pr (\texttt{Zero} / \Lambda; P, Q) = \operatorname{Tr}\left\ frac{\boldone + Q} {2} \Lambda\left[ \frac{\boldone + P} {2} \direita).</span><span class="sxs-lookup"><span data-stu-id="6bb60-114">The Result `Zero` with probability $$ \begin{align} \Pr(\texttt{Zero} | \Lambda; P, Q) = \operatorname{Tr}\left( \frac{\boldone + Q}{2} \Lambda\left[ \frac{\boldone + P}{2} \right] \right).</span></span>
<span data-ttu-id="6bb60-115">\end{align} $$</span><span class="sxs-lookup"><span data-stu-id="6bb60-115">\end{align} $$</span></span>

## <a name="remarks"></a><span data-ttu-id="6bb60-116">Observações</span><span class="sxs-lookup"><span data-stu-id="6bb60-116">Remarks</span></span>

<span data-ttu-id="6bb60-117">A distribuição sobre os resultados devolvidos por esta operação é um caso especial de tomografia estatal de dois qubits.</span><span class="sxs-lookup"><span data-stu-id="6bb60-117">The distribution over results returned by this operation is a special case of two-qubit state tomography.</span></span> <span data-ttu-id="6bb60-118">Let $\rho = J(\Lambda) / 2$ seja o estado Choi-Jamiłkowski por $\Lambda$.</span><span class="sxs-lookup"><span data-stu-id="6bb60-118">Let $\rho = J(\Lambda) / 2$ be the Choi–Jamiłkowski state for $\Lambda$.</span></span> <span data-ttu-id="6bb60-119">Em seguida, a distribuição acima é idêntica a $$ \start{align} \Pr (\texttt{Zero} / \rho; M) = \operatorname{Tr}(M\rho), \end{align} $$ where $M = 2 (\boldone + P)^\mathrm{T} / 2 \cdot (\boldone + Q) / 2$ é a medida eficaz correspondente a $P$ e $Q$.</span><span class="sxs-lookup"><span data-stu-id="6bb60-119">Then, the distribution above is identical to $$ \begin{align} \Pr(\texttt{Zero} | \rho; M) = \operatorname{Tr}(M \rho), \end{align} $$ where $M = 2 (\boldone + P)^\mathrm{T} / 2 \cdot (\boldone + Q) / 2$ is the effective measurement corresponding to $P$ and $Q$.</span></span>