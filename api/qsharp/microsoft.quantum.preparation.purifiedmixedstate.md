---
uid: Microsoft.Quantum.Preparation.PurifiedMixedState
title: Função Do Estado-Metado Purificado
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedState
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed state.\rA \"purified mixed state\" refers to states of the form |ψ⟩ = Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |garbageᵢ⟩ specified by a vector of\rcoefficients {\U0001D45Dᵢ}. States of this form can be reduced to mixed states ρ ≔ \U0001D45Dᵢ |\U0001D456⟩⟨\U0001D456| by tracing over the \"garbage\"\rregister (that is, a mixed state that is diagonal in the computational basis).\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: 594a1d9fa674e457ab88072ade4198283b677af6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854294"
---
# <a name="purifiedmixedstate-function"></a><span data-ttu-id="72c86-102">Função Do Estado-Metado Purificado</span><span class="sxs-lookup"><span data-stu-id="72c86-102">PurifiedMixedState function</span></span>

<span data-ttu-id="72c86-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="72c86-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="72c86-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="72c86-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="72c86-105">Devolve uma operação que prepara uma purificação de um dado estado misto.</span><span class="sxs-lookup"><span data-stu-id="72c86-105">Returns an operation that prepares a a purification of a given mixed state.</span></span>
<span data-ttu-id="72c86-106">Um "estado misto purificado" refere-se aos estados da forma |ψ⟩ = Σi √pi |i⟩ |garbagei⟩ especificado por um vetor de coeficientes {pi}.</span><span class="sxs-lookup"><span data-stu-id="72c86-106">A "purified mixed state" refers to states of the form |ψ⟩ = Σᵢ √𝑝ᵢ |𝑖⟩ |garbageᵢ⟩ specified by a vector of coefficients {𝑝ᵢ}.</span></span> <span data-ttu-id="72c86-107">Os estados desta forma podem ser reduzidos a estados mistos ≔ pi |i⟩⟨i| rastreando o registo "lixo" (isto é, um estado misto que é diagonal na base computacional).</span><span class="sxs-lookup"><span data-stu-id="72c86-107">States of this form can be reduced to mixed states ρ ≔ 𝑝ᵢ |𝑖⟩⟨𝑖| by tracing over the "garbage" register (that is, a mixed state that is diagonal in the computational basis).</span></span>

<span data-ttu-id="72c86-108">Veja https://arxiv.org/pdf/1805.03662.pdf?page=15 mais na discussão.</span><span class="sxs-lookup"><span data-stu-id="72c86-108">See https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion.</span></span>

```qsharp
function PurifiedMixedState (targetError : Double, coefficients : Double[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a><span data-ttu-id="72c86-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="72c86-109">Description</span></span>

<span data-ttu-id="72c86-110">Usa a técnica de ROM quântica para representar uma determinada matriz de densidade, devolvendo essa representação como uma operação de preparação do estado.</span><span class="sxs-lookup"><span data-stu-id="72c86-110">Uses the Quantum ROM technique to represent a given density matrix, returning that representation as a state preparation operation.</span></span>

<span data-ttu-id="72c86-111">Em particular, dada uma lista de coeficientes de $N$ $\alpha_j$, esta função devolve uma operação que utiliza a técnica de ROM quântica para preparar uma aproximação $$ \start{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \0Ket{j}\bra{j} \end{align} $$ do estado misto $$ \start{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|} {\sum_k |\alpha_k|} \ket{j}\bra{j}, \end{align} $$ onde cada $p_j$ é uma aproximação ao coeficiente dado $\alpha_j$ tal que $$ \start{align} \left| p_j - \frac{|\alpha_j| } { \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ por cada $j$.</span><span class="sxs-lookup"><span data-stu-id="72c86-111">In particular, given a list of $N$ coefficients $\alpha_j$, this function returns an operation that uses the Quantum ROM technique to prepare an approximation $$ \begin{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \ket{j}\bra{j} \end{align} $$ of the mixed state $$ \begin{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|}{\sum_k |\alpha_k|} \ket{j}\bra{j}, \end{align} $$ where each $p_j$ is an approximation to the given coefficient $\alpha_j$ such that $$ \begin{align} \left| p_j - \frac{ |\alpha_j| }{ \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ for each $j$.</span></span>

<span data-ttu-id="72c86-112">Quando passou um registo de índices e um registo de qubits de lixo, inicialmente no estado {0} $\ket \ket {00\cdots 0}, a operação devolvida prepara ambos os registos na purificação de $\tilde \rho$, \$ \start{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j}ket{\text{garbage}_j}, \end{align}</span><span class="sxs-lookup"><span data-stu-id="72c86-112">When passed an index register and a register of garbage qubits, initially in the state $\ket{0} \ket{00\cdots 0}, the returned operation prepares both registers into the purification of $\tilde \rho$, $$ \begin{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage}_j}, \end{align} $$ such that resetting and deallocating the garbage register enacts the desired preparation to within the target error $\epsilon$.</span></span>

## <a name="input"></a><span data-ttu-id="72c86-113">Entrada</span><span class="sxs-lookup"><span data-stu-id="72c86-113">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="72c86-114">targetError : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="72c86-114">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="72c86-115">O erro do alvo $\epsilon$.</span><span class="sxs-lookup"><span data-stu-id="72c86-115">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="72c86-116">coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="72c86-116">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="72c86-117">Conjunto de coeficientes de $N$ especificando a probabilidade dos estados de base.</span><span class="sxs-lookup"><span data-stu-id="72c86-117">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="72c86-118">Números negativos $-\alpha_j$ serão tratados como positivos $|alpha_j|$.</span><span class="sxs-lookup"><span data-stu-id="72c86-118">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--mixedstatepreparation"></a><span data-ttu-id="72c86-119">Saída : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span><span class="sxs-lookup"><span data-stu-id="72c86-119">Output : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span></span>

<span data-ttu-id="72c86-120">Uma operação que prepara $\tilde \rho$ como purificação para um índice conjunto e registo de lixo.</span><span class="sxs-lookup"><span data-stu-id="72c86-120">An operation that prepares $\tilde \rho$ as a purification onto a joint index and garbage register.</span></span>

## <a name="example"></a><span data-ttu-id="72c86-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="72c86-121">Example</span></span>

<span data-ttu-id="72c86-122">O seguinte corte de código prepara uma purificação do estado $\rho=\rho=\sum_{j=0}^ {4} \frac{|alpha_j|} {\sum_k |\alpha_k|} \ket{j}\bra{j}$, onde $\vec\alpha=(1.0, 2.0, 3.0, 4.0, 5.0)$, e o erro alvo é $10^ {-3} $:</span><span class="sxs-lookup"><span data-stu-id="72c86-122">The following code snippet prepares an purification of the $3$-qubit state $\rho=\sum_{j=0}^{4}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$, where $\vec\alpha=(1.0, 2.0, 3.0, 4.0, 5.0)$, and the target error is $10^{-3}$:</span></span>

```qsharp
let coefficients = [1.0, 2.0, 3.0, 4.0, 5.0];
let targetError = 1e-3;
let purifiedState = PurifiedMixedState(targetError, coefficients);
using (indexRegister = Qubit[purifiedState::Requirements::NIndexQubits]) {
    using (garbageRegister = Qubit[purifiedState::Requirements::NGarbageQubits]) {
        purifiedState::Prepare(LittleEndian(indexRegister), new Qubit[0], garbageRegister);
    }
}
```

## <a name="remarks"></a><span data-ttu-id="72c86-123">Observações</span><span class="sxs-lookup"><span data-stu-id="72c86-123">Remarks</span></span>

<span data-ttu-id="72c86-124">Os coeficientes fornecidos a esta operação são normalizados seguindo a norma 1, de modo que os coeficientes são sempre considerados para descrever uma distribuição de probabilidades categóricas válida.</span><span class="sxs-lookup"><span data-stu-id="72c86-124">The coefficients provided to this operation are normalized following the 1-norm, such that the coefficients are always considered to describe a valid categorical probability distribution.</span></span>

## <a name="references"></a><span data-ttu-id="72c86-125">Referências</span><span class="sxs-lookup"><span data-stu-id="72c86-125">References</span></span>

- <span data-ttu-id="72c86-126">Codificação de Espectros Eletrónicos em Circuitos Quânticos com Complexidade Linear T Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="72c86-126">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>

## <a name="see-also"></a><span data-ttu-id="72c86-127">Consulte também</span><span class="sxs-lookup"><span data-stu-id="72c86-127">See Also</span></span>

- [<span data-ttu-id="72c86-128">Microsoft.Quantum.Preparation.PurifiedMixedStateWithData</span><span class="sxs-lookup"><span data-stu-id="72c86-128">Microsoft.Quantum.Preparation.PurifiedMixedStateWithData</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedStateWithData)