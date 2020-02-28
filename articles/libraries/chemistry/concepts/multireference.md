---
title: Funções de onda correlacionadas
description: Aprenda sobre correlações dinâmicas e não dinâmicas em funções de ondas usando a biblioteca de química Quântica da Microsoft.
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.multireference
ms.openlocfilehash: 005ef86382ca72969b06a4206cab01f3845718e2
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904439"
---
# <a name="correlated-wavefunctions"></a><span data-ttu-id="48f79-103">Funções de onda correlacionadas</span><span class="sxs-lookup"><span data-stu-id="48f79-103">Correlated wavefunctions</span></span>

<span data-ttu-id="48f79-104">Para muitos sistemas, particularmente aqueles perto da geometria do equilíbrio, a teoria [de Hartree-Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) fornece uma descrição qualitativa das propriedades moleculares através de um estado de referência único determinante.</span><span class="sxs-lookup"><span data-stu-id="48f79-104">For many systems, particularly those near the equilibrium geometry, [Hartree–Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) theory provides a qualitative description of molecular properties through a single-determinant reference state.</span></span> <span data-ttu-id="48f79-105">No entanto, para se conseguir uma precisão quantitativa, é necessário também considerar os efeitos da correlação.</span><span class="sxs-lookup"><span data-stu-id="48f79-105">However, in order to achieve quantitative accuracy, one must also consider correlation effects.</span></span> 

<span data-ttu-id="48f79-106">Neste contexto, é importante dinpidar entre correlações dinâmicas e não dinâmicas.</span><span class="sxs-lookup"><span data-stu-id="48f79-106">In this context, it is important to dinstinguish between dynamic and non-dynamic correlations.</span></span>
<span data-ttu-id="48f79-107">As correlações dinâmicas surgem da tendência dos eletrões para se manterem separados, como por exemplo devido à repulsão interelectrónica.</span><span class="sxs-lookup"><span data-stu-id="48f79-107">Dynamical correlations arise from the tendency of electrons to stay apart, such as due to interelectronic repulsion.</span></span> <span data-ttu-id="48f79-108">Este efeito pode ser modelado considerando as excitações de eletrões fora do estado de referência.</span><span class="sxs-lookup"><span data-stu-id="48f79-108">This effect can be modelled by considering excitations of electrons out of the reference state.</span></span> <span data-ttu-id="48f79-109">As correlações não dinâmicas surgem quando a função de onda é dominada por duas ou mais configurações à ordem zero, mesmo para obter apenas uma descrição qualitativa do sistema.</span><span class="sxs-lookup"><span data-stu-id="48f79-109">Non-dynamic correlations arise when the wavefunction is dominated by two or more configurations at zeroth order, even to achieve only a qualitative description of the system.</span></span>
<span data-ttu-id="48f79-110">Isto requer uma sobreposição de determinantes e é um exemplo de uma função de onda multi-referência.</span><span class="sxs-lookup"><span data-stu-id="48f79-110">This necessitates a superposition of determinants and is an example of a multireference wavefunction.</span></span>

<span data-ttu-id="48f79-111">A biblioteca de química fornece uma maneira de especificar uma função de onda de ordem zero para o problema de multireferência como uma superposição de determinantes.</span><span class="sxs-lookup"><span data-stu-id="48f79-111">The chemistry library provides a way to specify a zeroth order wavefunction for the multireference problem as a superposition of determinants.</span></span> <span data-ttu-id="48f79-112">Esta abordagem, a que chamamos funções de ondas multi-referência escassas, é eficaz quando apenas alguns componentes são suficientes para especificar a superposição.</span><span class="sxs-lookup"><span data-stu-id="48f79-112">This approach, which we call sparse multireference wavefunctions, is effective when only a few components suffice to specify the superposition.</span></span> <span data-ttu-id="48f79-113">A biblioteca também fornece um método para incluir correlações dinâmicas em cima de uma referência determinante única através do aglomerado unitário generalizado ansatz.</span><span class="sxs-lookup"><span data-stu-id="48f79-113">The library also provides a method to include dynamic correlations on top of a single-determinant reference via the generalized unitary coupled-cluster ansatz.</span></span> <span data-ttu-id="48f79-114">Além disso, também constrói circuitos quânticos que geram estes estados num computador quântico.</span><span class="sxs-lookup"><span data-stu-id="48f79-114">Furthermore, it also constructs quantum circuits that generate these states on a quantum computer.</span></span> <span data-ttu-id="48f79-115">Estes estados podem ser especificados no esquema de [Broombridge,](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)e também fornecemos a funcionalidade para especificar manualmente estes estados através da biblioteca de química.</span><span class="sxs-lookup"><span data-stu-id="48f79-115">These states may be specified in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), and we also provide the functionality to manually specify these states through the chemistry library.</span></span>

## <a name="sparse-multi-reference-wavefunction"></a><span data-ttu-id="48f79-116">Função de ondas de várias referências escassas</span><span class="sxs-lookup"><span data-stu-id="48f79-116">Sparse multi-reference wavefunction</span></span>
<span data-ttu-id="48f79-117">Um estado de referência multi-referência $\ket {\psi_{\rm {MCSCF}}}$pode ser especificado explicitamente como uma combinação linear de determininantes slater de $N$-eletrões.</span><span class="sxs-lookup"><span data-stu-id="48f79-117">A multi-reference state $\ket{\psi_{\rm {MCSCF}}}$ may be specified explicitly as a linear combination of $N$-electron Slater determininants.</span></span>
<span data-ttu-id="48f79-118">\begin{align} \ket{\psi_{\rm {MCSCF}} \propto \sum_{i_1 < i_2 < \cdots < i_N} \lambda_{i_1,i_2,\cdots,i_N} a^\dagger_{i_1}\\dagger_\lambda_{i_2}\cdots a^{dagger_{i_N}}\{0}ket</span><span class="sxs-lookup"><span data-stu-id="48f79-118">\begin{align} \ket{\psi_{\rm {MCSCF}}} \propto \sum_{i_1 < i_2 < \cdots < i_N} \lambda_{i_1,i_2,\cdots,i_N} a^\dagger_{i_1}a^\dagger_{i_2}\cdots a^\dagger_{i_N}\ket{0}.</span></span>
<span data-ttu-id="48f79-119">\end{align} Por exemplo, o estado $\propto (0.1 a^\dagger_1a\\dagger_2a^\dagger_6 - 0,2 a^\dagger_2a^\dagger_1a^\dagger_5)\ket{0}$ pode ser especificado na biblioteca de química da seguinte forma.</span><span class="sxs-lookup"><span data-stu-id="48f79-119">\end{align} For example, the state $\propto(0.1 a^\dagger_1a^\dagger_2a^\dagger_6 - 0.2 a^\dagger_2a^\dagger_1a^\dagger_5)\ket{0}$ may be specified in the chemistry library as follows.</span></span>
```csharp
// Create a list of tuples where the first item of each 
// tuple are indices to the creation operators acting on the
// vacuum state, and the second item is the coefficient
// of that basis state.
var superposition = new[] {
    (new[] {1, 2, 6}, 0.1),
    (new[] {2, 1, 5}, -0.2) };

// Create a fermion wavefunction object that represents the superposition.
var wavefunction = new FermionWavefunction<int>(superposition);
```
<span data-ttu-id="48f79-120">Esta representação explícita dos componentes de superposição é eficaz quando apenas alguns componentes precisam de ser especificados.</span><span class="sxs-lookup"><span data-stu-id="48f79-120">This explicit representation of the superposition components is effective when only a few components need to be specified.</span></span> <span data-ttu-id="48f79-121">Deve-se evitar utilizar esta representação quando muitos componentes são necessários para capturar com precisão o estado desejado.</span><span class="sxs-lookup"><span data-stu-id="48f79-121">One should avoid using this representation when many components are required to accurately capture the desired state.</span></span> <span data-ttu-id="48f79-122">A razão para isso é o custo do portão do circuito quântico que prepara este estado num computador quântico, que escala pelo menos linearmente com o número de componentes de superposição, e no máximo quadraticamente com a norma das amplitudes de superposição.</span><span class="sxs-lookup"><span data-stu-id="48f79-122">The reason for this is the gate cost of quantum circuit that prepares this state on a quantum computer, which scales at least linearly with the number of superposition components, and at most quadratically with the one-norm of the superposition amplitudes.</span></span>

## <a name="unitary-coupled-cluster-wavefunction"></a><span data-ttu-id="48f79-123">Função unitária de onda de aglomerado acopd</span><span class="sxs-lookup"><span data-stu-id="48f79-123">Unitary coupled-cluster wavefunction</span></span>
<span data-ttu-id="48f79-124">Também é possível especificar uma função unitária de onda de cluster $\ket{\psi_{\rm {UCC}}}$$ usando a biblioteca de químicos.</span><span class="sxs-lookup"><span data-stu-id="48f79-124">It is also possible to specify a unitary coupled-cluster wavefunction $\ket{\psi_{\rm {UCC}}}$ using the chemistery library.</span></span> <span data-ttu-id="48f79-125">Nesta situação, temos um estado de referência único, digamos, $\ket{\psi_{\rm{SCF}}}$.</span><span class="sxs-lookup"><span data-stu-id="48f79-125">In this situation, we have a single-determinant reference state, say, $\ket{\psi_{\rm{SCF}}}$.</span></span> <span data-ttu-id="48f79-126">Os componentes da função de onda de aglomerado unitário são então especificados implicitamente através de um operador unitário que atua num estado de referência.</span><span class="sxs-lookup"><span data-stu-id="48f79-126">The components of the unitary coupled-cluster wavefunction are then specified implicity through a unitary operator acting on a reference state.</span></span>
<span data-ttu-id="48f79-127">Este operador unitário é comumente escrito como $e^{T-T^\dagger}$, onde $T-T^\dagger$ é o operador de cluster anti-eremititiano.</span><span class="sxs-lookup"><span data-stu-id="48f79-127">This unitary operator is commonly written as $e^{T-T^\dagger}$, where $T-T^\dagger$ is the anti-Hermitian cluster operator.</span></span> <span data-ttu-id="48f79-128">Assim\ comece {align} \ket{\psi_{\rm {UCC}} = e^T-T^\dagger}\ket{\psi_{\rm{SCF}}.</span><span class="sxs-lookup"><span data-stu-id="48f79-128">Thus \begin{align} \ket{\psi_{\rm {UCC}}} = e^{T-T^\dagger}\ket{\psi_{\rm{SCF}}}.</span></span>
<span data-ttu-id="48f79-129">\fim{align}</span><span class="sxs-lookup"><span data-stu-id="48f79-129">\end{align}</span></span>

<span data-ttu-id="48f79-130">Também é comum dividir o operador do cluster $T = T_1 + T_2 + \cdots$ em partes, onde cada parte $T_j$ contém termos $j corpo de $.</span><span class="sxs-lookup"><span data-stu-id="48f79-130">It is also common to split the cluster operator $T = T_1 + T_2 + \cdots$ into parts, where each part $T_j$ contains $j$-body terms.</span></span> <span data-ttu-id="48f79-131">Na teoria do cluster acoplado generalizado, o operador de cluster de um corpo (singles) é da forma \begin{align} T_1 = \sum_{pq}t^{p}_{q} a^\dagger_p a_q, \end{align}</span><span class="sxs-lookup"><span data-stu-id="48f79-131">In generalized coupled-cluster theory, the one-body cluster operator (singles) is of the form \begin{align} T_1 = \sum_{pq}t^{p}_{q} a^\dagger_p a_q, \end{align}</span></span>

<span data-ttu-id="48f79-132">e o operador de cluster de duas carroças (duplos) é da forma \begin{align} T_2 = \sum_{pqrs}t^{pq}{{rs} a^\dagger_p a^\dagger_q a_r a_s.</span><span class="sxs-lookup"><span data-stu-id="48f79-132">and two-body cluster operator (doubles) is of the form \begin{align} T_2 = \sum_{pqrs}t^{pq}_{rs} a^\dagger_p a^\dagger_q a_r a_s.</span></span>
<span data-ttu-id="48f79-133">\fim{align}</span><span class="sxs-lookup"><span data-stu-id="48f79-133">\end{align}</span></span>

<span data-ttu-id="48f79-134">Os termos de ordem superior (triplos, quadruplos, etc.) são possíveis, mas não são atualmente suportados pela biblioteca de química.</span><span class="sxs-lookup"><span data-stu-id="48f79-134">Higher-order terms (triples, quadruples, etc.) are possible, but not currently supported by the chemistry library.</span></span>

<span data-ttu-id="48f79-135">Por exemplo, deixe $\ket{\psi_{\rm{SCF}}} = a^dagger_1 a^\\dagger_2\ket{0}$, e deixe $T= 0,123 a^\dagger_0 a_1 + 0,456 a^\dagger_0a^\dagger_3 a_1 a_2 - 0,789 a^\dagger_3a^\dagger_2 a_1 a_0$.</span><span class="sxs-lookup"><span data-stu-id="48f79-135">For example, let $\ket{\psi_{\rm{SCF}}} = a^\dagger_1 a^\dagger_2\ket{0}$, and let $T= 0.123 a^\dagger_0 a_1 + 0.456 a^\dagger_0a^\dagger_3 a_1 a_2 - 0.789 a^\dagger_3a^\dagger_2 a_1 a_0$.</span></span> <span data-ttu-id="48f79-136">Então este estado é instantaneamente instantâneo na biblioteca de química da seguinte forma.</span><span class="sxs-lookup"><span data-stu-id="48f79-136">Then this state is instantiated in the chemistry library as follows.</span></span>
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { 1, 2 };

// Create a list describing the cluster operator
// The first half of each list of integers will be
// associated with the creation operators, and
// the second half with the annihilation operators.
var clusterOperator = new[]
{
    (new [] {0, 1}, 0.123),
    (new [] {0, 3, 1, 2}, 0.456),
    (new [] {3, 2, 1, 0}, 0.789)
};

// Create a fermion wavefunction object that represents the 
// unitary coupled-cluster wavefunction. It is assumed implicity
// that the exponent of the unitary coupled-cluster operator
// is the cluster operator minus its Hermitian conjugate.
var wavefunction = new FermionWavefunction<int>(reference, clusterOperator);
```

<span data-ttu-id="48f79-137">A convervação de giro pode ser explicitada especificando `SpinOrbital` índices em vez de índices inteiros.</span><span class="sxs-lookup"><span data-stu-id="48f79-137">Spin convervation may be made explicit by instead specifying `SpinOrbital` indices instead of integer indices.</span></span> <span data-ttu-id="48f79-138">Por exemplo, deixe $\ket{\psi_{\rm{SCF}}} = a^dagger_{1,\uparrow} a^\dagger_{2, \downarrow}\ket{0}$, e deixe $T= 0,123 a^\dagger_{0, \uparrow} a_{1, \uparrow} + 0,456 a^\dagger_{0, \uparrow} a^\dagger_{3, \downarrow} a_{1, \uparrow} a_{2, \downarrow} - 0,789 a^\dagger_{3,\uparrow} a^\dagger_{2,uparrow} a_{1,\uparrow a_{0, \up</span><span class="sxs-lookup"><span data-stu-id="48f79-138">For example, let $\ket{\psi_{\rm{SCF}}} = a^\dagger_{1,\uparrow} a^\dagger_{2, \downarrow}\ket{0}$, and let $T= 0.123 a^\dagger_{0, \uparrow} a_{1, \uparrow} + 0.456 a^\dagger_{0, \uparrow} a^\dagger_{3, \downarrow} a_{1, \uparrow} a_{2, \downarrow} - 0.789 a^\dagger_{3,\uparrow} a^\dagger_{2,\uparrow} a_{1,\uparrow} a_{0, \uparrow}$ be spin convserving.</span></span> <span data-ttu-id="48f79-139">Então este estado é instantaneamente instantâneo na biblioteca de química da seguinte forma.</span><span class="sxs-lookup"><span data-stu-id="48f79-139">Then this state is instantiated in the chemistry library as follows.</span></span>
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { (1, Spin.u), (2, Spin.d) }.ToSpinOrbitals();

// Create a list describing the cluster operator
// The first half of each list of integers will be
// associated with the creation operators, and
// the second half with the annihilation operators.
var clusterOperator = new[]
{
    (new [] {(0, Spin.u), (1, Spin.u)}, 0.123),
    (new [] {(0, Spin.u), (3, Spin.d), (1, Spin.u), (2, Spin.d)}, 0.456),
    (new [] {(3, Spin.u), (2, Spin.u), (1, Spin.u), (0, Spin.u)}, 0.789)
}.Select(o => (o.Item1.ToSpinOrbitals(), o.Item2);

// Create a fermion wavefunction object that represents the 
// unitary coupled-cluster wavefunction. It is assumed implicity
// that the exponent of the unitary coupled-cluster operator
// is the cluster operator minus its Hermitian conjugate.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(reference, clusterOperator);

// Convert the wavefunction indexed by spin-orbitals to one indexed
// by integers
var wavefunctionInteger = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

<span data-ttu-id="48f79-140">Também fornecemos uma função de conveniência que enumera todos os operadores de clusters que aniquilam apenas os orbitais de centrifugação ocupados e excitam apenas os orbitais de spin-orbitais desocupados.</span><span class="sxs-lookup"><span data-stu-id="48f79-140">We also provide a convenience function that enumerates over all spin-conversing cluster operators that annihilate only occupied spin-orbitals and excite to only unoccupied spin-orbitals.</span></span>
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { (1, Spin.u), (2, Spin.d) }.ToSpinOrbitals();

// Generate all spin-conversing excitations from spin-orbitals 
// occupied by the reference state to virtual orbitals.
var generatedExcitations = reference.CreateAllUCCSDSingletExcitations(nOrbitals: 3).Excitations;

// This is the list of expected spin-consvering excitations
var expectedExcitations = new[]
{
    new []{ (0, Spin.u), (1,Spin.u)},
    new []{ (2, Spin.u), (1,Spin.u)},
    new []{ (0, Spin.d), (2,Spin.d)},
    new []{ (1, Spin.d), (2,Spin.d)},
    new []{ (0, Spin.u), (0, Spin.d), (2, Spin.d), (1,Spin.u)},
    new []{ (0, Spin.u), (1, Spin.d), (2, Spin.d), (1,Spin.u)},
    new []{ (0, Spin.d), (2, Spin.u), (2, Spin.d), (1,Spin.u)},
    new []{ (1, Spin.d), (2, Spin.u), (2, Spin.d), (1,Spin.u)}
}.Select(o => new IndexOrderedSequence<SpinOrbital>(o.ToLadderSequence()));

// The following two assertions are true, and verify that the generated 
// excitations exactly match the expected excitations.
var bool0 = generatedExcitations.Keys.All(expectedExcitations.Contains);
var bool1 = generatedExcitations.Count() == expectedExcitations.Count();
```
