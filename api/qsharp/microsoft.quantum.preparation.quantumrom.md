---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: Função QuantumROM
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 8ba5c6fab4abcfaee7233df9535f22eea5f68c28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722960"
---
# <a name="quantumrom-function"></a><span data-ttu-id="f4256-102">Função QuantumROM</span><span class="sxs-lookup"><span data-stu-id="f4256-102">QuantumROM function</span></span>

<span data-ttu-id="f4256-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="f4256-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="f4256-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f4256-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f4256-105">Usa a técnica de ROM quântica para representar uma determinada matriz de densidade.</span><span class="sxs-lookup"><span data-stu-id="f4256-105">Uses the Quantum ROM technique to represent a given density matrix.</span></span>

<span data-ttu-id="f4256-106">Dada a lista de coeficientes de $N$ $\alpha_j$, isto devolve uma $U$ unitária que usa a técnica Quantum-ROM para preparar uma aproximação $\tilde\rho\rho\rho\sum_{j=0}{N-1}p_j\ket{j}bra{j}$ da purificação da matriz de densidade $\rho=\sum_{j=0}{N-1 alpha_j} {\sum_k [\alpha_k]} \ket{j}\bra{j}$.</span><span class="sxs-lookup"><span data-stu-id="f4256-106">Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$.</span></span> <span data-ttu-id="f4256-107">Nesta aproximação, o erro $\epsilon$ é tal que $/p_j-\frac{[alpha_j]. {\sum_k [\alpha_k]. \le \epsilon / N$ e $ \| \tilde\rho - \rho \| \le \epsilon$.</span><span class="sxs-lookup"><span data-stu-id="f4256-107">In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$.</span></span> <span data-ttu-id="f4256-108">Por outras palavras, $$ \start{align} U\ket {0} ^{\lceil\log_2 N\rceil}\ket {0} ^{m}={sum_ j=0}^{N-1}\sqrt{p_j} \ket{j}ket{ket{\ket{\text{garbage}_j}.</span><span class="sxs-lookup"><span data-stu-id="f4256-108">In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}.</span></span>
<span data-ttu-id="f4256-109">\end{align} $$</span><span class="sxs-lookup"><span data-stu-id="f4256-109">\end{align} $$</span></span>

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a><span data-ttu-id="f4256-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="f4256-110">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="f4256-111">targetError : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f4256-111">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f4256-112">O erro do alvo $\epsilon$.</span><span class="sxs-lookup"><span data-stu-id="f4256-112">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="f4256-113">coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="f4256-113">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="f4256-114">Conjunto de coeficientes de $N$ especificando a probabilidade dos estados de base.</span><span class="sxs-lookup"><span data-stu-id="f4256-114">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="f4256-115">Números negativos $-\alpha_j$ serão tratados como positivos $\alpha_j.$.</span><span class="sxs-lookup"><span data-stu-id="f4256-115">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--intintintdoublelittleendianqubit--unit-adj--ctl"></a><span data-ttu-id="f4256-116">Saída :[(Int (Int](xref:microsoft.quantum.lang-ref.int),[Int),](xref:microsoft.quantum.lang-ref.int)[Double](xref:microsoft.quantum.lang-ref.double)[(LittleEndian,](xref:Microsoft.Quantum.Arithmetic.LittleEndian)[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)[Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f4256-116">Output : (([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double),([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)</span></span>

## <a name="first-parameter"></a><span data-ttu-id="f4256-117">Primeiro parâmetro</span><span class="sxs-lookup"><span data-stu-id="f4256-117">First parameter</span></span>

<span data-ttu-id="f4256-118">Um tuple `(x,(y,z))` onde está o número total de `x = y + z` qubits atribuídos, `y` é o número de qubits para o `LittleEndian` registo, e é o número de `z` qubits de lixo.</span><span class="sxs-lookup"><span data-stu-id="f4256-118">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="f4256-119">Segundo parâmetro</span><span class="sxs-lookup"><span data-stu-id="f4256-119">Second parameter</span></span>

<span data-ttu-id="f4256-120">A norma única $\sum_j [\alpha_j] do conjunto de coeficientes.</span><span class="sxs-lookup"><span data-stu-id="f4256-120">The one-norm $\sum_j |\alpha_j|$ of the coefficient array.</span></span>

## <a name="third-parameter"></a><span data-ttu-id="f4256-121">Terceiro parâmetro</span><span class="sxs-lookup"><span data-stu-id="f4256-121">Third parameter</span></span>

<span data-ttu-id="f4256-122">O $U unitário.</span><span class="sxs-lookup"><span data-stu-id="f4256-122">The unitary $U$.</span></span>

## <a name="references"></a><span data-ttu-id="f4256-123">Referências</span><span class="sxs-lookup"><span data-stu-id="f4256-123">References</span></span>

- <span data-ttu-id="f4256-124">Codificação de Espectros Eletrónicos em Circuitos Quânticos com Complexidade Linear T Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="f4256-124">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>