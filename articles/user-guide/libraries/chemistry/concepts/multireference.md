---
title: Funções de onda correlacionadas
description: Saiba mais sobre correlações dinâmicas e não dinâmicas em funções de onda usando a biblioteca de química quântica da Microsoft.
author: guanghaolow
ms.author: gulow
ms.date: 05/28/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.multireference
no-loc:
- Q#
- $$v
ms.openlocfilehash: 420fc8e108852f6548e2147693e089f5ce970aa9
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835490"
---
# <a name="correlated-wavefunctions"></a><span data-ttu-id="69231-103">Funções de onda correlacionadas</span><span class="sxs-lookup"><span data-stu-id="69231-103">Correlated wavefunctions</span></span>

<span data-ttu-id="69231-104">Para muitos sistemas, particularmente aqueles perto da geometria do equilíbrio, a teoria [hartree-Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) fornece uma descrição qualitativa das propriedades moleculares através de um estado de referência único determinante.</span><span class="sxs-lookup"><span data-stu-id="69231-104">For many systems, particularly those near the equilibrium geometry, [Hartree–Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) theory provides a qualitative description of molecular properties through a single-determinant reference state.</span></span> <span data-ttu-id="69231-105">No entanto, para se obter uma precisão quantitativa, é também necessário considerar os efeitos da correlação.</span><span class="sxs-lookup"><span data-stu-id="69231-105">However, in order to achieve quantitative accuracy, one must also consider correlation effects.</span></span> 

<span data-ttu-id="69231-106">Neste contexto, é importante jantar entre correlações dinâmicas e não dinâmicas.</span><span class="sxs-lookup"><span data-stu-id="69231-106">In this context, it is important to dinstinguish between dynamic and non-dynamic correlations.</span></span>
<span data-ttu-id="69231-107">As correlações dinâmicas surgem da tendência dos eletrões para se manterem separados, como devido à repulsão interelectrónica.</span><span class="sxs-lookup"><span data-stu-id="69231-107">Dynamical correlations arise from the tendency of electrons to stay apart, such as due to interelectronic repulsion.</span></span> <span data-ttu-id="69231-108">Este efeito pode ser modelado considerando excitações de eletrões fora do estado de referência.</span><span class="sxs-lookup"><span data-stu-id="69231-108">This effect can be modelled by considering excitations of electrons out of the reference state.</span></span> <span data-ttu-id="69231-109">As correlações não dinâmicas surgem quando a função de onda é dominada por duas ou mais configurações na ordem zero, mesmo para conseguir apenas uma descrição qualitativa do sistema.</span><span class="sxs-lookup"><span data-stu-id="69231-109">Non-dynamic correlations arise when the wavefunction is dominated by two or more configurations at zeroth order, even to achieve only a qualitative description of the system.</span></span>
<span data-ttu-id="69231-110">Isto requer uma superposição de determinantes e é um exemplo de uma função de onda multireferência.</span><span class="sxs-lookup"><span data-stu-id="69231-110">This necessitates a superposition of determinants and is an example of a multireference wavefunction.</span></span>

<span data-ttu-id="69231-111">A biblioteca de química fornece uma maneira de especificar uma função de onda de ordem zero para o problema multireferência como uma superposição de determinantes.</span><span class="sxs-lookup"><span data-stu-id="69231-111">The chemistry library provides a way to specify a zeroth order wavefunction for the multireference problem as a superposition of determinants.</span></span> <span data-ttu-id="69231-112">Esta abordagem, a que chamamos funções de onda multireferência escassas, é eficaz quando apenas alguns componentes são suficientes para especificar a superposição.</span><span class="sxs-lookup"><span data-stu-id="69231-112">This approach, which we call sparse multireference wavefunctions, is effective when only a few components suffice to specify the superposition.</span></span> <span data-ttu-id="69231-113">A biblioteca também fornece um método para incluir correlações dinâmicas em cima de uma referência determinante única através do ansatz de agrupamento unitário generalizado.</span><span class="sxs-lookup"><span data-stu-id="69231-113">The library also provides a method to include dynamic correlations on top of a single-determinant reference via the generalized unitary coupled-cluster ansatz.</span></span> <span data-ttu-id="69231-114">Além disso, também constrói circuitos quânticos que geram estes estados num computador quântico.</span><span class="sxs-lookup"><span data-stu-id="69231-114">Furthermore, it also constructs quantum circuits that generate these states on a quantum computer.</span></span> <span data-ttu-id="69231-115">Estes estados podem ser especificados no [esquema de Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), e também fornecemos a funcionalidade para especificar manualmente estes estados através da biblioteca de química.</span><span class="sxs-lookup"><span data-stu-id="69231-115">These states may be specified in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), and we also provide the functionality to manually specify these states through the chemistry library.</span></span>

## <a name="sparse-multi-reference-wavefunction"></a><span data-ttu-id="69231-116">Função de onda multi-referência escassa</span><span class="sxs-lookup"><span data-stu-id="69231-116">Sparse multi-reference wavefunction</span></span>
<span data-ttu-id="69231-117">Um estado de multi-referências $\ket{\psi_{\rm {MCSCF}}}} pode ser especificado explicitamente como uma combinação linear de determinantes $N$-eletrões Slater.</span><span class="sxs-lookup"><span data-stu-id="69231-117">A multi-reference state $\ket{\psi_{\rm {MCSCF}}}$ may be specified explicitly as a linear combination of $N$-electron Slater determininants.</span></span>
<span data-ttu-id="69231-118">\start{align} \ket{\psi_{\rm {\rm {MCSCF}}} \propto \sum_{i_1 < i_2 < \cdots < i_N} \lambda_{i_1,i_2,\cdots,i_N} a^\dagger_{i_1}a^\dagger_{i_2}\cdots a^\dagger_{i_N}\ket {0} .</span><span class="sxs-lookup"><span data-stu-id="69231-118">\begin{align} \ket{\psi_{\rm {MCSCF}}} \propto \sum_{i_1 < i_2 < \cdots < i_N} \lambda_{i_1,i_2,\cdots,i_N} a^\dagger_{i_1}a^\dagger_{i_2}\cdots a^\dagger_{i_N}\ket{0}.</span></span>
<span data-ttu-id="69231-119">\end{align} Por exemplo, o estado $\propto (0,1 a^\dagger_1a^\\\dagger_2a^\dagger_6 - 0,2 a^\dagger_2a^\\dagger_1a^\\dagger_5)\ket {0} $ pode ser especificado na biblioteca de química da seguinte forma.</span><span class="sxs-lookup"><span data-stu-id="69231-119">\end{align} For example, the state $\propto(0.1 a^\dagger_1a^\dagger_2a^\dagger_6 - 0.2 a^\dagger_2a^\dagger_1a^\dagger_5)\ket{0}$ may be specified in the chemistry library as follows.</span></span>
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
<span data-ttu-id="69231-120">Esta representação explícita dos componentes da superposição é eficaz quando apenas alguns componentes precisam de ser especificados.</span><span class="sxs-lookup"><span data-stu-id="69231-120">This explicit representation of the superposition components is effective when only a few components need to be specified.</span></span> <span data-ttu-id="69231-121">Deve-se evitar a utilização desta representação quando são necessários muitos componentes para capturar com precisão o estado pretendido.</span><span class="sxs-lookup"><span data-stu-id="69231-121">One should avoid using this representation when many components are required to accurately capture the desired state.</span></span> <span data-ttu-id="69231-122">A razão para isso é o custo do portão do circuito quântico que prepara este estado num computador quântico, que escala pelo menos linearmente com o número de componentes de superposição, e no máximo quadraticamente com a norma única das amplitudes de superposição.</span><span class="sxs-lookup"><span data-stu-id="69231-122">The reason for this is the gate cost of quantum circuit that prepares this state on a quantum computer, which scales at least linearly with the number of superposition components, and at most quadratically with the one-norm of the superposition amplitudes.</span></span>

## <a name="unitary-coupled-cluster-wavefunction"></a><span data-ttu-id="69231-123">Função unitária de ondas de aglomerados</span><span class="sxs-lookup"><span data-stu-id="69231-123">Unitary coupled-cluster wavefunction</span></span>
<span data-ttu-id="69231-124">Também é possível especificar uma função unitária de acoplar-cluster de ondas $\ket{\psi_{\rm {{\rm {UCC}}}} usando a biblioteca de farmácia.</span><span class="sxs-lookup"><span data-stu-id="69231-124">It is also possible to specify a unitary coupled-cluster wavefunction $\ket{\psi_{\rm {UCC}}}$ using the chemistery library.</span></span> <span data-ttu-id="69231-125">Nesta situação, temos um estado de referência único determinante, por exemplo, $\ket{\psi_{\rm{SCF}}}}$.</span><span class="sxs-lookup"><span data-stu-id="69231-125">In this situation, we have a single-determinant reference state, say, $\ket{\psi_{\rm{SCF}}}$.</span></span> <span data-ttu-id="69231-126">Os componentes da função unitária de ondas acopladas são então especificados implicitamente através de um operador unitário que atua num estado de referência.</span><span class="sxs-lookup"><span data-stu-id="69231-126">The components of the unitary coupled-cluster wavefunction are then specified implicity through a unitary operator acting on a reference state.</span></span>
<span data-ttu-id="69231-127">Este operador unitário é comumente escrito como $e^{T-T^\dagger}$, onde $T-T^\dagger$ é o operador de cluster anti-hermitiano.</span><span class="sxs-lookup"><span data-stu-id="69231-127">This unitary operator is commonly written as $e^{T-T^\dagger}$, where $T-T^\dagger$ is the anti-Hermitian cluster operator.</span></span> <span data-ttu-id="69231-128">Assim\ \start{align} \ket{\psi_{\rm {{rm {UCC}}} = e^{T^\dagger}\ket{\psi_{\rm{SCF}}}</span><span class="sxs-lookup"><span data-stu-id="69231-128">Thus \begin{align} \ket{\psi_{\rm {UCC}}} = e^{T-T^\dagger}\ket{\psi_{\rm{SCF}}}.</span></span>
<span data-ttu-id="69231-129">\end{align}</span><span class="sxs-lookup"><span data-stu-id="69231-129">\end{align}</span></span>

<span data-ttu-id="69231-130">Também é comum dividir o operador de cluster $T = T_1 + T_2 + \cdots$ em partes, onde cada parte $T_j$ contém termos de $j$-body.</span><span class="sxs-lookup"><span data-stu-id="69231-130">It is also common to split the cluster operator $T = T_1 + T_2 + \cdots$ into parts, where each part $T_j$ contains $j$-body terms.</span></span> <span data-ttu-id="69231-131">Na teoria do cluster acoplado generalizado, o operador de cluster de um corpo (singles) é da forma \start{align} T_1 = \sum_{pq}t^{p}_{q} a^\dagger_p a_q, \end{align}</span><span class="sxs-lookup"><span data-stu-id="69231-131">In generalized coupled-cluster theory, the one-body cluster operator (singles) is of the form \begin{align} T_1 = \sum_{pq}t^{p}_{q} a^\dagger_p a_q, \end{align}</span></span>

<span data-ttu-id="69231-132">e o operador de cluster de duas partes (duplos) é do formulário \start{align} T_2 = \sum_{pqrs}t^{pq}_{rs} a^\dagger_p a^\dagger_q a_r a_s.</span><span class="sxs-lookup"><span data-stu-id="69231-132">and two-body cluster operator (doubles) is of the form \begin{align} T_2 = \sum_{pqrs}t^{pq}_{rs} a^\dagger_p a^\dagger_q a_r a_s.</span></span>
<span data-ttu-id="69231-133">\end{align}</span><span class="sxs-lookup"><span data-stu-id="69231-133">\end{align}</span></span>

<span data-ttu-id="69231-134">Termos de ordem superior (triplos, quádruplos, etc.) são possíveis, mas não suportados atualmente pela biblioteca de química.</span><span class="sxs-lookup"><span data-stu-id="69231-134">Higher-order terms (triples, quadruples, etc.) are possible, but not currently supported by the chemistry library.</span></span>

<span data-ttu-id="69231-135">Por exemplo, deixe $\ket{\psi_{\rm{SCF}}} = a^\dagger_1 a^\dagger_2\ket {0} $, e deixe $T= 0,123 a^\dagger_0 a_1 + 0,456 a^dagger_0a^\dagger_3 a_1 a_2 - 0,789 a\dagger_3a^dagger_2 a_1 a_0$.</span><span class="sxs-lookup"><span data-stu-id="69231-135">For example, let $\ket{\psi_{\rm{SCF}}} = a^\dagger_1 a^\dagger_2\ket{0}$, and let $T= 0.123 a^\dagger_0 a_1 + 0.456 a^\dagger_0a^\dagger_3 a_1 a_2 - 0.789 a^\dagger_3a^\dagger_2 a_1 a_0$.</span></span> <span data-ttu-id="69231-136">Então este estado é instantâneo na biblioteca de química da seguinte forma.</span><span class="sxs-lookup"><span data-stu-id="69231-136">Then this state is instantiated in the chemistry library as follows.</span></span>
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

<span data-ttu-id="69231-137">A convervação de centrifugação pode ser explicitada especificando `SpinOrbital` índices em vez de índices inteiros.</span><span class="sxs-lookup"><span data-stu-id="69231-137">Spin convervation may be made explicit by instead specifying `SpinOrbital` indices instead of integer indices.</span></span> <span data-ttu-id="69231-138">Por exemplo, deixe $\ket{\psi_{\rm{SCF}}} = a^\dagger_{1,\uparrow} a^\dagger_{2, \downarrow}\ket {0} $, e deixe $T= 0,123 a^\dagger_{0, \uparrow} a_{1, \uparrow} + 0,456 a^\dagger_{0, \uparrow} a^\dagger_{3, \downarrow} a_{1, \uparrow} a_{2, \downarrow} - 0,789 a^\dagger_{3,\uparrow} a^\dagger_{2,\uparrow} a_{1,\uparrow} a_{0, \uparrow}$ ser conservação de rotação.</span><span class="sxs-lookup"><span data-stu-id="69231-138">For example, let $\ket{\psi_{\rm{SCF}}} = a^\dagger_{1,\uparrow} a^\dagger_{2, \downarrow}\ket{0}$, and let $T= 0.123 a^\dagger_{0, \uparrow} a_{1, \uparrow} + 0.456 a^\dagger_{0, \uparrow} a^\dagger_{3, \downarrow} a_{1, \uparrow} a_{2, \downarrow} - 0.789 a^\dagger_{3,\uparrow} a^\dagger_{2,\uparrow} a_{1,\uparrow} a_{0, \uparrow}$ be spin convserving.</span></span> <span data-ttu-id="69231-139">Então este estado é instantâneo na biblioteca de química da seguinte forma.</span><span class="sxs-lookup"><span data-stu-id="69231-139">Then this state is instantiated in the chemistry library as follows.</span></span>
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

<span data-ttu-id="69231-140">Também fornecemos uma função de conveniência que enumera todos os operadores de clusters que aniquilam apenas os orbitais de spin-orbitals ocupados e excitam apenas os orbitais de spin-orbitals desocupados.</span><span class="sxs-lookup"><span data-stu-id="69231-140">We also provide a convenience function that enumerates over all spin-conversing cluster operators that annihilate only occupied spin-orbitals and excite to only unoccupied spin-orbitals.</span></span>
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
