---
title: Teoria de Hartree-Fock
description: Aprenda sobre a teoria hartree-Fock, uma forma simples de construir o estado inicial para sistemas quânticos.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.hartreefock
ms.openlocfilehash: 6fa63cbe13fe98565ffb42b56f3ade86720cedb3
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904456"
---
# <a name="hartreefock-theory"></a>Teoria hartree-fock

Talvez a quantidade mais importante na simulação da química quântica seja o estado do solo, que é o eigenvector de energia mínima da matriz hamiltoniana.
Isto porque para a maioria das moléculas em quantidades de temperatura ambiente, tais como taxas de reação são dominadas por diferenças de energia livres entre estados quânticos que descrevem o início e o fim de um passo numa via de reação e à temperatura ambiente tão intermediário estado são geralmente estados de terra.
Embora o estado do solo seja tipicamente muito difícil de aprender (mesmo com um computador quântico) porque é uma distribuição sobre um número exponencialmente grande de configurações.
Quantidades como a energia do estado terrestre podem ser aprendidas.
Por exemplo, se $\ket{\psi}$ for qualquer estado quântico puro então \begin{equation} E = \bra{ \psi } \hat{H} \ket{\psi} \end{equation} dá a energia média que o sistema tem nesse estado.
O estado de terra então é o estado que dá o menor valor a este. Como resultado, escolher um estado o mais próximo possível do verdadeiro estado terrestre é vital para estimar a energia diretamente (como é feito em eigensolvers variacionais) ou através da estimativa de fase.

A teoria de Hartree-Fock dá uma forma simples de construir o estado inicial para sistemas quânticos. Produz uma única aproximação determinante de Slater ao estado terrestre de um sistema quântico. Para tal, encontra uma rotação dentro do espaço Fock que minimiza a energia do estado terrestre. Em particular, para um sistema de eletrões $N$ o método executa a rotação \start{equation} \prod_{j=0}^{N-1} a^\dagger_j \ket{0} \mapsto \prod_{j=0}^{N-1} e^{{u} a^\dagger_j e^{-u} \ket{0}\defeq\prod_{j=0}^{N-1} \widetilde{a}^\dagger_j \ket{0}, \end{equation} com um anti-Hermitiano (i.e. $u= -u^\dagger$) matriz $u = \sum_{pq} u_{pq} a^\dagger_p a_q$. Note-se que a matriz $u$ representa as rotações orbitais e $\widetilde{a}^\dagger_j$ e $\widetilde{a}_j$ representam os operadores de criação e aniquilação de eletrões que ocupam os orbitais de centrifugação molecular Hartree-Fock.


A matriz $u$ é então otimizada para minimizar a energia esperada $\bra{0} \prod_{j=0}^N-1} \widetilde{a}\_j H \prod\_{k=0}^{N-1} \widetilde{a}^\dagger_k\ket{0}$. Embora tais problemas de otimização possam ser genericamente difíceis, na prática o algoritmo Hartree-Fock tende a convergir rapidamente para uma solução quase ideal para o problema de otimização, especialmente para moléculas de casca fechada nas geometrias do equilíbrio. Podemos especificar estes Estados como um exemplo do `FermionWavefunction` objeto. Por exemplo, o estado $a^\dagger_{1}a^\dagger_{2}a^\dagger_{6}{0}$ é instantaneamente instantâneo na biblioteca de química da seguinte forma.
```csharp
// Create a list of integer indices of the creation operators
var indices = new[] { 1, 2, 6 };

// Convert the list of indices to a `FermionWavefunction` object.
// In this case, the indices are integers, so we use the `int`
// type specialization.
var wavefunction = new FermionWavefunction<int>(indices);
```
Também é possível indexar as funções de onda com índices `SpinOrbital`, e depois converter estes índices em inteiros da seguinte forma.
```csharp
// Create a list of spin orbital indices of the creation operators
var indices = new[] { (0, Spin.d), (1,Spin.u), (3, Spin.u) };

// Convert the list of indices to a `FermionWavefunction` object.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(indices.ToSpinOrbitals());

// Convert a wavefunction indexed by spin orbitals to
// one indexed by integers
var wavefunctionInt = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

A característica mais marcante sobre a teoria de Hartree-Fock é que produz um estado quântico que não tem nenhum emaranhado entre os eletrões.
Isto significa que muitas vezes fornece uma descrição qualitativa adequada das propriedades dos sistemas moleculares. 

O estado de Hartree-Fock também pode ser reconstruído a partir de um `FermionHamiltonian` seguinte.
```csharp
// We initialize a fermion Hamiltonian.
var fermionHamiltonian = new FermionHamiltonian();

// Create a Hartree-Fock state from the Hamiltonian 
// with, say, `4` occupied spin orbitals.
var wavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons: 4);
```

No entanto, a obtenção de resultados precisos, especialmente para sistemas fortemente correlacionados, requer estados quânticos que vão além da teoria de Hartree-Fock.
