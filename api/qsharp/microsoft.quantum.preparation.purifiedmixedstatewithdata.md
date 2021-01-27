---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateWithData
title: Função PurifiedMixedStateWithData
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateWithData
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed\rstate, entangled with a register representing a given collection of data.\rA \"purified mixed state with data\" refers to a state of the form Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |\U0001D465ᵢ⟩ |garbageᵢ⟩,\rwhere each \U0001D465ᵢ is a bitstring encoding additional data associated with the register |\U0001D456⟩.\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: fc7bf8e6157af079ae4233ef45e67ce8ddfb8fe3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854286"
---
# <a name="purifiedmixedstatewithdata-function"></a><span data-ttu-id="5fe6b-102">Função PurifiedMixedStateWithData</span><span class="sxs-lookup"><span data-stu-id="5fe6b-102">PurifiedMixedStateWithData function</span></span>

<span data-ttu-id="5fe6b-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="5fe6b-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="5fe6b-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5fe6b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5fe6b-105">Devolve uma operação que prepara uma purificação de um dado estado misto, enredada num registo que representa uma determinada recolha de dados.</span><span class="sxs-lookup"><span data-stu-id="5fe6b-105">Returns an operation that prepares a a purification of a given mixed state, entangled with a register representing a given collection of data.</span></span>
<span data-ttu-id="5fe6b-106">Um "estado misto purificado com dados" refere-se a um estado do formulário Σi √pi |i⟩ |xi⟩ |garbagei⟩, onde cada xi é um bitstring codificando dados adicionais associados ao registo |i⟩.</span><span class="sxs-lookup"><span data-stu-id="5fe6b-106">A "purified mixed state with data" refers to a state of the form Σᵢ √𝑝ᵢ |𝑖⟩ |𝑥ᵢ⟩ |garbageᵢ⟩, where each 𝑥ᵢ is a bitstring encoding additional data associated with the register |𝑖⟩.</span></span>

<span data-ttu-id="5fe6b-107">Veja https://arxiv.org/pdf/1805.03662.pdf?page=15 mais na discussão.</span><span class="sxs-lookup"><span data-stu-id="5fe6b-107">See https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion.</span></span>

```qsharp
function PurifiedMixedStateWithData (targetError : Double, coefficients : (Double, Bool[])[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a><span data-ttu-id="5fe6b-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="5fe6b-108">Description</span></span>

<span data-ttu-id="5fe6b-109">Usa a técnica de ROM quântica para representar uma determinada matriz de densidade, devolvendo essa representação como uma operação de preparação do estado.</span><span class="sxs-lookup"><span data-stu-id="5fe6b-109">Uses the Quantum ROM technique to represent a given density matrix, returning that representation as a state preparation operation.</span></span>

<span data-ttu-id="5fe6b-110">Em particular, dada uma lista de coeficientes de $N$ $\alpha_j$, e um bitstring $\vec{x}_j$ associado a cada coeficiente, esta função devolve uma operação que usa a técnica de ROM quântica para preparar uma aproximação $$ \start{alinhar} \tilde\rho = \soma_{j = 0}^{N - 1} p_j \ket{j}bra{j} \otimes \ket{\vec{x}_j}\bra{\vec{x}_j} \end{align} $$ do estado misto $$ \begin{align} \rho = \soma_{j = 0}^{N-1}\ frac{|alpha_j|} {\sum_k |\alpha_k|} \ket{j}\bra{j} \otimes \ket{\vec{x}_j}}\bra{\vec{x}_j, \end{align} $$ onde cada $p_j$ é uma aproximação ao coeficiente dado $\alpha_j$ tal que $$ start \{|{} p_j - \frac{|\alpha_j| } { \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ por cada $j$.</span><span class="sxs-lookup"><span data-stu-id="5fe6b-110">In particular, given a list of $N$ coefficients $\alpha_j$, and a bitstring $\vec{x}_j$ associated with each coefficient, this function returns an operation that uses the Quantum ROM technique to prepare an approximation $$ \begin{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x}_j}\bra{\vec{x}_j} \end{align} $$ of the mixed state $$ \begin{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|}{\sum_k |\alpha_k|} \ket{j}\bra{j} \otimes \ket{\vec{x}_j}\bra{\vec{x}_j}, \end{align} $$ where each $p_j$ is an approximation to the given coefficient $\alpha_j$ such that $$ \begin{align} \left| p_j - \frac{ |\alpha_j| }{ \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ for each $j$.</span></span>

<span data-ttu-id="5fe6b-111">Quando passou um registo de índices e um registo de qubits de lixo, inicialmente no estado {0} $\ket \ket {00\cdots 0}, a operação devolvida prepara ambos os registos na purificação de $\tilde \rho$, \$ \start{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j} \ket{\vec{x}}_j} \ket{\text{garbage}_j}, \end{align} $$ tal que repor e negociar o lixo regista a preparação desejada para dentro do erro-alvo $\eps</span><span class="sxs-lookup"><span data-stu-id="5fe6b-111">When passed an index register and a register of garbage qubits, initially in the state $\ket{0} \ket{00\cdots 0}, the returned operation prepares both registers into the purification of $\tilde \rho$, $$ \begin{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j} \ket{\vec{x}_j} \ket{\text{garbage}_j}, \end{align} $$ such that resetting and deallocating the garbage register enacts the desired preparation to within the target error $\epsilon$.</span></span>

## <a name="input"></a><span data-ttu-id="5fe6b-112">Entrada</span><span class="sxs-lookup"><span data-stu-id="5fe6b-112">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="5fe6b-113">targetError : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5fe6b-113">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5fe6b-114">O erro do alvo $\epsilon$.</span><span class="sxs-lookup"><span data-stu-id="5fe6b-114">The target error $\epsilon$.</span></span>


### <a name="coefficients--doublebool"></a><span data-ttu-id="5fe6b-115">coeficientes :[(Duplo,](xref:microsoft.quantum.lang-ref.double)[Bool](xref:microsoft.quantum.lang-ref.bool)[][].</span><span class="sxs-lookup"><span data-stu-id="5fe6b-115">coefficients : ([Double](xref:microsoft.quantum.lang-ref.double),[Bool](xref:microsoft.quantum.lang-ref.bool)[])[]</span></span>

<span data-ttu-id="5fe6b-116">Array de coeficientes de $N$ especificando a probabilidade de estados de base, juntamente com o bitstring $\vec{x}_j$ associado a cada coeficiente.</span><span class="sxs-lookup"><span data-stu-id="5fe6b-116">Array of $N$ coefficients specifying the probability of basis states, along with the bitstring $\vec{x}_j$ associated with each coefficient.</span></span>
<span data-ttu-id="5fe6b-117">Números negativos $-\alpha_j$ serão tratados como positivos $|alpha_j|$.</span><span class="sxs-lookup"><span data-stu-id="5fe6b-117">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--mixedstatepreparation"></a><span data-ttu-id="5fe6b-118">Saída : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span><span class="sxs-lookup"><span data-stu-id="5fe6b-118">Output : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span></span>

<span data-ttu-id="5fe6b-119">Uma operação que prepara $\tilde \rho$ como purificação para um índice conjunto e registo de lixo.</span><span class="sxs-lookup"><span data-stu-id="5fe6b-119">An operation that prepares $\tilde \rho$ as a purification onto a joint index and garbage register.</span></span>

## <a name="remarks"></a><span data-ttu-id="5fe6b-120">Observações</span><span class="sxs-lookup"><span data-stu-id="5fe6b-120">Remarks</span></span>

<span data-ttu-id="5fe6b-121">Os coeficientes fornecidos a esta operação são normalizados seguindo a norma 1, de modo que os coeficientes são sempre considerados para descrever uma distribuição de probabilidades categóricas válida.</span><span class="sxs-lookup"><span data-stu-id="5fe6b-121">The coefficients provided to this operation are normalized following the 1-norm, such that the coefficients are always considered to describe a valid categorical probability distribution.</span></span>

## <a name="references"></a><span data-ttu-id="5fe6b-122">Referências</span><span class="sxs-lookup"><span data-stu-id="5fe6b-122">References</span></span>

- <span data-ttu-id="5fe6b-123">Codificação de Espectros Eletrónicos em Circuitos Quânticos com Complexidade Linear T Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="5fe6b-123">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>

## <a name="see-also"></a><span data-ttu-id="5fe6b-124">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5fe6b-124">See Also</span></span>

- [<span data-ttu-id="5fe6b-125">Microsoft.Quantum.Preparation.PurifiedMixedState</span><span class="sxs-lookup"><span data-stu-id="5fe6b-125">Microsoft.Quantum.Preparation.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)