---
title: Simulando o Hamiltonian Dynamics | Microsoft Docs
description: Simulando documentos conceituais do Hamiltonian Dynamics
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
ms.openlocfilehash: 905b03478d453e475fc1e49ea5f88dd0cd2704bc
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184071"
---
# <a name="simulating-hamiltonian-dynamics"></a><span data-ttu-id="2ab7a-103">Simulando o Hamiltonian Dynamics</span><span class="sxs-lookup"><span data-stu-id="2ab7a-103">Simulating Hamiltonian Dynamics</span></span>

<span data-ttu-id="2ab7a-104">Depois que o Hamiltonian tiver sido expresso como uma soma dos operadores elementares, o Dynamics poderá então ser compilado em operações fundamentais de portão usando uma série de técnicas bem conhecidas.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-104">Once the Hamiltonian has been expressed as a sum of elementary operators the dynamics can then be compiled into fundamental gate operations using a host of well-known techniques.</span></span>
<span data-ttu-id="2ab7a-105">Três abordagens eficientes incluem as fórmulas Trotter – Suzuki, combinações lineares de unidades e qubitization.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-105">Three efficient approaches include are Trotter–Suzuki formulas, linear combinations of unitaries, and qubitization.</span></span>
<span data-ttu-id="2ab7a-106">Explicamos essas três abordagens abaixo e fornecemos exemplos concretos de Q # sobre como implementar esses métodos usando a biblioteca de simulação de Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-106">We explain these three approaches below and give concrete Q# examples of how to implement these methods using the Hamiltonian simulation library.</span></span>


## <a name="trottersuzuki-formulas"></a><span data-ttu-id="2ab7a-107">Trotter – fórmulas Suzuki</span><span class="sxs-lookup"><span data-stu-id="2ab7a-107">Trotter–Suzuki Formulas</span></span>
<span data-ttu-id="2ab7a-108">A ideia por trás das fórmulas Trotter – Suzuki é simples: expresse a Hamiltonian como uma soma de fácil de simular Hamiltonians e, em seguida, aproximar a evolução total como uma sequência dessas evoluções mais simples.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-108">The idea behind Trotter–Suzuki formulas is simple: express the Hamiltonian as a sum of easy to simulate Hamiltonians and then approximate the total evolution as a sequence of these simpler evolutions.</span></span>
<span data-ttu-id="2ab7a-109">Em particular, permita que $H = \sum_{j = 1} ^ m H_j $ seja o Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-109">In particular, let $H=\sum_{j=1}^m H_j$ be the Hamiltonian.</span></span>
<span data-ttu-id="2ab7a-110">Em seguida, $ $ e ^ {-i\sum_ {j = 1} ^ m H_j t} = \prod_{j = 1} ^ m e ^ {-iH_j t} + O (m ^ 2 t ^ 2), $ $, o que significa que, se $t \ll $1, o erro nessa aproximação se tornará insignificante.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-110">Then, $$ e^{-i\sum_{j=1}^m H_j t} =\prod_{j=1}^m e^{-iH_j t} + O(m^2 t^2), $$ which is to say that, if $t\ll 1$, then the error in this approximation becomes negligible.</span></span>
<span data-ttu-id="2ab7a-111">Observe que se $e ^ {-i H} $ fosse um exponencial comum, o erro nessa aproximação não seria $O (m ^ 2 t ^ 2) $: ele seria zero.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-111">Note that if $e^{-i H t}$ were an ordinary exponential then the error in this approximation would not be $O(m^2 t^2)$: it would be zero.</span></span>
<span data-ttu-id="2ab7a-112">Esse erro ocorre porque $e ^ {-iHt} $ é um exponencial de operador e, como resultado, há um erro incorrido ao usar essa fórmula devido ao fato de que os termos $H _J $ não m (*ou seja*, $H _J H_k \Ne H_k H_j $ em geral).</span><span class="sxs-lookup"><span data-stu-id="2ab7a-112">This error occurs because $e^{-iHt}$ is an operator exponential and as a result there is an error incurred when using this formula due to the fact that the $H_j$ terms do not commute (*i.e.*, $H_j H_k \ne H_k H_j$ in general).</span></span>

<span data-ttu-id="2ab7a-113">Se $t $ for grande, as fórmulas Trotter – Suzuki ainda poderão ser usadas para simular o Dynamics com precisão, dividindo-o em uma sequência de etapas curtas.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-113">If $t$ is large, Trotter–Suzuki formulas can still be used to simulate the dynamics accurately by breaking it up into a sequence of short time-steps.</span></span>
<span data-ttu-id="2ab7a-114">Deixe $r $ seja o número de etapas executadas na evolução do tempo.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-114">Let $r$ be the number of steps taken in the time evolution.</span></span>
<span data-ttu-id="2ab7a-115">Em seguida, temos o $ $ e ^ {-i\sum_ {j = 1} ^ m H_j t} = \left (\prod_{j = 1} ^ m e ^ {-iH_j t/r} \ right) ^ r + O (m ^ 2 t ^ 2/r), $ $, que implica que se $r $ for dimensionado como $m ^ 2 t ^ 2/\ épsilon $, o erro poderá ser feito no máximo $ \epsilon $ para qualquer $ \epsilon > 0 $.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-115">Then, we have that $$ e^{-i\sum_{j=1}^m H_j t} =\left(\prod_{j=1}^m e^{-iH_j t/r}\right)^r + O(m^2 t^2/r), $$ which implies that if $r$ scales as $m^2 t^2/\epsilon$ then the error can be made at most $\epsilon$ for any $\epsilon>0$.</span></span>

<span data-ttu-id="2ab7a-116">As aproximações mais precisas podem ser criadas com a construção de uma sequência de exponenciais de operador, de modo que os termos de erro sejam cancelados.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-116">More accurate approximations can be built by constructing a sequence of operator exponentials such that the error terms cancel.</span></span>
<span data-ttu-id="2ab7a-117">A fórmula mais simples, a fórmula Trotter simétrica ou a divisão Strang, usa a forma $ $ U_1 (t) = \prod_{j = 1} ^ m e ^ {-iH_j t/2} \ prod_ {j = m} ^ 1 e ^ {-iH_j t} = e ^ {-iHt} + O (m ^ 3 t ^ 3), $ $ que pode ser feito com menos de $ \epsilon $ para qualquer $ \epsilon > 0 $ escolhendo $ r $ para dimensionar como $m ^ {3/2} t ^ {3/2}/\sqrt {\ Épsilon} $.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-117">The simplest such formula, the symmetric Trotter formula or Strang splitting, takes the form $$ U_1(t) =\prod_{j=1}^m e^{-iH_j t/2}\prod_{j=m}^1 e^{-iH_j t} = e^{-iHt} + O(m^3 t^3), $$ which can be made less than $\epsilon$ for any $\epsilon>0$ by choosing $r$ to scale as $m^{3/2}t^{3/2}/\sqrt{\epsilon}$.</span></span>

<span data-ttu-id="2ab7a-118">As fórmulas Trotter de ordem superior podem ser construídas com base em $U _1 $.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-118">Even higher-order Trotter formulas can be constructed based on $U_1$.</span></span>
<span data-ttu-id="2ab7a-119">A maneira mais simples é a quarta fórmula de ordem a seguir, originalmente introduzido por Suzuki: $ $ U_2 (t) = U_1 ^ 2 (s_1t) U_1 ([1-4s_1] t) U_1 ^ 2 (s_1 t) = e ^ {-iHt} + O (m ^ 5T ^ 5), $ $, em que $s _1 = (4-4 ^ {1/3}) ^{-1}$.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-119">The simplest is the following fourth order formula, originally introduced by Suzuki: $$ U_2(t) = U_1^2(s_1t) U_1([1-4s_1]t)U_1^2(s_1 t) = e^{-iHt} +O(m^5t^5), $$ where $s_1 = (4-4^{1/3})^{-1}$.</span></span>
<span data-ttu-id="2ab7a-120">Em geral, as fórmulas de ordem superior arbitrariamente podem ser construídas de forma semelhante; no entanto, os custos incorridos com o uso de integradores mais complexos geralmente superam os benefícios além da quarta ordem para os problemas mais práticos.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-120">In general, arbitrarily high-order formulas can be similarly constructed; however, the costs incurred from using more complex integrators often outweigh the benefits beyond fourth order for most practical problems.</span></span>

<span data-ttu-id="2ab7a-121">Para fazer com que as estratégias acima funcionem, precisamos ter um método para simular uma ampla classe de $e ^ {-iH_j t} $.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-121">In order to make the above strategies work, we need to have a method for simulating a wide class of $e^{-iH_j t}$.</span></span>
<span data-ttu-id="2ab7a-122">A família mais simples de Hamiltonians e, possivelmente, mais útil, que poderíamos usar aqui são os operadores Pauli.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-122">The simplest family of Hamiltonians, and arguably most useful, that we could use here are Pauli operators.</span></span>
<span data-ttu-id="2ab7a-123">Os operadores Pauli podem ser facilmente simulados porque podem ser interdiagonals usando operações Clifford (que são Gates padrão na computação Quantum).</span><span class="sxs-lookup"><span data-stu-id="2ab7a-123">Pauli operators can be easily simulated because they can be diagonalized using Clifford operations (which are standard gates in quantum computing).</span></span>
<span data-ttu-id="2ab7a-124">Além disso, depois de terem sido diagonais, seus eigenvalues podem ser encontrados computando a paridade do qubits em que eles atuam.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-124">Further, once they have been diagonalized, their eigenvalues can be found by computing the parity of the qubits on which they act.</span></span>

<span data-ttu-id="2ab7a-125">Por exemplo, $ $ e ^ {-iX\otimes X t} = (H\otimes H) e ^ {-iZ\otimes Z t} (H\otimes H), $ $ em que $ $ e ^ {-i Z \otimes Z t} = \begin{bmatrix} e ^ {-IT} & 0 & 0 & 0 </span><span class="sxs-lookup"><span data-stu-id="2ab7a-125">For example, $$ e^{-iX\otimes X t}= (H\otimes H)e^{-iZ\otimes Z t}(H\otimes H), $$ where $$ e^{-i Z \otimes Z t} = \begin{bmatrix} e^{-it} & 0  & 0  & 0 </span></span>\\\
        <span data-ttu-id="2ab7a-126">0 & e ^ {i t} & 0 & 0 </span><span class="sxs-lookup"><span data-stu-id="2ab7a-126">0 & e^{i t}  & 0 & 0 </span></span>\\\
        <span data-ttu-id="2ab7a-127">0 & 0 & e ^ {IT} & 0 </span><span class="sxs-lookup"><span data-stu-id="2ab7a-127">0 & 0 & e^{it} & 0 </span></span>\\\
        <span data-ttu-id="2ab7a-128">0 & 0 & 0 & e ^ {-it} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-128">0 & 0 & 0 & e^{-it} \end{bmatrix}.</span></span>
<span data-ttu-id="2ab7a-129">$ $ Aqui, $e ^ {-iHt} \ket{00} = e ^ {it} \ket{00}$ e $e ^ {-iHt} \ket{01} = e ^ {-it} \ket{01}$, que pode ser visto diretamente como consequência do fato de que a paridade de $0 $ é $0 $ enquanto a paridade da cadeia de caracteres de bits $1 $ é $1 $.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-129">$$ Here, $e^{-iHt} \ket{00} = e^{it} \ket{00}$ and $e^{-iHt} \ket{01} = e^{-it} \ket{01}$, which can be seen directly as a consequence of the fact that the parity of $00$ is $0$ while the parity of the bit string $01$ is $1$.</span></span>

<span data-ttu-id="2ab7a-130">Os exponencials dos operadores Pauli podem ser implementados diretamente em Q # usando a operação <xref:microsoft.quantum.primitive.exp>:</span><span class="sxs-lookup"><span data-stu-id="2ab7a-130">Exponentials of Pauli operators can be implemented directly in Q# using the <xref:microsoft.quantum.primitive.exp> operation:</span></span>
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies e^{- i X \otimes X t} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

<span data-ttu-id="2ab7a-131">Para Fermionic Hamiltonians, a [decomposição da Jordânia – Wigner](xref:microsoft.quantum.chemistry.concepts.jordanwigner) mapeia de forma conveniente o Hamiltonian para uma soma de operadores de Pauli.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-131">For Fermionic Hamiltonians, the [Jordan–Wigner decomposition](xref:microsoft.quantum.chemistry.concepts.jordanwigner) conveniently maps the Hamiltonian into a sum of Pauli operators.</span></span>
<span data-ttu-id="2ab7a-132">Isso significa que a abordagem acima pode facilmente ser adaptada para simular a química.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-132">This means that the above approach can easily be adapted to simulating chemistry.</span></span>
<span data-ttu-id="2ab7a-133">Em vez de fazer um loop manual de todos os termos do Pauli na representação da Jordânia-Wigner, veja abaixo um exemplo simples de como a execução dessa simulação dentro do química seria semelhante.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-133">Rather than manually looping over all Pauli terms in the Jordan-Wigner representation, below is a simple example of how executing such a simulation within the chemistry would look.</span></span>
<span data-ttu-id="2ab7a-134">Nosso ponto de partida é uma [codificação Jordânia – Wigner](xref:microsoft.quantum.chemistry.concepts.jordanwigner) do Fermionic Hamiltonian, expressa em código como uma instância da classe `JordanWignerEncoding`.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-134">Our starting point is a [Jordan–Wigner encoding](xref:microsoft.quantum.chemistry.concepts.jordanwigner) of the Fermionic Hamiltonian, expressed in code as an instance of the `JordanWignerEncoding` class.</span></span>

```csharp
    // This example uses the following namespaces:
    // using Microsoft.Quantum.Chemistry.OrbitalIntegrals;
    // using Microsoft.Quantum.Chemistry.Fermion;
    // using Microsoft.Quantum.Chemistry.Pauli;
    // using Microsoft.Quantum.Chemistry.QSharpFormat;

    // We create an instance of the `FermionHamiltonian` objecclasst to store the terms.
    var hamiltonian = new OrbitalIntegralHamiltonian(new[] 
    {
        new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123),
        new OrbitalIntegral(new[] { 0, 1 }, 0.456)
    }).ToFermionHamiltonian(IndexConvention.UpDown);

    // We convert this fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = hamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);

    // We now convert this representation into a format consumable by Q#.
    var qSharpData = jordanWignerEncoding.ToQSharpFormat();
```

<span data-ttu-id="2ab7a-135">Esse formato da Jordânia – Wigner reprsentation que é consumível pelos algoritmos de simulação do Q # é um tipo definido pelo usuário `JordanWignerEncodingData`.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-135">This format of the Jordan–Wigner reprsentation that is consumable by the Q# simulation algorithms is a user-defined type `JordanWignerEncodingData`.</span></span>
<span data-ttu-id="2ab7a-136">Em Q #, esse formato é passado para uma função de conveniência `TrotterStepOracle` que retorna um operador aproximar a evolução do tempo usando o Trotter – Suzuki Integrator, além de outros parâmetros necessários para sua execução.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-136">Within Q#, this format is passed to a convenience function `TrotterStepOracle` that returns an operator approximating time-evolution using the Trotter—Suzuki integrator, in addition to other parameters required for its execution.</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operatrion.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single time-step.
using(qubits = Qubit[nQubits]){

    // Apply single step of time-evolution
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

<span data-ttu-id="2ab7a-137">De uma maneira importante, essa implementação aplica algumas otimizações discutidas em [simulação de estrutura eletrônica Hamiltonians usando computadores Quantum](https://arxiv.org/abs/1001.3855) e [aprimorando os algoritmos Quantum para o quantum química](https://arxiv.org/abs/1403.1539) para minimizar o número de rotações de qubit simples necessárias, bem como reduzir erros de simulação.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-137">Importantly, this implementation applies some optimizations discussed in [Simulation of Electronic Structure Hamiltonians Using Quantum Computers](https://arxiv.org/abs/1001.3855) and [Improving Quantum Algorithms for Quantum Chemistry](https://arxiv.org/abs/1403.1539) to minimize the number of single-qubit rotations required, as well as reduce simulation errors.</span></span>

## <a name="qubitization"></a><span data-ttu-id="2ab7a-138">Qubitization</span><span class="sxs-lookup"><span data-stu-id="2ab7a-138">Qubitization</span></span>

<span data-ttu-id="2ab7a-139">Qubitization é uma abordagem alternativa para a simulação que usa ideias de exames do Quantum para simular a dinâmica da Quantum.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-139">Qubitization is an alternative approach to simulation that uses ideas from quantum walks to simulate quantum dynamics.</span></span>
<span data-ttu-id="2ab7a-140">Embora qubitization exija mais qubits do que as fórmulas do Trotter, o método promete o dimensionamento ideal com o tempo de evolução e a tolerância a erros.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-140">While qubitization requires more qubits than Trotter formulas, the method promises optimal scaling with the evolution time and the error tolerance.</span></span>
<span data-ttu-id="2ab7a-141">Por esses motivos, ele se tornou um método favorecedo para simular o Hamiltonian Dynamics em geral e para resolver o problema de estrutura eletrônica em particular.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-141">For these reasons it has become a favored method for simulating Hamiltonian dynamics in general, and for solving the electronic structure problem in particular.</span></span>

<span data-ttu-id="2ab7a-142">Em um alto nível, o qubitization realiza isso por meio das etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-142">At a high level, qubitization accomplishes this through the following steps.</span></span>
<span data-ttu-id="2ab7a-143">Primeiro, permita que $H = \sum_j h_j H_j $ para unitário e Hermitian $H _J $ e $h _J \ GE $0.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-143">First, let $H=\sum_j h_j H_j$ for unitary and Hermitian $H_j$ and $h_j\ge 0$.</span></span>
<span data-ttu-id="2ab7a-144">Ao executar um par de reflexos, o qubitization implementa um operador equivalente a $ $W = e ^ {\pm i \cos ^{-1}(H/| h | _1)}, $ $, em que $ | H | _1 = \sum_j | h_j | $.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-144">By performing a pair of reflections, qubitization implements an operator that is equivalent to $$W=e^{\pm i \cos^{-1}(H/|h|_1)},$$ where $|h|_1 = \sum_j |h_j|$.</span></span>
<span data-ttu-id="2ab7a-145">A próxima etapa envolve transformar o eigenvalues do operador de passeio de $e ^ {i\pm \cos ^{-1}(E_k/| h | _1)} $, em que $E _K $ são os eigenvalues de $H $ para $e ^ {-iE_k t} $.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-145">The next step involves transforming the eigenvalues of the walk operator from $e^{i\pm \cos^{-1}(E_k/|h|_1)}$, where $E_k$ are the eigenvalues of $H$ to $e^{-iE_k t}$.</span></span>
<span data-ttu-id="2ab7a-146">Isso pode ser feito usando uma variedade de métodos de transformação de valor singular de Quantum, incluindo [processamento de sinal de Quantum](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).</span><span class="sxs-lookup"><span data-stu-id="2ab7a-146">This can be achieved using a variety of quantum singular value transformation methods including [quantum signal processing](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).</span></span>

<span data-ttu-id="2ab7a-147">Como alternativa, se apenas as quantidades estáticas forem desejadas (como a energia de estado de aterramento do Hamiltonian), será suficiente aplicar a [estimativa de fase](xref:microsoft.quantum.libraries.characterization) diretamente a $W $ para estimar a energia de estado terrestre do resultado, tirando o cosseno do resultado.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-147">Alternatively, if only static quantities are desired (such as the ground state energy of the Hamiltonian) then it suffices to apply [phase estimation](xref:microsoft.quantum.libraries.characterization) directly to $W$ to estimate the ground state energy from the result by taking the cosine of the result.</span></span>
<span data-ttu-id="2ab7a-148">Isso é significativo porque permite que a transformação Spectral seja executada de forma clássica em vez de usar um método de transformação de valor singular de Quantum.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-148">This is significant because it allows the spectral transformation to be performed classically rather than using a quantum singular value transformation method.</span></span>

<span data-ttu-id="2ab7a-149">Em um nível mais detalhado, a implementação de qubitization requer duas sub-rotinas que fornecem as interfaces para o Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-149">On a more detailed level, the implementation of qubitization requires two subroutines that provide the interfaces for the Hamiltonian.</span></span>
<span data-ttu-id="2ab7a-150">Ao contrário dos métodos Trotter – Suzuki, essas sub-rotinas são a Quantum não clássica e sua implementação precisará usar o logaritmicamente mais qubits do que seria necessário para uma simulação baseada em Trotter.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-150">Unlike Trotter–Suzuki methods, these subroutines are quantum not classical and their implementation will necessitate using logarithmically more qubits than would be required for a Trotter-based simulation.</span></span>

<span data-ttu-id="2ab7a-151">A primeira sub-rotina Quantum usada pelo qubitization é chamada de $ \operatorname{Select} $ e é prometida para produzir \begin{Equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{Equation} em que cada $H _J $ é considerado Hermitian e unitário.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-151">The first quantum subroutine that qubitization uses is called $\operatorname{Select}$ and it is promised to yield \begin{equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{equation} where each $H_j$ is assumed to be Hermitian and unitary.</span></span>
<span data-ttu-id="2ab7a-152">Embora isso pareça restritivo, lembre-se de que os operadores Pauli são Hermitian e unitário e, portanto, aplicativos como a simulação química da Quantum se enquadram naturalmente nessa estrutura.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-152">While this may seem to be restrictive, recall that Pauli operators are Hermitian and unitary and so applications like quantum chemistry simulation naturally fall into this framework.</span></span>
<span data-ttu-id="2ab7a-153">A operação $ \operatorname{Select} $, talvez surpreendentemente, é, na verdade, uma operação de reflexão.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-153">The $\operatorname{Select}$ operation, perhaps surprisingly, is actually a reflection operation.</span></span>
<span data-ttu-id="2ab7a-154">Isso pode ser visto do fato de que $ \operatorname{Select} ^ 2 \ ket {j} \ket{\psi} = \ket{j} \ket{\psi} $, já que cada $H _J $ é unitário e Hermitian e, portanto, tem eigenvalues $ \pm $1.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-154">This can be seen from the fact that $\operatorname{Select}^2\ket{j} \ket{\psi} = \ket{j} \ket{\psi}$ since each $H_j$ is unitary and Hermitian and thus has eigenvalues $\pm 1$.</span></span>

<span data-ttu-id="2ab7a-155">A segunda sub-rotina é chamada $ \operatorname{Prepare} $.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-155">The second subroutine is called $\operatorname{Prepare}$.</span></span>
<span data-ttu-id="2ab7a-156">Enquanto a operação SELECT fornece um meio de acessar de forma coerente cada um dos termos de Hamiltonian $H _J $ a sub-rotina Prepare fornece um método para acessar os coeficientes $h _J $, \begin{Equation} \operatorname{Prepare}\ket{0} = \sum_j \sqrt{\frac{h_j}{ | h | _1}} \ket{j}.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-156">While the select operation provides a means to coherently access each of the Hamiltonian terms $H_j$ the prepare subroutine gives a method for accessing the coefficients $h_j$, \begin{equation} \operatorname{Prepare}\ket{0} = \sum_j \sqrt{\frac{h_j}{|h|_1}}\ket{j}.</span></span>
<span data-ttu-id="2ab7a-157">\end{Equation} em seguida, usando um portão de fase controlado por multiplicação, vemos que $ $ \Lambda\ket{0}^ {\otimes n} = \begin{cases} \-\ket{x} & \Text{If} x = 0 </span><span class="sxs-lookup"><span data-stu-id="2ab7a-157">\end{equation} Then, by using a multiply controlled phase gate, we see that $$ \Lambda\ket{0}^{\otimes n} = \begin{cases} \-\ket{x} & \text{if } x = 0 </span></span>\\\
        <span data-ttu-id="2ab7a-158">\ket{x} & \Text{otherwise} \end{cases}.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-158">\ket{x}   & \text{otherwise} \end{cases}.</span></span>
$$

<span data-ttu-id="2ab7a-159">A operação $ \operatorname{Prepare} $ não é usada diretamente em qubitization, mas é usada para implementar uma reflexão sobre o estado em que $ \operatorname{Prepare} $ cria $ $ \begin{align} R &amp; = 1-2 \ OperatorName {Prepare} \ket{0}\bra @no_ _t_2_ \operatorname{Prepare} ^{-1} \\\\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare} ^{-1}.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-159">The $\operatorname{Prepare}$ operation is not used directly in qubitization, but rather is used to implement a reflection about the state that $\operatorname{Prepare}$ creates $$ \begin{align} R &amp; = 1 - 2\operatorname{Prepare} \ket{0}\bra{0} \operatorname{Prepare}^{-1} \\\\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare}^{-1}.</span></span>
<span data-ttu-id="2ab7a-160">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="2ab7a-160">\end{align} $$</span></span>

<span data-ttu-id="2ab7a-161">O operador de passeio, $W $, pode ser expresso em termos das operações $ \operatorname{Select} $ e $R $ como $ $ W = \operatorname{Select} R, $ $, que pode ser visto novamente para implementar um operador equivalente (até um isometry) a $e ^ {\pm i \cos ^{-1}(H/| h | _1)} $.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-161">The walk operator, $W$, can be expressed in terms of the $\operatorname{Select}$ and $R$ operations as $$ W = \operatorname{Select} R, $$ which again can be seen to implement an operator that is equivalent (up to an isometry) to $e^{\pm i \cos^{-1}(H/|h|_1)}$.</span></span>

<span data-ttu-id="2ab7a-162">Essas sub-rotinas são fáceis de configurar em Q #.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-162">These subroutines are easy to set up in Q#.</span></span>
<span data-ttu-id="2ab7a-163">Como exemplo, considere o simples qubit transversal-Ising Hamiltonian em que $H = X_1 + X_2 + Z_1 Z_2 $.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-163">As an example, consider the simple qubit transverse-Ising Hamiltonian where $H = X_1 + X_2 + Z_1 Z_2$.</span></span>
<span data-ttu-id="2ab7a-164">Nesse caso, o código de Q # que implementaria a operação $ \operatorname{Select} $ é invocado por <xref:microsoft.quantum.canon.multiplexoperations>, enquanto a operação $ \operatorname{Prepare} $ pode ser implementada usando <xref:microsoft.quantum.preparation.preparearbitrarystate>.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-164">In this case, Q# code that would implement the $\operatorname{Select}$ operation is invoked by <xref:microsoft.quantum.canon.multiplexoperations>, whereas the $\operatorname{Prepare}$ operation can be implemented using <xref:microsoft.quantum.preparation.preparearbitrarystate>.</span></span>
<span data-ttu-id="2ab7a-165">Um exemplo que envolve a simulação do modelo Hubbard pode ser encontrado como um [exemplo de Q #](https://github.com/Microsoft/Quantum/tree/master/Samples/src/HubbardSimulation).</span><span class="sxs-lookup"><span data-stu-id="2ab7a-165">An example that involves simulating the Hubbard model can be found as a [Q# sample](https://github.com/Microsoft/Quantum/tree/master/Samples/src/HubbardSimulation).</span></span>

<span data-ttu-id="2ab7a-166">A especificação manual dessas etapas para problemas de química arbitrária exigiria muito esforço, o que é evitado com o uso da biblioteca química.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-166">Manually specifying these steps for arbitrary chemistry problems would require much effort, which is avoided using the chemistry library.</span></span>
<span data-ttu-id="2ab7a-167">Da mesma forma que o algoritmo de simulação Trotter – Suzuki acima, o `JordanWignerEncodingData` é passado para a função de conveniência `QubitizationOracle` que retorna o operador de orientação, além de outros parâmetros necessários para sua execução.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-167">Similarly to the Trotter–Suzuki simulation algorithm above, the `JordanWignerEncodingData` is passed to the convenience function `QubitizationOracle` that returns the walk-operator, in addition to other parameters required for its execution.</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/oneNorm`, where oneNorm is the sum of absolute values of all probabilities in state prepared by `Prepare`.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operatrion.
let (nQubits, (rescale, oracle)) =  QubitizationOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single step of the quantum walk.
using(qubits = Qubit[nQubits]){

    // Apply single step of quantum walk.
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

<span data-ttu-id="2ab7a-168">É importante que o <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> de implementação seja aplicável a Hamiltonians arbitrários especificado como uma combinação linear de cadeias de caracteres Pauli.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-168">Importantly, the implementation <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> is applicable to arbitrary Hamiltonians specified as a linear combination of Pauli strings.</span></span>
<span data-ttu-id="2ab7a-169">Uma versão otimizada para simulações de química é invocada usando <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-169">A version optimized for chemistry simulations is invoked using <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>.</span></span>
<span data-ttu-id="2ab7a-170">Esta versão é otimizada para minimizar o número de T Gates usando técnicas discutidas na [codificação eletrônica de Spectra em circuitos Quantum com complexidade de T linear](https://arxiv.org/abs/1805.03662).</span><span class="sxs-lookup"><span data-stu-id="2ab7a-170">This version is optimized to minimize the number of T gates using techniques discussed in [Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity](https://arxiv.org/abs/1805.03662).</span></span>
