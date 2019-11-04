---
title: Wavefunctions correlacionado | Microsoft Docs
description: Documentos conceituais do Quantum Dynamics
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.multireference
ms.openlocfilehash: 0b14f373d31c5b63e313e07810daf62d9195b1d3
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184037"
---
# <a name="correlated-wavefunctions"></a>Wavefunctions correlacionado

Para muitos sistemas, especialmente aqueles próximos à geometria equilíbrio, a teoria de [Hartree – Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) fornece uma descrição qualitativa das propriedades de molecular por meio de um estado de referência de determinante único. No entanto, para obter uma precisão quantitativa, também é necessário considerar os efeitos de correlação. 

Nesse contexto, é importante dinstinguish entre correlações dinâmicas e não dinâmicas.
As correlações dinâmicas surgem da tendência de elétrons para ficarem separadas, como devido à repulsão intereletrônica. Esse efeito pode ser modeladas considerando excitations de elétrons do estado de referência. As correlações não dinâmicas surgem quando o wavefunction é dominado por duas ou mais configurações em ordem inicial, mesmo para obter apenas uma descrição qualitativa do sistema.
Isso exige uma superposição dos determinantes e é um exemplo de wavefunction de multireferência.

A biblioteca química fornece uma maneira de especificar um wavefunction de ordem inicial para o problema de multireferência como uma superposição de determinantes. Essa abordagem, que chamamos de wavefunctions de várias referências esparsas, é eficaz quando apenas alguns componentes são suficientes para especificar a superposição. A biblioteca também fornece um método para incluir correlações dinâmicas sobre uma referência de determinante único por meio do ansatz de cluster acoplado unitário generalizado. Além disso, ele também constrói circuitos Quantum que geram esses Estados em um computador Quantum. Esses Estados podem ser especificados no [esquema Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)e também fornecemos a funcionalidade para especificar manualmente esses Estados por meio da biblioteca química.

## <a name="sparse-multi-reference-wavefunction"></a>Wavefunction de várias referências esparsas
Um estado de referência múltipla $ \ket{\psi_{\rm {MCSCF}}} $ pode ser especificado explicitamente como uma combinação linear de $N $-$-Slater.
\begin{align} \ket{\psi_{\rm {MCSCF}}} \propto \sum_{i_1 < i_2 < \cdots < i_N} \lambda_{i_1, i_2, \cdots, i_N} a ^ \dagger_{i_1}a ^ \dagger_{i_2}\cdots a ^ \dagger_{i_N}\ket{0}.
\end{align} por exemplo, o estado $ \propto (0,1 a ^ \dagger_1a ^ \dagger_2a ^ \dagger_6-0,2 a ^ \dagger_2a ^ \dagger_1a ^ \dagger_5) \ket{0}$ pode ser especificado na biblioteca química da seguinte maneira.
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
Essa representação explícita dos componentes de superposição é eficaz quando apenas alguns componentes precisam ser especificados. É necessário evitar o uso dessa representação quando muitos componentes são necessários para capturar com precisão o estado desejado. A razão para isso é o custo de portão do circuito Quantum que prepara esse estado em um computador Quantum, que pode ser dimensionado pelo menos linearmente com o número de componentes de superposição e, no máximo, de forma quadrática com a norma de amplitude de superposição.

## <a name="unitary-coupled-cluster-wavefunction"></a>Wavefunction de cluster acoplado unitário
Também é possível especificar um wavefunction de cluster acoplado unitário $ \ket{\psi_{\rm {UCC}}} $ usando a biblioteca chemistery. Nessa situação, temos um estado de referência de determinante único, digamos, $ \ket{\psi_{\rm{SCF}}} $. Os componentes dos wavefunction de cluster acoplados unitários são então especificados implicitamente por meio de um operador unitário agindo em um estado de referência.
Esse operador unitário normalmente é escrito como $e ^ {T-T ^ \dagger} $, em que $T-T ^ \dagger $ é o operador de cluster Hermitian. Portanto, \begin{align} \ket{\psi_{\rm {UCC}} = e ^ {T-T ^ \dagger}\ket{\psi_{\rm{SCF}}}.
\end{align}

Também é comum dividir o operador de cluster $T = T_1 + T_2 + \cdots $ em partes, em que cada parte $T _J $ contém $j termos de corpo. Na teoria de clusters agrupadas generalizadas, o operador de cluster de um corpo (singles) está no formato \begin{align} T_1 = \sum_{pq}t ^ {p} _ {q} a ^ \dagger_p a_q, \end{align}

e o operador de cluster de dois corpo (duplo) está no formato \begin{align} T_2 = \sum_{PQRS}t ^ {pq} _ {RS} a ^ \dagger_p \dagger_q A_R A_S.
\end{align}

Os termos de ordem superior (corridas, quádruplos, etc.) são possíveis, mas não têm suporte da biblioteca química no momento.

Por exemplo, permita que $ \ket{\psi_{\rm{SCF}}} = a ^ \dagger_1 a ^ \dagger_2\ket{0}$ e permita $T = 0,123 a ^ \dagger_0 a_1 + 0,456 a ^ \dagger_0a ^ \dagger_3 a_1 a_2-0,789 a ^ \dagger_3a ^ \dagger_2 a_1 a_0 $. Em seguida, esse estado é instanciado na biblioteca química da seguinte maneira.
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

O spin Convervation pode se tornar explícito, especificando `SpinOrbital` índices em vez de índices inteiros. Por exemplo, deixe $ \ket{\psi_{\rm{SCF}}} = a ^ \dagger_{1, \uparrow} a ^ \dagger_{2, \downarrow}\ket{0}$ e permita $T = 0,123 a ^ \dagger_{0, \uparrow} a_ {1, \uparrow} + 0,456 a ^ \dagger_{0, \uparrow} a ^ \dagger_{3, \downarrow} a_ {1, \uparrow} a_ {2, \ seta}-0,789 a ^ \dagger_{3, \uparrow} a ^ \dagger_{2, \uparrow} a_ {1, \uparrow} a_ {0, \uparrow} $ ser spin convserving. Em seguida, esse estado é instanciado na biblioteca química da seguinte maneira.
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

Também fornecemos uma função de conveniência que enumera em todos os operadores de clusters de rotação, que Annihilate ocupam apenas giro girado e excite apenas para girar giros desocupadas.
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