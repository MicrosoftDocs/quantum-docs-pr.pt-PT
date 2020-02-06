---
title: Segunda Quantificação  Microsoft Docs
description: Segundo Doscs Conceituais de Quantificação
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.secondquantization
ms.openlocfilehash: 4b7b5a6be6d0c1f3520128609e6b9fa83e5460d5
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036428"
---
# <a name="second-quantization"></a><span data-ttu-id="f026b-103">Segunda Quantificação</span><span class="sxs-lookup"><span data-stu-id="f026b-103">Second Quantization</span></span>

<span data-ttu-id="f026b-104">A segunda quantificação analisa o problema da estrutura electrónica através de uma lente diferente.</span><span class="sxs-lookup"><span data-stu-id="f026b-104">Second quantization looks at the problem of electronic structure through a different lens.</span></span>
<span data-ttu-id="f026b-105">Em vez de atribuir cada um dos eletrões $N_e$ a um estado específico (ou orbital), a segunda quantificação rastreia cada orbital e armazena se existe um eletrão presente em cada um deles e, ao mesmo tempo, assegura automaticamente propriedades de simetria do função de onda correspondente.</span><span class="sxs-lookup"><span data-stu-id="f026b-105">Rather than assigning each of the $N_e$ electrons to a specific state (or orbital), second quantization tracks each orbital and stores whether there is an electron present in each of them and at the same time automatically ensures symmetry properties of the corresponding wave function.</span></span>
<span data-ttu-id="f026b-106">Isto é importante porque permite especificar os modelos de química quântica sem ter que se preocupar com a anti-simmetrização do estado de entrada (como é necessário para fermiões) e também porque a segunda quantificação permite que tais modelos sejam simulados usando um pequeno quantum computadores.</span><span class="sxs-lookup"><span data-stu-id="f026b-106">This is important because it allows quantum chemistry models to be specified without having to worry about anti-symmetrizing the input state (as is required for fermions) and also because second quantization allows such models to be simulated using small quantum computers.</span></span>

<span data-ttu-id="f026b-107">Como exemplo de segunda quantificação em ação, vamos assumir que $\psi_0\cdots \psi_{N-1}$ são um conjunto ortonormal de orbitais espaciais.</span><span class="sxs-lookup"><span data-stu-id="f026b-107">As an example of second quantization in action, let's assume that $\psi_0\cdots \psi_{N-1}$ are an orthonormal set of spatial orbitals.</span></span>
<span data-ttu-id="f026b-108">Estes orbitais são escolhidos para representar o sistema o mais precisamente possível dentro do conjunto de base finita considerado.</span><span class="sxs-lookup"><span data-stu-id="f026b-108">These orbitals are chosen to represent the system as accurately as possible within the finite basis set considered.</span></span>
<span data-ttu-id="f026b-109">Um exemplo comum desses orbitais são os orbitais atómicos que formam uma base eigenpara o átomo de hidrogénio.</span><span class="sxs-lookup"><span data-stu-id="f026b-109">A common example of such orbitals are atomic orbitals which form an eigenbasis for the hydrogen atom.</span></span>
<span data-ttu-id="f026b-110">Como os eletrões têm dois estados de rotação, dois eletrões podem ser amontoados em cada um desses orbitais espaciais.</span><span class="sxs-lookup"><span data-stu-id="f026b-110">Because electrons have two spin states, two electrons can be crammed into each such spatial orbital.</span></span>
<span data-ttu-id="f026b-111">Ou seja, os estados de base válidas são do formulário $\psi_{0,\uparrow},\ldots,\psi_{N-1,\uparrow}, \psi_{{0,\downarrow},\ldots,\psi_{N-1,\downarrow}$ onde $\uparrow$ e $downarrow$ são rótulos que especificam os dois eigenstates do grau de centrifugação liberdade.</span><span class="sxs-lookup"><span data-stu-id="f026b-111">That is to say, the valid basis states are of the form $\psi_{0,\uparrow},\ldots,\psi_{N-1,\uparrow}, \psi_{0,\downarrow},\ldots,\psi_{N-1,\downarrow}$ where $\uparrow$ and $\downarrow$ are labels that specify the two eigenstates of the spin degree of freedom.</span></span>
<span data-ttu-id="f026b-112">Este índice combinado de $(j,\sigma)$ para $\sigma \in \{\uparrow,\downarrow\}$ é chamado de spin-orbital porque armazena tanto o espaço como o grau de rotação da liberdade.</span><span class="sxs-lookup"><span data-stu-id="f026b-112">This combined index of $(j,\sigma)$ for $\sigma \in \{\uparrow,\downarrow\}$ is called a spin-orbital because it stores both the spatial as well as the spin degree of freedom.</span></span>
<span data-ttu-id="f026b-113">Na biblioteca de química, os orbitais de rotação são armazenados numa estrutura de dados `SpinOrbital`, e são criados da seguinte forma.</span><span class="sxs-lookup"><span data-stu-id="f026b-113">In the chemistry library, spin-orbitals are stored in a `SpinOrbital` data structure, and are created as follows.</span></span>

```csharp
    // First, we load the namespace containing spin-orbital objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // First, we assign an orbital index, say `5`. Note that we use 0-indexing,
    // so this is the 6th orbital.
    var orbitalIdx = 5;

    // Second, we assign a spin index, say `Spin.u` for spin up or `Spin.d` for spin down.
    var spin = Spin.d;

    // the spin-orbital (5, ↓) is then
    var spinOrbital = new SpinOrbital(orbitalIdx, spin);

    // A tuple `(int, Spin)` is also implicitly recognized as a spin-orbital.
    (int, Spin) tuple = (orbitalIdx, spin);

    // We explicitly specify the type of `spinOrbital1` to demonstrate
    // the implicit cast to `SpinOrbital`.
    SpinOrbital spinOrbital1 = tuple;
```

<span data-ttu-id="f026b-114">Isto significa que podemos pensar formalmente na base tanto para a parte giratória como para a parte espacial da função de onda como $\psi_{0} \cdots \psi_ {2N-1}$ onde cada um dos índices agora é uma enumeração de um $(j,\sigma)$.</span><span class="sxs-lookup"><span data-stu-id="f026b-114">This means that we can formally think of the basis for both the spin and spatial part of the wave function as $\psi_{0} \cdots \psi_{2N-1}$ where each of the indices now is an enumeration of a $(j,\sigma)$.</span></span>
<span data-ttu-id="f026b-115">Uma possível enumeração é $g (j,\sigma) = j+N\sigma'$.</span><span class="sxs-lookup"><span data-stu-id="f026b-115">One possible enumeration is $g(j,\sigma) = j+N\sigma'$.</span></span>
<span data-ttu-id="f026b-116">Outra possível enumeração é $h (j,\sigma) = 2\*j + \sigma$.</span><span class="sxs-lookup"><span data-stu-id="f026b-116">Another possible enumeration is $h(j,\sigma) = 2\*j + \sigma$.</span></span>
<span data-ttu-id="f026b-117">A biblioteca de química quântica pode usar estas convenções, e os orbitais de rotação em tal codificação podem ser instantâneos da seguinte forma.</span><span class="sxs-lookup"><span data-stu-id="f026b-117">The quantum chemistry library can use these conventions, and the spin-orbitals in such an encoding can be instantiated as follows.</span></span>

```csharp
    // Let us use the spin orbital created in the previous snippet.
   var spinOrbital = new SpinOrbital(5, Spin.d);

   // Let us set the total number of orbitals to be say, `7`.
   var nOrbitals = 7;

    // This converts a spin-orbital index to a unique integer, in this case `12`,
    // using the formula `g(j,σ)`.
    var integerIndexHalfUp = spinOrbital.ToInt(IndexConvention.HalfUp);

    // This converts a spin-orbital index to a unique integer, in this case `11`,
    // using the formula `h(j,σ)`.
    var integerIndexUpDown = spinOrbital.ToInt(IndexConvention.UpDown);

    // The default conversion uses the formula `h(j,σ)`, in this case `11`.
    var integerIndexDefault = spinOrbital.ToInt();
```

<span data-ttu-id="f026b-118">Para os sistemas fermiónicos, o princípio da exclusão de Pauli impede que mais do que um eletrão esteja presente em qualquer rotação-orbital ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="f026b-118">For fermionic systems, the Pauli exclusion principle prevents more than one electron from being present in any spin-orbital at the same time.</span></span>
<span data-ttu-id="f026b-119">Isto significa que podemos escrever os dois estados legais por $\psi_1$ como \{equação} \psi_1 \seta direita \start{cases} \ket{0}_1 & \text{if $\psi_1$ is not ocupado,} </span><span class="sxs-lookup"><span data-stu-id="f026b-119">This means that we can write the two legal states for $\psi_1$ as \begin{equation} \psi_1 \rightarrow \begin{cases} \ket{0}_1 & \text{if $\psi_1$ is not occupied,} </span></span>\\\
<span data-ttu-id="f026b-120">\ket{1}_1 & \text{if $\psi_1$ is ocupado.}</span><span class="sxs-lookup"><span data-stu-id="f026b-120">\ket{1}_1 & \text{if $\psi_1$ is occupied.}</span></span> <span data-ttu-id="f026b-121">\end{cases} \end{equation} Esta codificação é ótima para computadores quânticos porque significa que podemos armazenar a ocupação electrónica como uma única bit quântica.</span><span class="sxs-lookup"><span data-stu-id="f026b-121">\end{cases} \end{equation} This encoding is great for quantum computers because it means that we can store the electronic occupation as a single quantum bit.</span></span>

<span data-ttu-id="f026b-122">A ocupação indica que os orbitais de rotação de $2N$ podem igualmente ser armazenados em qubits de $2N$.</span><span class="sxs-lookup"><span data-stu-id="f026b-122">The occupation states for the $2N$ spin orbitals can similarly be stored in $2N$ qubits.</span></span>
<span data-ttu-id="f026b-123">Como exemplo, se $N=2$ então o Estado $${0} \ket{1} \ket{1} \ket{0}, $$</span><span class="sxs-lookup"><span data-stu-id="f026b-123">As an example, if $N=2$ then the state $$ \ket{0} \ket{1} \ket{1} \ket{0}, $$</span></span>

<span data-ttu-id="f026b-124">corresponderia aos orbitais de giro $1$ e $2$ sendo ocupados com o restante vazio.</span><span class="sxs-lookup"><span data-stu-id="f026b-124">would correspond to spin orbitals $1$ and $2$ being occupied with the remainder empty.</span></span>
<span data-ttu-id="f026b-125">Da mesma forma, o estado $$ \ket{0} \equiv \ket{0} _{0} \cdots \ket{0}_ {N-1}, $$</span><span class="sxs-lookup"><span data-stu-id="f026b-125">Similarly, the state $$ \ket{0} \equiv \ket{0}_{0} \cdots \ket{0}_{N-1}, $$</span></span>

<span data-ttu-id="f026b-126">não tem eletrões e é conhecido como o "estado de vácuo".</span><span class="sxs-lookup"><span data-stu-id="f026b-126">has no electrons and is known as the 'vacuum state'.</span></span>

<span data-ttu-id="f026b-127">Um belo efeito colateral da segunda quantificação é que já não temos de acompanhar explicitamente a anti-simetria do estado quântico.</span><span class="sxs-lookup"><span data-stu-id="f026b-127">A beautiful side-effect of second quantization is that we no longer have to explicitly keep track of the anti-symmetry of the quantum state.</span></span>
<span data-ttu-id="f026b-128">Isto porque, como veremos, a anti-simetria do Estado representa-se, em vez disso, através das regras anti-comutação dos operadores que criam e destroem as ocupações electrónicas de um orbital de rotação.</span><span class="sxs-lookup"><span data-stu-id="f026b-128">This is because, as we will see, the anti-symmetry of the state represents itself instead through the anti-commutation rules of the operators that create and destroy electronic occupations of a spin orbital.</span></span>

## <a name="fermionic-operators"></a><span data-ttu-id="f026b-129">Operadores fermiónicos</span><span class="sxs-lookup"><span data-stu-id="f026b-129">Fermionic operators</span></span>

<span data-ttu-id="f026b-130">Os dois operadores fundamentais que atuam sobre os vetores de base segundo quantificado são conhecidos como operadores de criação e aniquilação.</span><span class="sxs-lookup"><span data-stu-id="f026b-130">The two fundamental operators that act on the second-quantized basis vectors are known as creation and annihilation operators.</span></span>
<span data-ttu-id="f026b-131">Estes operadores inserem ou destroem eletrões num determinado local.</span><span class="sxs-lookup"><span data-stu-id="f026b-131">These operators insert or destroy electrons at a particular location.</span></span>
<span data-ttu-id="f026b-132">Estes são denotados $a^\dagger_j$ e $a_j$ respectivamente.</span><span class="sxs-lookup"><span data-stu-id="f026b-132">These are denoted $a^\dagger_j$ and $a_j$ respectively.</span></span>

<span data-ttu-id="f026b-133">Por exemplo, \start{align} a^\dagger_1 \ket{0}_1 = \ket{1}_1,quad a^\dagger_1 \ket{1}_1 = 0,\quad a_1 \ket{0}_1 = 0,\quad a_1 \ket{1}_1 = \ket{0}_1.</span><span class="sxs-lookup"><span data-stu-id="f026b-133">For example, \begin{align} a^\dagger_1 \ket{0}_1 = \ket{1}_1,\quad a^\dagger_1 \ket{1}_1 = 0,\quad a_1 \ket{0}_1 = 0,\quad a_1 \ket{1}_1 = \ket{0}_1.</span></span>
<span data-ttu-id="f026b-134">\end{align} Note que aqui $a^\dagger_1 \ket{1}_1=0$ e $a_1 \ket{0}_1$ rendimento do vetor zero e não $\ket{0}_1$.</span><span class="sxs-lookup"><span data-stu-id="f026b-134">\end{align} Note that here $a^\dagger_1 \ket{1}_1=0$ and $a_1 \ket{0}_1$ yield the zero-vector not $\ket{0}_1$.</span></span>
<span data-ttu-id="f026b-135">Por conseguinte, estes operadores não são hermitianos nem unitários.</span><span class="sxs-lookup"><span data-stu-id="f026b-135">Such operators are therefore neither Hermitian nor unitary.</span></span>
<span data-ttu-id="f026b-136">Representamos operadores gerais de criação e aniquilação utilizando o tipo <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1>.</span><span class="sxs-lookup"><span data-stu-id="f026b-136">We represent general creation and annihilation operators using the <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> type.</span></span>
<span data-ttu-id="f026b-137">Por exemplo, um único operador de criação é representado como segue.</span><span class="sxs-lookup"><span data-stu-id="f026b-137">For instance, a single creation operator is represented as follow.</span></span>

```csharp
    // We load the namespace containing ladder operator objects.
    using Microsoft.Quantum.Chemistry.LadderOperators;

    // Let us use the spin orbital created in the previous snippet.
    var spinOrbitalInteger = new SpinOrbital(5, Spin.d).ToInt();

    // We specify either a creation or annihilation operator using 
    // the enumerable type `RaisingLowering.u` or `RaisingLowering.d`
    // respectively;
    var creationEnum = RaisingLowering.u;

    // The type representing a creation operator is then initialized 
    // as follows. Here, we index these operators with integers.
    // Hence we initialize the generic ladder operator with an
    // integer index type.
    var ladderOperator0 = new LadderOperator<int>(creationEnum, spinOrbitalInteger);

    // An alternate constructor for a LadderOperator instead uses
    // a tuple.
    var ladderOperator1 = new LadderOperator<int>((creationEnum, spinOrbitalInteger));
```

<span data-ttu-id="f026b-138">Também usando tais operadores podemos expressar $$ \ket{0} \ket{1} \ket{1} \ket{0} = a^\dagger_1 a^\dagger_2 \ket{0}{{\otimes 4}.</span><span class="sxs-lookup"><span data-stu-id="f026b-138">Also using such operators we can express $$ \ket{0} \ket{1} \ket{1} \ket{0} = a^\dagger_1 a^\dagger_2 \ket{0}^{\otimes 4}.</span></span>
<span data-ttu-id="f026b-139">$$ Esta sequência de operadores seria construída dentro C# da biblioteca de simulação hamiltoniana usando código semelhante ao caso orbital de rotação única acima considerado:</span><span class="sxs-lookup"><span data-stu-id="f026b-139">$$ This sequence of operators would be constructed within the Hamiltonian simulation library using C# code that is similar to the single-spin orbital case considered above above:</span></span>
```csharp
    // We load the namespace containing fermion-related objects.
    using Microsoft.Quantum.Chemistry.Fermion;

    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We can convert this array of tuples to a sequence of ladder
    // operators using the `ToLadderSequence()` methods.
    var ladderSequences = indices.ToLadderSequence();

    // Sequences of ladder operators are quite general. For instance,
    // they could be bosonic operators, instead of fermionic operators.
    // We specialize them by constructing a `FermionTerm` representing 
    // a fermion creation operator on the index `2` followed by `1`.
    var fermionTerm = new FermionTerm(ladderSequences);
```

<span data-ttu-id="f026b-140">Para um sistema de $k$ Fermions, em segunda quantificação a ação do operador de criação $a^\dagger_i$ é dada por $$ a^\dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k } = (-1)^{S_i} \ket{n_1, n_2, \ldots, 1_i , \ldots, n_k}, $$ e $$ a^\dagger_i \ket{n_1, n_2, \ldots, \ldots 1_i, \ldots, n_k } = 0, $$ onde $S_i = \sum_{j<i} a^\dagger_j a_j$ mede o número total de Fermions que estão no estado de uma única partícula e que têm um índice $j < i$.</span><span class="sxs-lookup"><span data-stu-id="f026b-140">For a system of $k$ Fermions, in second quantization the action of the creation operator $a^\dagger_i$ is given by $$ a^\dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k } = (-1)^{S_i} \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k}, $$ and $$ a^\dagger_i \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k } = 0, $$ where $S_i = \sum_{j<i} a^\dagger_j a_j$ measures the total number of Fermions that are in the state of a single particle and that have an index $j < i$.</span></span>

<span data-ttu-id="f026b-141">Um terceiro operador também é frequentemente utilizado em segundas representações quantificadas.</span><span class="sxs-lookup"><span data-stu-id="f026b-141">A third operator is also often used in second quantized representations.</span></span>
<span data-ttu-id="f026b-142">Este operador é conhecido como o operador de números e é definido por \start{equation} n_i = a^\dagger_i a_i.</span><span class="sxs-lookup"><span data-stu-id="f026b-142">This operator is known as the number operator and is defined by \begin{equation} n_i = a^\dagger_i a_i.</span></span>
<span data-ttu-id="f026b-143">\end{equation} Este operador conta a ocupação de um dado orbital de centrifugação, ou seja, \start{align} n_i{0}_i & 0\nonumber</span><span class="sxs-lookup"><span data-stu-id="f026b-143">\end{equation} This operator counts the occupation of a given spin orbital, which is to say \begin{align} n_i \ket{0}_i &= 0\nonumber</span></span>\\\
<span data-ttu-id="f026b-144">n_i \ket{1}_i &= \ket{1}_i.</span><span class="sxs-lookup"><span data-stu-id="f026b-144">n_i \ket{1}_i &= \ket{1}_i.</span></span>
<span data-ttu-id="f026b-145">\end{align} Semelhante aos exemplos acima `FermionTerm`, este operador de número é construído da seguinte forma.</span><span class="sxs-lookup"><span data-stu-id="f026b-145">\end{align} Similar to the above `FermionTerm` examples, this number operator is constructed as follows.</span></span>
```csharp
    // Let us use a new method to compactly create a sequence of ladder
    // operators. Note that we have omitted specifying whether the 
    // operators are raising or lowering. In this case, the first half
    // will be raising operators, and the second half will be lowering 
    // operators.
    var indices = new[] { 1, 1 }.ToLadderSequence();

    // We now construct a `FermionTerm` representing an annihilation operator
    // on the index 1 followed by the creation operator on the index 1.
    var fermionTerm0 = new FermionTerm(indices);
```

<span data-ttu-id="f026b-146">Uma subtileza surge quando se utilizam operadores de criação ou aniquilação em sistemas fermiónicos.</span><span class="sxs-lookup"><span data-stu-id="f026b-146">A subtlety emerges though when using creation or annihilation operators in fermionic systems.</span></span>
<span data-ttu-id="f026b-147">Exigimos que qualquer estado quântico válido seja antissimétrico sob troca de rótulos.</span><span class="sxs-lookup"><span data-stu-id="f026b-147">We require that any valid quantum state is anti-symmetric under exchange of labels.</span></span>
<span data-ttu-id="f026b-148">Isto significa que $$ a^\dagger_2 a^\dagger_1 \ket{0} = -a^\dagger_1 a^\dagger_2 \ket{0}.</span><span class="sxs-lookup"><span data-stu-id="f026b-148">This means that $$ a^\dagger_2 a^\dagger_1 \ket{0} = -a^\dagger_1 a^\dagger_2 \ket{0}.</span></span>
<span data-ttu-id="f026b-149">$$ Estes operadores são ditos 'anti-comutação' e, em geral, para qualquer $i, j$ temos que \begin{align} a^\dagger_i a^\dagger_j = -(1-\delta_{i,j})a^\dagger_j a^\dagger_i,quad a^\dagger_i a_j =\delta_{i,j} - a_j a^\dagger_i.</span><span class="sxs-lookup"><span data-stu-id="f026b-149">$$ Such operators are said to 'anti-commute' and in general for any $i, j$ we have that \begin{align} a^\dagger_i a^\dagger_j  = -(1-\delta_{i,j})a^\dagger_j a^\dagger_i,\quad a^\dagger_i a_j =\delta_{i,j} - a_j a^\dagger_i.</span></span>
<span data-ttu-id="f026b-150">\end{align} Assim, as duas seguintes <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> casos são consideradas inequivalentes</span><span class="sxs-lookup"><span data-stu-id="f026b-150">\end{align} Thus the following two <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> instances are considered inequivalent</span></span>
```csharp
    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We now construct a `LadderSequence` representing a creation operator
    // on the index 1 followed by 2, then a term with the reverse ordering.
    var laddderSeqeunce = indices.ToLadderSequence();
    var laddderSeqeunceReversed = indices.Reverse().ToLadderSequence();

    // The following Boolean is `false`.
    var equal = laddderSeqeunce == laddderSeqeunceReversed;
```

<span data-ttu-id="f026b-151">A exigência de que cada um dos operadores de criação anti-deslocação significa que a utilização de uma segunda representação quantificada obvia os desafios enfrentados pela anti-simetria dos Fermions.</span><span class="sxs-lookup"><span data-stu-id="f026b-151">The requirement that each of the creation operators anti-commute means that using a second quantized representation does obviate the challenges faced by the anti-symmetry of Fermions.</span></span>
<span data-ttu-id="f026b-152">Em vez disso, o desafio ressurge na nossa definição de operadores de criação.</span><span class="sxs-lookup"><span data-stu-id="f026b-152">Instead the challenge re-emerges in our definition of the creation operators.</span></span> 

<span data-ttu-id="f026b-153">Utilizando as regras anti-comutação, algumas `LadderSequence` casos correspondem à mesma sequência de operadores fermiónicos, às vezes até um sinal negativo.</span><span class="sxs-lookup"><span data-stu-id="f026b-153">Using the anti-commutation rules, some `LadderSequence` instances actually correspond to the same sequence of fermionic operators, sometimes up to a minus sign.</span></span>
<span data-ttu-id="f026b-154">Por exemplo, considere o $a_0^\dagger hamiltonian a_1^\punhal a_1 a_0 = - a_1\dagger a_0^\dagger a_0^\dagger a_1 a_0$.</span><span class="sxs-lookup"><span data-stu-id="f026b-154">For instance, consider the Hamiltonian $a_0^\dagger a_1^\dagger a_1 a_0 = - a_1^\dagger a_0^\dagger a_1 a_0$.</span></span>
<span data-ttu-id="f026b-155">Isto motiva-nos a definir uma encomenda canónica para cada `FermionTerm`.</span><span class="sxs-lookup"><span data-stu-id="f026b-155">This motivates us to define a canonical ordering for every `FermionTerm`.</span></span>
<span data-ttu-id="f026b-156">Qualquer `FermionTerm` é automaticamente colocada em ordem canónica da seguinte forma.</span><span class="sxs-lookup"><span data-stu-id="f026b-156">Any `FermionTerm` is automatically put into canonical order as follows.</span></span>
```csharp
    // We now construct two `FermionTerms` that are equivalent with respect to
    // anti-commutation up to a sign change.
    var fermionTerm0 = new FermionTerm(new[] { 0, 1, 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 1, 0, 1, 0 }.ToLadderSequence());

    // The following Boolean is `true`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // The change in sign is not compared above, but is an internally tracked
    // property of `FermionTerm`.
    int sign0 = fermionTerm0.Coefficient;
    var sign1 = fermionTerm1.Coefficient;

    // The following Boolean is `false`.
    var signEqual = sign0 == sign1;
```

## <a name="second-quantized-fermionic-hamiltonian"></a><span data-ttu-id="f026b-157">Segundo-quantificado Fermionic Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="f026b-157">Second-Quantized Fermionic Hamiltonian</span></span>

<span data-ttu-id="f026b-158">Talvez não seja de estranhar que o Hamiltonian em [Modelos Quânticos de Sistemas Eletrónicos](xref:microsoft.quantum.chemistry.concepts.quantummodels) possa ser escrito em termos de criação e aniquilação dos operadores.</span><span class="sxs-lookup"><span data-stu-id="f026b-158">It is perhaps unsurprising that the Hamiltonian in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels) can be written in terms of creation and annihilation operators.</span></span>
<span data-ttu-id="f026b-159">Em particular, se $\psi\_j$ são os orbitais de rotação que formam a base então</span><span class="sxs-lookup"><span data-stu-id="f026b-159">In particular, if $\psi\_j$ are the spin orbitals that form the basis then</span></span>

<span data-ttu-id="f026b-160">\begin{equation} \hat{H} = \soma\_{pq} h\_{pq}a^\dagger\_p a\_q + \frac{1}{2}\sum\_{pqrs} h\_{pqrs}a^\dagger\_p a^\dagger\_q a\_ra\_s +h\_{\textrm nuc},\label{eq:totalHam} \end{equation} onde $h\_{\textrm nuc}$ é a energia nuclear (que é uma constante sob a aproximação born-oppenheimer) e</span><span class="sxs-lookup"><span data-stu-id="f026b-160">\begin{equation} \hat{H} = \sum\_{pq} h\_{pq}a^\dagger\_p a\_q + \frac{1}{2}\sum\_{pqrs} h\_{pqrs}a^\dagger\_p a^\dagger\_q a\_ra\_s +h\_{\textrm nuc},\label{eq:totalHam} \end{equation} where $h\_{\textrm nuc}$ is the nuclear energy (which is a constant under the Born-Oppenheimer approximation) and</span></span>

<span data-ttu-id="f026b-161">\begin{align} h\_{pq} &= \int\_{-\infty}\infty\infty \psi^ \_\*p(x\_1) \left(-\frac{\nabla^2}{2} +V(x\_1)\direita) \psi\_q(x\_1)\mathrm{d}^3x\_1, \end align{}</span><span class="sxs-lookup"><span data-stu-id="f026b-161">\begin{align} h\_{pq} &= \int\_{-\infty}^\infty \psi^\*\_p(x\_1) \left(-\frac{\nabla^2}{2} +V(x\_1)\right)  \psi\_q(x\_1)\mathrm{d}^3x\_1, \end{align}</span></span>

<span data-ttu-id="f026b-162">onde $V(x)$ é o potencial médio-campo, e</span><span class="sxs-lookup"><span data-stu-id="f026b-162">where $V(x)$ is the mean-field potential, and</span></span>

<span data-ttu-id="f026b-163">\begin{align} h\_{pqrs} &= \int\_{-\infty}^\int\_{-\infty}\infty\infty\infty\psi\_p^\*(x\_1)\psi\_q^\*(x\_2) \left(\frac{1}{/x_1-x_2} \right)\psi\_r(x\_2)\psi\_s(x\_1)\mathrm{d}^3x\_1\mathrm{d}^3x\_2.\label{eq :integrals} \end{align}</span><span class="sxs-lookup"><span data-stu-id="f026b-163">\begin{align} h\_{pqrs} &= \int\_{-\infty}^\infty \int\_{-\infty}^\infty\psi\_p^\*(x\_1)\psi\_q^\*(x\_2) \left(\frac{1}{|x_1-x_2|} \right)\psi\_r(x\_2)\psi\_s(x\_1)\mathrm{d}^3x\_1\mathrm{d}^3x\_2.\label{eq:integrals} \end{align}</span></span>

<span data-ttu-id="f026b-164">Os termos $h\_{pq}$ são referidos como integrales de um eletrão, porque todos esses termos envolvem apenas eletrões simples e $h\_{pqrs}$ são os integrais de dois eletrões.</span><span class="sxs-lookup"><span data-stu-id="f026b-164">The terms $h\_{pq}$ are referred to as one-electron integrals because all such terms only involve single electrons and likewise $h\_{pqrs}$ are the two-electron integrals.</span></span>
<span data-ttu-id="f026b-165">São chamados integrais porque a computação dos valores destes coeficientes requer uma integral.</span><span class="sxs-lookup"><span data-stu-id="f026b-165">They are called integrals because computing the values of these coefficients requires an integral.</span></span>
<span data-ttu-id="f026b-166">Os termos de um eletrão descrevem a energia cinética dos eletrões individuais e as suas interações com os campos elétricos dos núcleos.</span><span class="sxs-lookup"><span data-stu-id="f026b-166">The one electron terms describe the kinetic energy of the individual electrons and their interactions with the electric fields of the nuclei.</span></span>
<span data-ttu-id="f026b-167">Os dois eletrões integrais, por outro lado, descrevem as interações entre os eletrões.</span><span class="sxs-lookup"><span data-stu-id="f026b-167">The two-electron integrals on the other hand describe the interactions between the electrons.</span></span>

<span data-ttu-id="f026b-168">Uma intuição para o que estes termos significam pode ser recolhida a partir da criação e da aniquilação dos operadores que compõem cada um deles.</span><span class="sxs-lookup"><span data-stu-id="f026b-168">An intuition for what these terms mean can be gleaned from the creation and annihilation operators that comprise each of them.</span></span>
<span data-ttu-id="f026b-169">Por exemplo, $h_{pq}a^\dagger_p a_q$ descreve o eletrão pulando de $q orbital de rotação para girar orbital $p$.</span><span class="sxs-lookup"><span data-stu-id="f026b-169">For example, $h_{pq}a^\dagger_p a_q$ describes the electron hopping from spin orbital $q$ to spin orbital $p$.</span></span>
<span data-ttu-id="f026b-170">Da mesma forma, o termo $h_{pqrs} a^\dagger_p a^\dagger_q a_r a_s$ (para $p distintos, q,r,s$) descreve dois eletrões em orbitais de rotação $r$ e $s$ espalhando-se uns dos outros e acabando em órbitas de rotação $p$ e $q$.</span><span class="sxs-lookup"><span data-stu-id="f026b-170">Similarly, the term $h_{pqrs} a^\dagger_p a^\dagger_q a_r a_s$ (for distinct $p,q,r,s$) describes two electrons in spin orbitals $r$ and $s$ scattering off of each other and ending up in spin orbitals $p$ and $q$.</span></span>
<span data-ttu-id="f026b-171">Se $r=q$ e $p=s$ então $h_{prrp} a^\dagger_p a^\dagger_r a_p a_r = h_{prrp} n_p n_r$ dá a penalidade energética associada aos dois eletrões que estão perto um do outro, mas não descreve um processo dinâmico.</span><span class="sxs-lookup"><span data-stu-id="f026b-171">If $r=q$ and $p=s$ then $h_{prrp} a^\dagger_p a^\dagger_r a_r a_p = h_{prrp} n_p n_r$ gives the energy penalty associated with the two electrons being near each other, but does not describe a dynamical process.</span></span>

<span data-ttu-id="f026b-172">Podemos representar esses Hamiltonians usando a classe `FermionHamiltonian`, que é essencialmente uma lista contendo todos os casos `FermionTerm` desejados.</span><span class="sxs-lookup"><span data-stu-id="f026b-172">We may represent such Hamiltonians using the `FermionHamiltonian` class, which is essentially a list containing all the desired `FermionTerm` instances.</span></span>
<span data-ttu-id="f026b-173">Como os hamiltonianos são hermitianos por definição, indexamos termos usando o tipo mais especializado `HermitianFermionTerm` que também usa simetria hermitiana ao verificar se os termos são equivalentes.</span><span class="sxs-lookup"><span data-stu-id="f026b-173">As Hamiltonians are Hermitian by definition, we index terms using the more specialized type `HermitianFermionTerm` that also uses Hermitian symmetry when checking whether terms are equivalent.</span></span>

<span data-ttu-id="f026b-174">Construamos alguns exemplos ilustrativos.</span><span class="sxs-lookup"><span data-stu-id="f026b-174">Let us construct a few illustrative examples.</span></span>
<span data-ttu-id="f026b-175">Considere o Hamiltonian $\hat{H} = a_0^\dagger a_1 + a_1^\dagger a_0$.</span><span class="sxs-lookup"><span data-stu-id="f026b-175">Consider the Hamiltonian $\hat{H} = a_0^\dagger a_1 + a_1^\dagger a_0$.</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the terms to be added.
    var fermionTerm0 = new FermionTerm(new[] { 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 0, 1 }.ToLadderSequence());

    // These fermion terms are not equal. The following Boolean is `false`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // However, these terms are equal under Hermitian symmetry.
    // We also take the opportunity to demonstrate equivalent constructors
    // for hermitian fermion terms
    var hermitianFermionTerm0 = new HermitianFermionTerm(fermionTerm0);
    var hermitianFermionTerm1 = new HermitianFermionTerm(new[] { 0, 1 });

    // These Hermitian fermion terms are equal. The following Boolean is `true`.
    var hermitianSequenceEqual = hermitianFermionTerm0 == hermitianFermionTerm1;

    // We add the terms to the Hamiltonian with the appropriate coefficient.
    // Note that these terms are identical.
    hamiltonian.Add(hermitianFermionTerm0, 1.0);
    hamiltonian.Add(hermitianFermionTerm1, 1.0);
```
<span data-ttu-id="f026b-176">Podemos simplificar esta construção utilizando o facto de os operadores hamiltonianos serem operadores hermitianos.</span><span class="sxs-lookup"><span data-stu-id="f026b-176">We may simplify this construction using the fact that Hamiltonian operators are Hermitian operators.</span></span>
<span data-ttu-id="f026b-177">Ao adicionar termos ao Hamiltonian usando `Add`, qualquer termo não eremitício como `fermionTerm0` é assumido ser emparelhado com o seu conjugado hermitário.</span><span class="sxs-lookup"><span data-stu-id="f026b-177">When adding terms to the Hamiltonian using `Add`, any non-Hermitian term such as `fermionTerm0` is assumed to be paired with its Hermitian conjugate.</span></span>
<span data-ttu-id="f026b-178">Assim, o seguinte corte representa também o mesmo Hamiltonian:</span><span class="sxs-lookup"><span data-stu-id="f026b-178">Thus the following snippet also represents the same Hamiltonian:</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

<span data-ttu-id="f026b-179">Utilizando as regras anti-comutação, alguns `FermionTerm` casos no Hamiltonian correspondem à mesma sequência de operadores fermiónicos, às vezes até um sinal negativo.</span><span class="sxs-lookup"><span data-stu-id="f026b-179">Using the anti-commutation rules, some `FermionTerm` instances in the Hamiltonian actually correspond to the same sequence of fermionic operators, sometimes up to a minus sign.</span></span>
<span data-ttu-id="f026b-180">Por exemplo, considere o $H hamiltoniano=a_0^\punhal a_1^\punhal a_1 a_0 - a_1\dagger a_0^a punhal a_1 a_0 =2a_0^\dagger a_1^\dagger a_1 a_0$, que é uma soma de termos construídos acima.</span><span class="sxs-lookup"><span data-stu-id="f026b-180">For instance, consider the Hamiltonian $H=a_0^\dagger a_1^\dagger a_1 a_0 - a_1^\dagger a_0^\dagger a_1 a_0 =2a_0^\dagger a_1^\dagger a_1 a_0$, which is a sum of terms constructed above.</span></span>
<span data-ttu-id="f026b-181">Pode nem sempre ser claro para o utilizador que estes são termos equivalentes, pelo que podem ser adicionados ao Hamiltonian separadamente.</span><span class="sxs-lookup"><span data-stu-id="f026b-181">It may not always be clear to the user that these are equivalent terms, and so they may be added to the Hamiltonian separately.</span></span>
<span data-ttu-id="f026b-182">Em alternativa, pode-se estar interessado em modificar os termos já existentes no Hamiltoniano.</span><span class="sxs-lookup"><span data-stu-id="f026b-182">Alternatively, one may be interested in modifying already-existing terms in the Hamiltonian.</span></span>
<span data-ttu-id="f026b-183">Nestes casos, podemos combinar termos equivalentes os seguintes.</span><span class="sxs-lookup"><span data-stu-id="f026b-183">In these cases, we may combine equivalent terms as follows.</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We now create two Hermitian fermion terms that are equivalent with respect to
    // anti-commutation and Hermitian symmetry.
    var terms = new[] {
        (new[] { 0, 1, 1, 0 }, 1.0),
        (new[] { 1, 0, 1, 0 }, 1.0) }
    .Select(o => (new HermitianFermionTerm(o.Item1.ToLadderSequence()), o.Item2.ToDoubleCoeff()));

    // Now add `terms` to the Hamiltonian.
    hamiltonian.AddRange(terms);

    // There is only one unique term. `nTerms == 1` is `true`.
    var nTerms = hamiltonian.CountTerms();
```
<span data-ttu-id="f026b-184">Ao combinar coeficientes de termos equivalentes, reduzimos o número total de termos no Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="f026b-184">By combining coefficients of equivalent terms, we reduce the total number of terms in the Hamiltonian.</span></span>
<span data-ttu-id="f026b-185">Mais tarde, isto reduz o número de portões quânticos necessários para simular o Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="f026b-185">Later on, this reduces the number of quantum gates required to simulate the Hamiltonian.</span></span>

### <a name="internal-representation"></a><span data-ttu-id="f026b-186">Representação Interna</span><span class="sxs-lookup"><span data-stu-id="f026b-186">Internal Representation</span></span>

<span data-ttu-id="f026b-187">Um Hamiltonian fermiónico com interações de um e dois corpos é representado em notação de segundo quantificado como</span><span class="sxs-lookup"><span data-stu-id="f026b-187">A fermionic Hamiltonian with one- and two-body interactions is represented in second-quantized notation as</span></span>

<span data-ttu-id="f026b-188">$$ \start{align} H=\sum\_{pq}h\_{pq}a^dagger\_{p}a\_{q}+\frac {2}{1} \sum\_{pqrs}h\_{pqrs}a^\dagger\_{p}a^\aapunhal\_{q}a\_{r}\_a {s}.</span><span class="sxs-lookup"><span data-stu-id="f026b-188">$$ \begin{align} H=\sum\_{pq}h\_{pq}a^\dagger\_{p}a\_{q}+\frac{1}{2}\sum\_{pqrs}h\_{pqrs}a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}.</span></span>
<span data-ttu-id="f026b-189">\end{align} $$</span><span class="sxs-lookup"><span data-stu-id="f026b-189">\end{align} $$</span></span>

<span data-ttu-id="f026b-190">Nesta notação, existem no máximo coeficientes $N^2+N^4$.</span><span class="sxs-lookup"><span data-stu-id="f026b-190">In this notation, there are at most $N^2+N^4$ coefficients.</span></span>
<span data-ttu-id="f026b-191">No entanto, muitos destes coeficientes podem ser recolhidos, uma vez que correspondem ao mesmo operador.</span><span class="sxs-lookup"><span data-stu-id="f026b-191">However, many of these coefficients may be collected as they correspond to the same operator.</span></span>
<span data-ttu-id="f026b-192">Por exemplo, no caso em que $p,q,r,s$ são índices distintos, podemos usar as regras anti-comutação para mostrar que: $$ a^\dagger\_{p}a^a\dagger\_{q}a\_{r}a\_{s} = -a^\dagger\_{q}a^\dagger\_{p}a\_{r }a\_{s} = -a^\dagger\_{p}a^\dagger\_{q}a\_{s}a\_{r} = a^\dagger\_{q}a^\dagger\_{p}a\_{s}a\_{r}.</span><span class="sxs-lookup"><span data-stu-id="f026b-192">For instance, in the case where $p,q,r,s$ are distinct indices, we may use the anti-commutation rules to show that: $$ a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s} = -a^\dagger\_{q}a^\dagger\_{p}a\_{r}a\_{s} = -a^\dagger\_{p}a^\dagger\_{q}a\_{s}a\_{r} = a^\dagger\_{q}a^\dagger\_{p}a\_{s}a\_{r}.</span></span>
$$

<span data-ttu-id="f026b-193">Além disso, como $H$ é hermitiano, todos os operadores fermiónicos não hermitianos, dizem $h\_{pqrs}a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}$, tem um conjugado Hermitiano que também é encontrado em $H$.</span><span class="sxs-lookup"><span data-stu-id="f026b-193">Furthermore, as $H$ is Hermitian, every non-Hermitian fermionic operator, say $h\_{pqrs}a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}$, has a Hermitian conjugate that is also found in $H$.</span></span> <span data-ttu-id="f026b-194">A fim de indexar exclusivamente grupos de termos caracterizados por estas simetrias, definimos uma encomenda canónica nos índices $(i\_1,\cdots,i\_n,j\_1,\cdots,j\_m)$ de qualquer sequência de operadores fermiónico $as\_\_s $n+m$ $a^\dagger\_{i\_1}\cdots a^\\_\_\_\_aada :</span><span class="sxs-lookup"><span data-stu-id="f026b-194">In order to uniquely index groups of terms characterized by these symmetries, we define a canonical ordering on the indices $(i\_1,\cdots,i\_n,j\_1,\cdots,j\_m)$ of any sequence of $n+m$ fermionic operators $a^\dagger\_{i\_1}\cdots a^\dagger\_{i\_n}a\_{j\_1}\cdots a\_{j\_m}$as follows:</span></span>
-   <span data-ttu-id="f026b-195">Todos os operadores de criação $a^\dagger\_{i\_\cdot}$ são colocados antes que todos os operadores de aniquilação $a\_{j\_\cdot}$.</span><span class="sxs-lookup"><span data-stu-id="f026b-195">All creation operators $a^\dagger\_{i\_\cdot}$ are placed before all annihilation operators $a\_{j\_\cdot}$.</span></span>
-   <span data-ttu-id="f026b-196">Todos os índices de operadores de criação estão classificados em ordem ascendente, ou seja, $i\_1< i\_2< \cdots < i\_n$.</span><span class="sxs-lookup"><span data-stu-id="f026b-196">All creation operator indices are sorted in ascending order, that is $i\_1< i\_2< \cdots < i\_n$.</span></span>
-   <span data-ttu-id="f026b-197">Todos os índices de aniquilação do operador estão classificados em ordem descendente, ou seja, $j\_1> j\_2 \cdots > j\_m$.</span><span class="sxs-lookup"><span data-stu-id="f026b-197">All annihilation operator indices are sorted in descending order, that is $j\_1> j\_2 \cdots > j\_m$.</span></span>
-   <span data-ttu-id="f026b-198">O índice mais à esquerda é inferior ou igual ao índice mais à direita, que é $i\_1\le j\_m$.</span><span class="sxs-lookup"><span data-stu-id="f026b-198">The left-most index is less than or equal to the right-most index, that is $i\_1\le j\_m$.</span></span>

<span data-ttu-id="f026b-199">Identifiquemos este conjunto de índices ordenados canonicamente como $$ \begin {align} (i\_1,\cdots,i\_n,j\_1,\cdots,j\_m) \in S\_{n,m}.</span><span class="sxs-lookup"><span data-stu-id="f026b-199">Let us identify this set of canonically ordered indices as $$ \begin{align} (i\_1,\cdots,i\_n,j\_1,\cdots,j\_m) \in S\_{n,m}.</span></span>
<span data-ttu-id="f026b-200">\end{align} $$</span><span class="sxs-lookup"><span data-stu-id="f026b-200">\end{align} $$</span></span>

<span data-ttu-id="f026b-201">Com esta ordem canónica, o Hamiltonian fermiónico pode ser expresso como $$ \start{align} H=\sum\_{(p,q)\em S\_{1,1}}h'\_{pq}\frac{a^\dagger\_{p}a\_{q}+a^\a^\dagger\_{q}a\_{p}}{2}+\soma\_{(p,q,r,s)\em S\_{2,2}}h'\_{pqrs}\frac{a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}+a^\a^\a^\a^\\_a^\a apunhal\_{r}a\_{q}a\_{p}}{2}, \end{align} $$ com integrals de um e dois eletrões adaptados $h'\_{pq}$ e $h'\_{pqrs}$, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="f026b-201">With this canonical ordering, the fermionic Hamiltonian may be expressed as $$ \begin{align} H=\sum\_{(p,q)\in S\_{1,1}}h'\_{pq}\frac{a^\dagger\_{p}a\_{q}+a^\dagger\_{q}a\_{p}}{2}+\sum\_{(p,q,r,s)\in S\_{2,2}}h'\_{pqrs}\frac{a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}+a^\dagger\_{s}a^\dagger\_{r}a\_{q}a\_{p}}{2}, \end{align} $$ with suitably adapted one- and two-electron integrals $h'\_{pq}$ and $h'\_{pqrs}$, respectively.</span></span>

