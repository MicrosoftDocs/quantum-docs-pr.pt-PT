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
# <a name="correlated-wavefunctions"></a>Funções de onda correlacionadas

Para muitos sistemas, particularmente aqueles perto da geometria do equilíbrio, a teoria [de Hartree-Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) fornece uma descrição qualitativa das propriedades moleculares através de um estado de referência único determinante. No entanto, para se conseguir uma precisão quantitativa, é necessário também considerar os efeitos da correlação. 

Neste contexto, é importante dinpidar entre correlações dinâmicas e não dinâmicas.
As correlações dinâmicas surgem da tendência dos eletrões para se manterem separados, como por exemplo devido à repulsão interelectrónica. Este efeito pode ser modelado considerando as excitações de eletrões fora do estado de referência. As correlações não dinâmicas surgem quando a função de onda é dominada por duas ou mais configurações à ordem zero, mesmo para obter apenas uma descrição qualitativa do sistema.
Isto requer uma sobreposição de determinantes e é um exemplo de uma função de onda multi-referência.

A biblioteca de química fornece uma maneira de especificar uma função de onda de ordem zero para o problema de multireferência como uma superposição de determinantes. Esta abordagem, a que chamamos funções de ondas multi-referência escassas, é eficaz quando apenas alguns componentes são suficientes para especificar a superposição. A biblioteca também fornece um método para incluir correlações dinâmicas em cima de uma referência determinante única através do aglomerado unitário generalizado ansatz. Além disso, também constrói circuitos quânticos que geram estes estados num computador quântico. Estes estados podem ser especificados no esquema de [Broombridge,](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)e também fornecemos a funcionalidade para especificar manualmente estes estados através da biblioteca de química.

## <a name="sparse-multi-reference-wavefunction"></a>Função de ondas de várias referências escassas
Um estado de referência multi-referência $\ket {\psi_{\rm {MCSCF}}}$pode ser especificado explicitamente como uma combinação linear de determininantes slater de $N$-eletrões.
\begin{align} \ket{\psi_{\rm {MCSCF}} \propto \sum_{i_1 < i_2 < \cdots < i_N} \lambda_{i_1,i_2,\cdots,i_N} a^\dagger_{i_1}\\dagger_\lambda_{i_2}\cdots a^{dagger_{i_N}}\{0}ket
\end{align} Por exemplo, o estado $\propto (0.1 a^\dagger_1a\\dagger_2a^\dagger_6 - 0,2 a^\dagger_2a^\dagger_1a^\dagger_5)\ket{0}$ pode ser especificado na biblioteca de química da seguinte forma.
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
Esta representação explícita dos componentes de superposição é eficaz quando apenas alguns componentes precisam de ser especificados. Deve-se evitar utilizar esta representação quando muitos componentes são necessários para capturar com precisão o estado desejado. A razão para isso é o custo do portão do circuito quântico que prepara este estado num computador quântico, que escala pelo menos linearmente com o número de componentes de superposição, e no máximo quadraticamente com a norma das amplitudes de superposição.

## <a name="unitary-coupled-cluster-wavefunction"></a>Função unitária de onda de aglomerado acopd
Também é possível especificar uma função unitária de onda de cluster $\ket{\psi_{\rm {UCC}}}$$ usando a biblioteca de químicos. Nesta situação, temos um estado de referência único, digamos, $\ket{\psi_{\rm{SCF}}}$. Os componentes da função de onda de aglomerado unitário são então especificados implicitamente através de um operador unitário que atua num estado de referência.
Este operador unitário é comumente escrito como $e^{T-T^\dagger}$, onde $T-T^\dagger$ é o operador de cluster anti-eremititiano. Assim\ comece {align} \ket{\psi_{\rm {UCC}} = e^T-T^\dagger}\ket{\psi_{\rm{SCF}}.
\fim{align}

Também é comum dividir o operador do cluster $T = T_1 + T_2 + \cdots$ em partes, onde cada parte $T_j$ contém termos $j corpo de $. Na teoria do cluster acoplado generalizado, o operador de cluster de um corpo (singles) é da forma \begin{align} T_1 = \sum_{pq}t^{p}_{q} a^\dagger_p a_q, \end{align}

e o operador de cluster de duas carroças (duplos) é da forma \begin{align} T_2 = \sum_{pqrs}t^{pq}{{rs} a^\dagger_p a^\dagger_q a_r a_s.
\fim{align}

Os termos de ordem superior (triplos, quadruplos, etc.) são possíveis, mas não são atualmente suportados pela biblioteca de química.

Por exemplo, deixe $\ket{\psi_{\rm{SCF}}} = a^dagger_1 a^\\dagger_2\ket{0}$, e deixe $T= 0,123 a^\dagger_0 a_1 + 0,456 a^\dagger_0a^\dagger_3 a_1 a_2 - 0,789 a^\dagger_3a^\dagger_2 a_1 a_0$. Então este estado é instantaneamente instantâneo na biblioteca de química da seguinte forma.
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

A convervação de giro pode ser explicitada especificando `SpinOrbital` índices em vez de índices inteiros. Por exemplo, deixe $\ket{\psi_{\rm{SCF}}} = a^dagger_{1,\uparrow} a^\dagger_{2, \downarrow}\ket{0}$, e deixe $T= 0,123 a^\dagger_{0, \uparrow} a_{1, \uparrow} + 0,456 a^\dagger_{0, \uparrow} a^\dagger_{3, \downarrow} a_{1, \uparrow} a_{2, \downarrow} - 0,789 a^\dagger_{3,\uparrow} a^\dagger_{2,uparrow} a_{1,\uparrow a_{0, \up Então este estado é instantaneamente instantâneo na biblioteca de química da seguinte forma.
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

Também fornecemos uma função de conveniência que enumera todos os operadores de clusters que aniquilam apenas os orbitais de centrifugação ocupados e excitam apenas os orbitais de spin-orbitais desocupados.
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
