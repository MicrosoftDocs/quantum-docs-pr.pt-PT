---
title: Teoria hartree-Fock
description: Conheça a teoria Hartree-Fock, uma forma simples de construir o estado inicial para sistemas quânticos.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.hartreefock
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2d5e597c36f7873dfd1e011e7ce7d4b01c0f786e
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869549"
---
# <a name="hartreefock-theory"></a><span data-ttu-id="b8295-103">Teoria hartree-Fock</span><span class="sxs-lookup"><span data-stu-id="b8295-103">Hartree–Fock Theory</span></span>

<span data-ttu-id="b8295-104">Talvez a quantidade mais importante na simulação da química quântica seja o estado do solo, que é o eigenvector energético mínimo da matriz hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="b8295-104">Perhaps the most important quantity in quantum chemistry simulation is the ground state, which is the minimum energy eigenvector of the Hamiltonian matrix.</span></span>
<span data-ttu-id="b8295-105">Isto porque para a maioria das moléculas em quantidades de temperatura ambiente, tais como taxas de reação, são dominadas por diferenças energéticas livres entre estados quânticos que descrevem o início e o fim de um passo numa via de reação e à temperatura ambiente tais estados intermédios são geralmente estados terrestres.</span><span class="sxs-lookup"><span data-stu-id="b8295-105">This is because for most molecules at room temperature quantities such as reaction rates are dominated by free energy differences between quantum states that describe the beginning and end of a step in a reaction pathway and at room temperature such intermediate state are usually ground states.</span></span>
<span data-ttu-id="b8295-106">Embora o estado do solo seja tipicamente muito difícil de aprender (mesmo com um computador quântico) porque é uma distribuição sobre um número exponencialmente grande de configurações.</span><span class="sxs-lookup"><span data-stu-id="b8295-106">While the ground state is typically too hard to learn (even with a quantum computer) because it is a distribution over an exponentially large number of configurations.</span></span>
<span data-ttu-id="b8295-107">Quantidades como a energia do estado do solo podem ser aprendidas.</span><span class="sxs-lookup"><span data-stu-id="b8295-107">Quantities such as ground state energy can be learned.</span></span>
<span data-ttu-id="b8295-108">Por exemplo, se $\ket{\psi}$ é qualquer estado quântico puro então \start{equação} E = \bra{ \\ \hat{H} \ket{\psi} \end{equação} dá a energia média que o sistema tem nesse estado.</span><span class="sxs-lookup"><span data-stu-id="b8295-108">For example, if $\ket{\psi}$ is any pure quantum state then \begin{equation} E = \bra{ \psi } \hat{H} \ket{\psi} \end{equation} gives the mean energy that the system has in that state.</span></span>
<span data-ttu-id="b8295-109">O estado terrestre é então o estado que dá o menor valor.</span><span class="sxs-lookup"><span data-stu-id="b8295-109">The ground state then is the state that gives the smallest such value.</span></span> <span data-ttu-id="b8295-110">Como resultado, escolher um estado o mais próximo possível do verdadeiro estado terrestre é vital para estimar a energia diretamente (como é feito em eigensolvers variacionais) ou através da estimativa de fase.</span><span class="sxs-lookup"><span data-stu-id="b8295-110">As a result, choosing a state that is as close as possible to the true ground state is vitally important for estimating the energy either directly (as is done in variational eigensolvers) or through phase estimation.</span></span>

<span data-ttu-id="b8295-111">A teoria hartree-Fock dá uma maneira simples de construir o estado inicial para sistemas quânticos.</span><span class="sxs-lookup"><span data-stu-id="b8295-111">Hartree–Fock theory gives a simple way to construct the initial state for quantum systems.</span></span> <span data-ttu-id="b8295-112">Produz uma única aproximação determinante de Slater ao estado terrestre de um sistema quântico.</span><span class="sxs-lookup"><span data-stu-id="b8295-112">It yields a single Slater-determinant approximation to the ground state of a quantum system.</span></span> <span data-ttu-id="b8295-113">Para tal, encontra uma rotação dentro do espaço Fock que minimiza a energia do estado do solo.</span><span class="sxs-lookup"><span data-stu-id="b8295-113">To that end, it finds a rotation within Fock-space that minimizes the ground state energy.</span></span> <span data-ttu-id="b8295-114">Em particular, para um sistema de eletrões $N$ o método executa a rotação \start{equação} \prod_{j=0}^{N-1} a^\dagger_j \ket {0} \mapsto \prod_{j=0}^{N-1} e^1} e^\\ket \ket \mapsto \prod_{j=0}^{N-1} e^1} e^\\ket \ket \mapsto \prod_{j=0}^{N-1} e^-1} {u} a^\dagger_j e^{-u} \ket {0} \defeq\prod_{j=0}^{N-1} \widetilde{a}^\dagger_j \ket {0} , \end{equation} com um anti-hermitiano (i.e. $u= -u^\dagger$) matriz $u = \sum_{pq} u_{pq} a^\dagger_p a_q$.</span><span class="sxs-lookup"><span data-stu-id="b8295-114">In particular, for a system of $N$ electrons the method performs the rotation \begin{equation} \prod_{j=0}^{N-1} a^\dagger_j \ket{0} \mapsto \prod_{j=0}^{N-1} e^{u} a^\dagger_j e^{-u} \ket{0}\defeq\prod_{j=0}^{N-1}  \widetilde{a}^\dagger_j  \ket{0}, \end{equation} with an anti-Hermitian (i.e. $u= -u^\dagger$) matrix $u = \sum_{pq} u_{pq} a^\dagger_p a_q$.</span></span> <span data-ttu-id="b8295-115">Note-se que a matriz $u$ representa as rotações orbitais e $\widetilde{a}^\\dagger_j$ e $\widetilde{a}_j$ representam operadores de criação e aniquilação para eletrões que ocupam os orbitais de rotação molecular Hartree-Fock.</span><span class="sxs-lookup"><span data-stu-id="b8295-115">It should be noted that the matrix $u$ represents the orbital rotations and $\widetilde{a}^\dagger_j$ and $\widetilde{a}_j$ represent creation and annihilation operators for electrons occupying Hartree–Fock molecular spin-orbitals.</span></span>


<span data-ttu-id="b8295-116">A matriz $u$ é então otimizada para minimizar a energia esperada $\bra {0} \prod_{j=0}^{N-1} \widetilde{a} \_ j H \prod \_ {k=0}^{N-1} \widetilde{a}\\dagger_k\ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="b8295-116">The matrix $u$ is then optimized to minimize the expected energy $\bra{0} \prod_{j=0}^{N-1}  \widetilde{a}\_j  H \prod\_{k=0}^{N-1}  \widetilde{a}^\dagger_k\ket{0}$.</span></span> <span data-ttu-id="b8295-117">Embora tais problemas de otimização possam ser genericamente difíceis, na prática o algoritmo Hartree-Fock tende a convergir rapidamente para uma solução quase ideal para o problema de otimização, especialmente para moléculas de concha fechada nas geometrias do equilíbrio.</span><span class="sxs-lookup"><span data-stu-id="b8295-117">While such optimization problems may be generically hard, in practice the Hartree–Fock algorithm tends to rapidly converge to a near-optimal solution to the optimization problem, especially for closed-shell molecules in the equilibrium geometries.</span></span> <span data-ttu-id="b8295-118">Podemos especificar estes estados como um exemplo do `FermionWavefunction` objeto.</span><span class="sxs-lookup"><span data-stu-id="b8295-118">We may specify these states as an instance of the `FermionWavefunction` object.</span></span> <span data-ttu-id="b8295-119">Por exemplo, o estado $a^\dagger_ {1} a^\dagger_ {2} a^\dagger_ {6} \ket $ é {0} instantâneo na biblioteca de química da seguinte forma.</span><span class="sxs-lookup"><span data-stu-id="b8295-119">For instance, the state $a^\dagger_{1}a^\dagger_{2}a^\dagger_{6}\ket{0}$ is instantiated in the chemistry library as follows.</span></span>
```csharp
// Create a list of integer indices of the creation operators
var indices = new[] { 1, 2, 6 };

// Convert the list of indices to a `FermionWavefunction` object.
// In this case, the indices are integers, so we use the `int`
// type specialization.
var wavefunction = new FermionWavefunction<int>(indices);
```
<span data-ttu-id="b8295-120">Também é possível indexar funções de onda com `SpinOrbital` índices, e depois converter estes índices em inteiros da seguinte forma.</span><span class="sxs-lookup"><span data-stu-id="b8295-120">It is also possible to index wave functions with `SpinOrbital` indices, and then convert these indices to integers as follows.</span></span>
```csharp
// Create a list of spin orbital indices of the creation operators
var indices = new[] { (0, Spin.d), (1,Spin.u), (3, Spin.u) };

// Convert the list of indices to a `FermionWavefunction` object.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(indices.ToSpinOrbitals());

// Convert a wavefunction indexed by spin orbitals to
// one indexed by integers
var wavefunctionInt = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

<span data-ttu-id="b8295-121">A característica mais marcante sobre a teoria hartree-Fock é que produz um estado quântico que não tem qualquer emaranhamento entre os eletrões.</span><span class="sxs-lookup"><span data-stu-id="b8295-121">The most striking feature about Hartree–Fock theory is that it yields a quantum state that has no entanglement between the electrons.</span></span>
<span data-ttu-id="b8295-122">Isto significa que muitas vezes fornece uma descrição qualitativa adequada das propriedades dos sistemas moleculares.</span><span class="sxs-lookup"><span data-stu-id="b8295-122">This means that it often provides a suitable qualitative description of properties of molecular systems.</span></span> 

<span data-ttu-id="b8295-123">O estado de Hartree-Fock também pode ser reconstruído da `FermionHamiltonian` seguinte forma.</span><span class="sxs-lookup"><span data-stu-id="b8295-123">The Hartree-Fock state may also be reconstructed from a `FermionHamiltonian`  as follows.</span></span>
```csharp
// We initialize a fermion Hamiltonian.
var fermionHamiltonian = new FermionHamiltonian();

// Create a Hartree-Fock state from the Hamiltonian 
// with, say, `4` occupied spin orbitals.
var wavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons: 4);
```

<span data-ttu-id="b8295-124">No entanto, obter resultados precisos, especialmente para sistemas fortemente correlacionados, requer estados quânticos que vão além da teoria hartree-Fock.</span><span class="sxs-lookup"><span data-stu-id="b8295-124">However, obtaining accurate results, especially for strongly correlated systems, necessitate quantum states that go beyond Hartree–Fock theory.</span></span>
