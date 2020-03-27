---
title: Simular a Dinâmica Hamiltoniana
description: Aprenda a usar fórmulas Trotter-Suzuki e qubitização para trabalhar com simulações hamiltonianas.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
ms.openlocfilehash: 5dad4e4a77eea99e72eb2efac52eec61ebbdb21c
ms.sourcegitcommit: a0e50c5f07841b99204c068cf5b5ec8ed087ffea
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "80320721"
---
# <a name="simulating-hamiltonian-dynamics"></a><span data-ttu-id="0e31c-103">Simular a Dinâmica Hamiltoniana</span><span class="sxs-lookup"><span data-stu-id="0e31c-103">Simulating Hamiltonian Dynamics</span></span>

<span data-ttu-id="0e31c-104">Uma vez que o Hamiltonian tenha sido expresso como uma soma de operadores elementares, a dinâmica pode então ser compilada em operações fundamentais do portal utilizando uma série de técnicas bem conhecidas.</span><span class="sxs-lookup"><span data-stu-id="0e31c-104">Once the Hamiltonian has been expressed as a sum of elementary operators the dynamics can then be compiled into fundamental gate operations using a host of well-known techniques.</span></span>
<span data-ttu-id="0e31c-105">Três abordagens eficientes incluem fórmulas Trotter-Suzuki, combinações lineares de unitárias e qubitização.</span><span class="sxs-lookup"><span data-stu-id="0e31c-105">Three efficient approaches include are Trotter–Suzuki formulas, linear combinations of unitaries, and qubitization.</span></span>
<span data-ttu-id="0e31c-106">Explicamos estas três abordagens abaixo e damos exemplos concretos de Q# de como implementar estes métodos usando a biblioteca de simulação Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="0e31c-106">We explain these three approaches below and give concrete Q# examples of how to implement these methods using the Hamiltonian simulation library.</span></span>


## <a name="trottersuzuki-formulas"></a><span data-ttu-id="0e31c-107">Fórmulas Trotter-Suzuki</span><span class="sxs-lookup"><span data-stu-id="0e31c-107">Trotter–Suzuki Formulas</span></span>
<span data-ttu-id="0e31c-108">A ideia por trás das fórmulas Trotter-Suzuki é simples: expressar o Hamiltonian como uma soma de fácil simular Hamiltonians e, em seguida, aproximar a evolução total como uma sequência destas evoluções mais simples.</span><span class="sxs-lookup"><span data-stu-id="0e31c-108">The idea behind Trotter–Suzuki formulas is simple: express the Hamiltonian as a sum of easy to simulate Hamiltonians and then approximate the total evolution as a sequence of these simpler evolutions.</span></span>
<span data-ttu-id="0e31c-109">Em particular, deixe $H=\sum_{j=1}^m H_j$ seja o Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="0e31c-109">In particular, let $H=\sum_{j=1}^m H_j$ be the Hamiltonian.</span></span>
<span data-ttu-id="0e31c-110">Em seguida, $$ e^{-i\sum_{j=1}^m H_j t} =\prod_{j=1}^m e^{-iH_j t} + O (m^2 t^2), $$ que é dizer que, se $t\ll 1$, então o erro nesta aproximação torna-se insignificante.</span><span class="sxs-lookup"><span data-stu-id="0e31c-110">Then, $$ e^{-i\sum_{j=1}^m H_j t} =\prod_{j=1}^m e^{-iH_j t} + O(m^2 t^2), $$ which is to say that, if $t\ll 1$, then the error in this approximation becomes negligible.</span></span>
<span data-ttu-id="0e31c-111">Note que se $e^{-i H t}$ fosse um exponencial comum, então o erro nesta aproximação não seria $O (m^2 t^2)$: seria zero.</span><span class="sxs-lookup"><span data-stu-id="0e31c-111">Note that if $e^{-i H t}$ were an ordinary exponential then the error in this approximation would not be $O(m^2 t^2)$: it would be zero.</span></span>
<span data-ttu-id="0e31c-112">Este erro ocorre porque $e^{-iHt}$ é um operador exponencial e, como resultado, há um erro incorrido ao utilizar esta fórmula devido ao facto de os termos $H_j$ não se deslocarem *(isto é,* $H_j H_k \ne H_k H_j$ em geral).</span><span class="sxs-lookup"><span data-stu-id="0e31c-112">This error occurs because $e^{-iHt}$ is an operator exponential and as a result there is an error incurred when using this formula due to the fact that the $H_j$ terms do not commute (*i.e.*, $H_j H_k \ne H_k H_j$ in general).</span></span>

<span data-ttu-id="0e31c-113">Se $t$ for grande, as fórmulas Trotter-Suzuki ainda podem ser usadas para simular a dinâmica com precisão, dividindo-a numa sequência de curtos passos de tempo.</span><span class="sxs-lookup"><span data-stu-id="0e31c-113">If $t$ is large, Trotter–Suzuki formulas can still be used to simulate the dynamics accurately by breaking it up into a sequence of short time-steps.</span></span>
<span data-ttu-id="0e31c-114">Deixe $r$ seja o número de passos dados na evolução do tempo, para que cada passo corra pelo tempo $t/r$.</span><span class="sxs-lookup"><span data-stu-id="0e31c-114">Let $r$ be the number of steps taken in the time evolution, so each time step runs for time $t/r$.</span></span> <span data-ttu-id="0e31c-115">Então, temos que $$ e^{-i\sum_{j=1}^m H_j t} =\left(\prod_{j=1}^m e^{-iH_j t/r}\direita)^r + O(m^2 t^^2/r), $$ o que implica que se $r$ escalacomo $m^2/\epsilon$ então o erro pode ser cometido no máximo $\epsilon$ por qualquer $\epsilon>0$.</span><span class="sxs-lookup"><span data-stu-id="0e31c-115">Then, we have that $$ e^{-i\sum_{j=1}^m H_j t} =\left(\prod_{j=1}^m e^{-iH_j t/r}\right)^r + O(m^2 t^2/r), $$ which implies that if $r$ scales as $m^2 t^2/\epsilon$ then the error can be made at most $\epsilon$ for any $\epsilon>0$.</span></span>

<span data-ttu-id="0e31c-116">Aproximações mais precisas podem ser construídas construindo uma sequência de exponenciais do operador de modo a que os termos de erro cancelem.</span><span class="sxs-lookup"><span data-stu-id="0e31c-116">More accurate approximations can be built by constructing a sequence of operator exponentials such that the error terms cancel.</span></span>
<span data-ttu-id="0e31c-117">A fórmula mais simples, a segunda encomenda fórmula Trotter-Suzuki, toma a forma $$ U_2(t) = \left(\prod_{j=1}^{m} e^-iH_j t/2r} \prod_{j=m}^1 e^{-iH_j t/2r}\right)^r = e^{-iHt} + O (m^t^t^t^t^t^t^t^t 3/r^2), $$ o erro do qual pode ser feito menos de $\epsilon$ por qualquer $\epsilon>0$, escolhendo $r$ para escalar como $m^{3/2}t^{3/2}/\sqrt{\epsilon}$.</span><span class="sxs-lookup"><span data-stu-id="0e31c-117">The simplest such formula, the second order Trotter-Suzuki formula, takes the form $$ U_2(t) = \left(\prod_{j=1}^{m} e^{-iH_j t/2r} \prod_{j=m}^1 e^{-iH_j t/2r}\right)^r = e^{-iHt} + O(m^3 t^3/r^2), $$ the error of which can be made less than $\epsilon$ for any $\epsilon>0$ by choosing $r$ to scale as $m^{3/2}t^{3/2}/\sqrt{\epsilon}$.</span></span>

<span data-ttu-id="0e31c-118">Fórmulas ainda mais altas, especificamente ($2k$)th-order para $k>0$, pode ser construído de forma recursiva: $$ U_{2k}(t) = [U_{2k-2}(s_k\~ t)]^2 U_{2k-2}([1-4s_k]t) [U_{2k-2}(s_k\~ t)^2 = e^{-iHt} + O (m t)^{2k+1}/r^{2k}), $$ onde $s_k = (4-4^{1/(2k-1)}^{-1}$.</span><span class="sxs-lookup"><span data-stu-id="0e31c-118">Even higher-order formulas, specifically ($2k$)th-order for $k>0$, can be constructed recursively: $$ U_{2k}(t) = [U_{2k-2}(s_k\~ t)]^2 U_{2k-2}([1-4s_k]t) [U_{2k-2}(s_k\~ t)]^2 = e^{-iHt} + O((m t)^{2k+1}/r^{2k}), $$ where $s_k = (4-4^{1/(2k-1)})^{-1}$.</span></span>

<span data-ttu-id="0e31c-119">A fórmula seguinte é a quarta encomenda ($k=2$), originalmente introduzida pela Suzuki: $$ U_4(t) = [U_2(s_2\~ t)]^2 U_2([1-4s_2]t) [U_2(s_2\~ t)]^2 = e^{-iHt} +O(m^5t^5/r^4), $$ onde $s_2 = (4-4^{1/3){-1}^</span><span class="sxs-lookup"><span data-stu-id="0e31c-119">The simplest is the following fourth order ($k=2$) formula, originally introduced by Suzuki: $$ U_4(t) = [U_2(s_2\~ t)]^2 U_2([1-4s_2]t) [U_2(s_2\~ t)]^2 = e^{-iHt} +O(m^5t^5/r^4), $$ where $s_2 = (4-4^{1/3})^{-1}$.</span></span>
<span data-ttu-id="0e31c-120">Em geral, as fórmulas arbitrariamente de alta ordem podem ser construídas de forma semelhante; no entanto, os custos incorridos com a utilização de integradores mais complexos superam frequentemente os benefícios para além da quarta ordem para a maioria dos problemas práticos.</span><span class="sxs-lookup"><span data-stu-id="0e31c-120">In general, arbitrarily high-order formulas can be similarly constructed; however, the costs incurred from using more complex integrators often outweigh the benefits beyond fourth order for most practical problems.</span></span>

<span data-ttu-id="0e31c-121">Para que as estratégias acima funcionassem, precisamos de ter um método para simular uma grande classe de $e^{-iH_j t}$.</span><span class="sxs-lookup"><span data-stu-id="0e31c-121">In order to make the above strategies work, we need to have a method for simulating a wide class of $e^{-iH_j t}$.</span></span>
<span data-ttu-id="0e31c-122">A família mais simples de Hamiltonians, e indiscutivelmente mais útil, que poderíamos usar aqui são operadores Pauli.</span><span class="sxs-lookup"><span data-stu-id="0e31c-122">The simplest family of Hamiltonians, and arguably most useful, that we could use here are Pauli operators.</span></span>
<span data-ttu-id="0e31c-123">Os operadores pauli podem ser facilmente simulados porque podem ser diagonalizados usando operações clifford (que são portões padrão na computação quântica).</span><span class="sxs-lookup"><span data-stu-id="0e31c-123">Pauli operators can be easily simulated because they can be diagonalized using Clifford operations (which are standard gates in quantum computing).</span></span>
<span data-ttu-id="0e31c-124">Além disso, uma vez nadiagonaldos, os seus valores eigen podem ser encontrados calculando a paridade dos qubits em que agem.</span><span class="sxs-lookup"><span data-stu-id="0e31c-124">Further, once they have been diagonalized, their eigenvalues can be found by computing the parity of the qubits on which they act.</span></span>

<span data-ttu-id="0e31c-125">Por exemplo, $$ e^{-iX\otimes X t}= (H\otimes H)e^{-iZ\otimes Z t}(H\otimes H), $$ onde $$ e^{-i Z \otimes Z t} = \start{bmatrix} e{{-it} & 0 & 0 & 0 </span><span class="sxs-lookup"><span data-stu-id="0e31c-125">For example, $$ e^{-iX\otimes X t}= (H\otimes H)e^{-iZ\otimes Z t}(H\otimes H), $$ where $$ e^{-i Z \otimes Z t} = \begin{bmatrix} e^{-it} & 0  & 0  & 0 </span></span>\\\
        <span data-ttu-id="0e31c-126">0 & e^{i t} & 0 & 0 e 0 </span><span class="sxs-lookup"><span data-stu-id="0e31c-126">0 & e^{i t}  & 0 & 0 </span></span>\\\
        <span data-ttu-id="0e31c-127">0 & 0 & e^{it} & 0 </span><span class="sxs-lookup"><span data-stu-id="0e31c-127">0 & 0 & e^{it} & 0 </span></span>\\\
        <span data-ttu-id="0e31c-128">0 & 0 & 0 & e^{-it} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="0e31c-128">0 & 0 & 0 & e^{-it} \end{bmatrix}.</span></span>
<span data-ttu-id="0e31c-129">$$ Aqui, $e^{-iHt} \ket{00} = e^{it} \ket{00}$ e $e^{-iHt} \ket{01} = e^{-it} \ket{01}$, que pode ser visto diretamente como consequência do facto de que a paridade de $00$ é $0$ enquanto a paridade da cadeia bit $01$ é $1$1$1$.</span><span class="sxs-lookup"><span data-stu-id="0e31c-129">$$ Here, $e^{-iHt} \ket{00} = e^{it} \ket{00}$ and $e^{-iHt} \ket{01} = e^{-it} \ket{01}$, which can be seen directly as a consequence of the fact that the parity of $00$ is $0$ while the parity of the bit string $01$ is $1$.</span></span>

<span data-ttu-id="0e31c-130">Os exponencials dos operadores pauli podem ser implementados diretamente em Q# usando a operação <xref:microsoft.quantum.intrinsic.exp>:</span><span class="sxs-lookup"><span data-stu-id="0e31c-130">Exponentials of Pauli operators can be implemented directly in Q# using the <xref:microsoft.quantum.intrinsic.exp> operation:</span></span>
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies 𝑒^{- 𝑖 𝑋⊗𝑋 𝑡} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

<span data-ttu-id="0e31c-131">Para os Hamiltonianos Fermiónicos, a [decomposição Jordan-Wigner mapeia](xref:microsoft.quantum.chemistry.concepts.jordanwigner) convenientemente o Hamiltoniano numa soma de operadores pauli.</span><span class="sxs-lookup"><span data-stu-id="0e31c-131">For Fermionic Hamiltonians, the [Jordan–Wigner decomposition](xref:microsoft.quantum.chemistry.concepts.jordanwigner) conveniently maps the Hamiltonian into a sum of Pauli operators.</span></span>
<span data-ttu-id="0e31c-132">Isto significa que a abordagem acima pode ser facilmente adaptada à simulação de química.</span><span class="sxs-lookup"><span data-stu-id="0e31c-132">This means that the above approach can easily be adapted to simulating chemistry.</span></span>
<span data-ttu-id="0e31c-133">Em vez de circular manualmente sobre todos os termos de Pauli na representação Jordan-Wigner, abaixo está um simples exemplo de como executar tal simulação dentro da química seria.</span><span class="sxs-lookup"><span data-stu-id="0e31c-133">Rather than manually looping over all Pauli terms in the Jordan-Wigner representation, below is a simple example of how executing such a simulation within the chemistry would look.</span></span>
<span data-ttu-id="0e31c-134">O nosso ponto de partida é uma [codificação Jordan-Wigner](xref:microsoft.quantum.chemistry.concepts.jordanwigner) do Hamiltonian Fermionic, expressa em código como um exemplo da classe `JordanWignerEncoding`.</span><span class="sxs-lookup"><span data-stu-id="0e31c-134">Our starting point is a [Jordan–Wigner encoding](xref:microsoft.quantum.chemistry.concepts.jordanwigner) of the Fermionic Hamiltonian, expressed in code as an instance of the `JordanWignerEncoding` class.</span></span>

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

<span data-ttu-id="0e31c-135">Este formato da representação Jordan-Wigner que é consumível pelos algoritmos de simulação Q# é um tipo definido pelo utilizador `JordanWignerEncodingData`.</span><span class="sxs-lookup"><span data-stu-id="0e31c-135">This format of the Jordan–Wigner representation that is consumable by the Q# simulation algorithms is a user-defined type `JordanWignerEncodingData`.</span></span>
<span data-ttu-id="0e31c-136">Dentro do Q#, este formato é passado para uma função de conveniência `TrotterStepOracle` que devolve um operador aproximando a evolução do tempo usando o integrador Trotter-Suzuki, além de outros parâmetros necessários para a sua execução.</span><span class="sxs-lookup"><span data-stu-id="0e31c-136">Within Q#, this format is passed to a convenience function `TrotterStepOracle` that returns an operator approximating time-evolution using the Trotter—Suzuki integrator, in addition to other parameters required for its execution.</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single time-step.
using(qubits = Qubit[nQubits]){

    // Apply single step of time-evolution
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

<span data-ttu-id="0e31c-137">Importante, esta implementação aplica algumas otimizações discutidas na [Simulação de Estrutura Eletrónica Hamiltonians Usando Computadores Quânticos](https://arxiv.org/abs/1001.3855) e [Melhorando Algoritmos Quânticos para A Química Quântica](https://arxiv.org/abs/1403.1539) para minimizar o número de rotações de qubit único necessárias, bem como reduzir erros de simulação.</span><span class="sxs-lookup"><span data-stu-id="0e31c-137">Importantly, this implementation applies some optimizations discussed in [Simulation of Electronic Structure Hamiltonians Using Quantum Computers](https://arxiv.org/abs/1001.3855) and [Improving Quantum Algorithms for Quantum Chemistry](https://arxiv.org/abs/1403.1539) to minimize the number of single-qubit rotations required, as well as reduce simulation errors.</span></span>

## <a name="qubitization"></a><span data-ttu-id="0e31c-138">Qubitização</span><span class="sxs-lookup"><span data-stu-id="0e31c-138">Qubitization</span></span>

<span data-ttu-id="0e31c-139">Qubitização é uma abordagem alternativa à simulação que usa ideias de caminhadas quânticas para simular dinâmicas quânticas.</span><span class="sxs-lookup"><span data-stu-id="0e31c-139">Qubitization is an alternative approach to simulation that uses ideas from quantum walks to simulate quantum dynamics.</span></span>
<span data-ttu-id="0e31c-140">Embora a qubitização exija mais qubits do que as fórmulas Trotter, o método promete uma escala ideal com o tempo de evolução e a tolerância ao erro.</span><span class="sxs-lookup"><span data-stu-id="0e31c-140">While qubitization requires more qubits than Trotter formulas, the method promises optimal scaling with the evolution time and the error tolerance.</span></span>
<span data-ttu-id="0e31c-141">Por estas razões, tornou-se um método favorável para simular a dinâmica hamiltoniana em geral e para resolver o problema da estrutura electrónica em particular.</span><span class="sxs-lookup"><span data-stu-id="0e31c-141">For these reasons it has become a favored method for simulating Hamiltonian dynamics in general, and for solving the electronic structure problem in particular.</span></span>

<span data-ttu-id="0e31c-142">A um nível elevado, a qubitização consegue isso através dos seguintes passos.</span><span class="sxs-lookup"><span data-stu-id="0e31c-142">At a high level, qubitization accomplishes this through the following steps.</span></span>
<span data-ttu-id="0e31c-143">Primeiro, deixe $H=\sum_j h_j H_j$ para $H_j$ unitário e hermitiano e $h_j\ge 0$.</span><span class="sxs-lookup"><span data-stu-id="0e31c-143">First, let $H=\sum_j h_j H_j$ for unitary and Hermitian $H_j$ and $h_j\ge 0$.</span></span>
<span data-ttu-id="0e31c-144">Ao realizar um par de reflexões, a qubitização implementa um operador equivalente a $$W=e{\pm i \cos^{-1}(H/hh_1)},$$ onde $hh_1 = \sum_j h_j$.</span><span class="sxs-lookup"><span data-stu-id="0e31c-144">By performing a pair of reflections, qubitization implements an operator that is equivalent to $$W=e^{\pm i \cos^{-1}(H/|h|_1)},$$ where $|h|_1 = \sum_j |h_j|$.</span></span>
<span data-ttu-id="0e31c-145">O passo seguinte passa pela transformação dos valores eigen do operador ambulante de $e^{i\pm \cos^{-1}(E_k/h[h]_1)}$, onde $E_k$ são os valores eigen de $H$ para $e^{-iE_k t}$.</span><span class="sxs-lookup"><span data-stu-id="0e31c-145">The next step involves transforming the eigenvalues of the walk operator from $e^{i\pm \cos^{-1}(E_k/|h|_1)}$, where $E_k$ are the eigenvalues of $H$ to $e^{-iE_k t}$.</span></span>
<span data-ttu-id="0e31c-146">Isto pode ser conseguido usando uma variedade de métodos de transformação de valor singular quântico, incluindo [o processamento de sinal quântico.](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501)</span><span class="sxs-lookup"><span data-stu-id="0e31c-146">This can be achieved using a variety of quantum singular value transformation methods including [quantum signal processing](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).</span></span>

<span data-ttu-id="0e31c-147">Alternativamente, se apenas forem desejadas quantidades estáticas (como a energia do estado terrestre do Hamiltonian), então basta aplicar a estimativa de [fase](xref:microsoft.quantum.libraries.characterization) diretamente para $W$ para estimar a energia do estado terrestre do resultado, tomando o cosine do resultado.</span><span class="sxs-lookup"><span data-stu-id="0e31c-147">Alternatively, if only static quantities are desired (such as the ground state energy of the Hamiltonian) then it suffices to apply [phase estimation](xref:microsoft.quantum.libraries.characterization) directly to $W$ to estimate the ground state energy from the result by taking the cosine of the result.</span></span>
<span data-ttu-id="0e31c-148">Isto é significativo porque permite que a transformação espectral seja realizada clássicamente em vez de usar um método de transformação de valor singular quântico.</span><span class="sxs-lookup"><span data-stu-id="0e31c-148">This is significant because it allows the spectral transformation to be performed classically rather than using a quantum singular value transformation method.</span></span>

<span data-ttu-id="0e31c-149">Num nível mais detalhado, a implementação da qubitização requer duas subrotinas que fornecem as interfaces para o Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="0e31c-149">On a more detailed level, the implementation of qubitization requires two subroutines that provide the interfaces for the Hamiltonian.</span></span>
<span data-ttu-id="0e31c-150">Ao contrário dos métodos Trotter-Suzuki, estas subrotinas não são quânticas e não clássicas e a sua implementação exigirá a utilização de qubits logarithmicamente mais do que seria necessário para uma simulação baseada em Trotter.</span><span class="sxs-lookup"><span data-stu-id="0e31c-150">Unlike Trotter–Suzuki methods, these subroutines are quantum not classical and their implementation will necessitate using logarithmically more qubits than would be required for a Trotter-based simulation.</span></span>

<span data-ttu-id="0e31c-151">A primeira subrotina quântica que a qubitização usa chama-se $\operatorname{Select}$ e promete-se que produz \start{equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{equation} onde cada $H_j$ é assumido como Hermitiano e unitário.</span><span class="sxs-lookup"><span data-stu-id="0e31c-151">The first quantum subroutine that qubitization uses is called $\operatorname{Select}$ and it is promised to yield \begin{equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{equation} where each $H_j$ is assumed to be Hermitian and unitary.</span></span>
<span data-ttu-id="0e31c-152">Embora isto possa parecer restritivo, lembre-se que os operadores pauli são hermitianos e unitários e, por isso, aplicações como a simulação de química quântica caem naturalmente nesta estrutura.</span><span class="sxs-lookup"><span data-stu-id="0e31c-152">While this may seem to be restrictive, recall that Pauli operators are Hermitian and unitary and so applications like quantum chemistry simulation naturally fall into this framework.</span></span>
<span data-ttu-id="0e31c-153">A operação $\operatorname{Select}$ operação, talvez surpreendentemente, é na verdade uma operação de reflexão.</span><span class="sxs-lookup"><span data-stu-id="0e31c-153">The $\operatorname{Select}$ operation, perhaps surprisingly, is actually a reflection operation.</span></span>
<span data-ttu-id="0e31c-154">Isto pode ser visto pelo facto de que $\operatorname{Select}^2\ket{j} \ket{\psi} = \ket{j} {{\psi}$ uma vez que cada $H_j$ é unitário e Hermitiano e, portanto, tem valores eigenvalues $\pm 1$.</span><span class="sxs-lookup"><span data-stu-id="0e31c-154">This can be seen from the fact that $\operatorname{Select}^2\ket{j} \ket{\psi} = \ket{j} \ket{\psi}$ since each $H_j$ is unitary and Hermitian and thus has eigenvalues $\pm 1$.</span></span>

<span data-ttu-id="0e31c-155">A segunda subrotina chama-se $\operatorname {Prepare}$.</span><span class="sxs-lookup"><span data-stu-id="0e31c-155">The second subroutine is called $\operatorname{Prepare}$.</span></span>
<span data-ttu-id="0e31c-156">Enquanto a operação selecionada fornece um meio de aceder coerentemente a cada um dos termos Hamiltonianos $H_j$ a subrotina de preparação dá um método de acesso aos coeficientes $h_j$, \start{equation} \operatorname{Prepare}\ket{0} = \sum_j \sqrt{\frac{h_j{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{</span><span class="sxs-lookup"><span data-stu-id="0e31c-156">While the select operation provides a means to coherently access each of the Hamiltonian terms $H_j$ the prepare subroutine gives a method for accessing the coefficients $h_j$, \begin{equation} \operatorname{Prepare}\ket{0} = \sum_j \sqrt{\frac{h_j}{|h|_1}}\ket{j}.</span></span>
<span data-ttu-id="0e31c-157">\end{equation} Então, utilizando um portão de fase controlado multiplicado, vemos que $$ \Lambda\ket{0}^{\otimes n} = \begin{cases} \-\ket{x} & \text{if } x = 0 </span><span class="sxs-lookup"><span data-stu-id="0e31c-157">\end{equation} Then, by using a multiply controlled phase gate, we see that $$ \Lambda\ket{0}^{\otimes n} = \begin{cases} \-\ket{x} & \text{if } x = 0 </span></span>\\\
        <span data-ttu-id="0e31c-158">\ket{x} & \text{otherwise} \end{cases}.</span><span class="sxs-lookup"><span data-stu-id="0e31c-158">\ket{x}   & \text{otherwise} \end{cases}.</span></span>
$$

<span data-ttu-id="0e31c-159">O nome de $\operador{Prepare}$ não é usado diretamente na qubitização, mas é usado para implementar uma reflexão sobre o estado de que o nome de operador de $\{Prepare}$ cria $$ {start{ R &amp; = 1 - 2\operatorname{Prepare} \ket{0}\bra{0} \operatorname{Prepare}^{-1} \\\\ &amp; = \operatorname {Prepare} \Lambda \operatorname{Prepare}{-1}}</span><span class="sxs-lookup"><span data-stu-id="0e31c-159">The $\operatorname{Prepare}$ operation is not used directly in qubitization, but rather is used to implement a reflection about the state that $\operatorname{Prepare}$ creates $$ \begin{align} R &amp; = 1 - 2\operatorname{Prepare} \ket{0}\bra{0} \operatorname{Prepare}^{-1} \\\\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare}^{-1}.</span></span>
<span data-ttu-id="0e31c-160">\end{align} $$</span><span class="sxs-lookup"><span data-stu-id="0e31c-160">\end{align} $$</span></span>

<span data-ttu-id="0e31c-161">O operador ambulante, $W$, pode ser expresso em termos do nome de $\operador{Select}$ e $R$ como $$ W = \operatorname{Select} R, $$ que novamente pode ser visto para implementar um operador equivalente (até um isometry) a $e^{\pm i \cos^{-1}(H/h__1)}}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}...}.}...}.}.}...}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.}.......}.}.}...}.}.}.}.}.}.}.....}.}.}.</span><span class="sxs-lookup"><span data-stu-id="0e31c-161">The walk operator, $W$, can be expressed in terms of the $\operatorname{Select}$ and $R$ operations as $$ W = \operatorname{Select} R, $$ which again can be seen to implement an operator that is equivalent (up to an isometry) to $e^{\pm i \cos^{-1}(H/|h|_1)}$.</span></span>

<span data-ttu-id="0e31c-162">Estas subrotinas são fáceis de configurar em Q#.</span><span class="sxs-lookup"><span data-stu-id="0e31c-162">These subroutines are easy to set up in Q#.</span></span>
<span data-ttu-id="0e31c-163">Como exemplo, considere o simples qubit transversal-Ising Hamiltonian onde $H = X_1 + X_2 + Z_1 Z_2$.</span><span class="sxs-lookup"><span data-stu-id="0e31c-163">As an example, consider the simple qubit transverse-Ising Hamiltonian where $H = X_1 + X_2 + Z_1 Z_2$.</span></span>
<span data-ttu-id="0e31c-164">Neste caso, o código Q# que implementaria o nome de $\operatorname{Select}$ é invocado por <xref:microsoft.quantum.canon.multiplexoperations>, enquanto que o nome de operador de $\operador{Prepare}$ pode ser implementado utilizando <xref:microsoft.quantum.preparation.preparearbitrarystate>.</span><span class="sxs-lookup"><span data-stu-id="0e31c-164">In this case, Q# code that would implement the $\operatorname{Select}$ operation is invoked by <xref:microsoft.quantum.canon.multiplexoperations>, whereas the $\operatorname{Prepare}$ operation can be implemented using <xref:microsoft.quantum.preparation.preparearbitrarystate>.</span></span>
<span data-ttu-id="0e31c-165">Um exemplo que envolve simular o modelo Hubbard pode ser encontrado como uma [amostra Q#](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard).</span><span class="sxs-lookup"><span data-stu-id="0e31c-165">An example that involves simulating the Hubbard model can be found as a [Q# sample](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard).</span></span>

<span data-ttu-id="0e31c-166">Especificar manualmente estes passos para problemas de química arbitrária exigiria muito esforço, o que é evitado usando a biblioteca de química.</span><span class="sxs-lookup"><span data-stu-id="0e31c-166">Manually specifying these steps for arbitrary chemistry problems would require much effort, which is avoided using the chemistry library.</span></span>
<span data-ttu-id="0e31c-167">À semelhança do algoritmo de simulação Trotter-Suzuki acima, o `JordanWignerEncodingData` é passado para a função de conveniência `QubitizationOracle` que devolve o walk-operator, além de outros parâmetros necessários para a sua execução.</span><span class="sxs-lookup"><span data-stu-id="0e31c-167">Similarly to the Trotter–Suzuki simulation algorithm above, the `JordanWignerEncodingData` is passed to the convenience function `QubitizationOracle` that returns the walk-operator, in addition to other parameters required for its execution.</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/oneNorm`, where oneNorm is the sum of absolute values of all probabilities in state prepared by `Prepare`.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  QubitizationOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single step of the quantum walk.
using(qubits = Qubit[nQubits]){

    // Apply single step of quantum walk.
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

<span data-ttu-id="0e31c-168">Importante, a implementação <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> é aplicável aos hamiltonianos arbitrários especificados como uma combinação linear de cordas Pauli.</span><span class="sxs-lookup"><span data-stu-id="0e31c-168">Importantly, the implementation <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> is applicable to arbitrary Hamiltonians specified as a linear combination of Pauli strings.</span></span>
<span data-ttu-id="0e31c-169">Uma versão otimizada para simulações de química é invocada usando <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>.</span><span class="sxs-lookup"><span data-stu-id="0e31c-169">A version optimized for chemistry simulations is invoked using <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>.</span></span>
<span data-ttu-id="0e31c-170">Esta versão é otimizada para minimizar o número de portões T utilizando técnicas discutidas na [codificação de Espectros Eletrónicos em Circuitos Quânticos com Complexidade Linear T](https://arxiv.org/abs/1805.03662).</span><span class="sxs-lookup"><span data-stu-id="0e31c-170">This version is optimized to minimize the number of T gates using techniques discussed in [Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity](https://arxiv.org/abs/1805.03662).</span></span>
