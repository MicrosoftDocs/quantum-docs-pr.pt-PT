---
title: Teoria hartree-Fock
description: Conheça a teoria Hartree-Fock, uma forma simples de construir o estado inicial para sistemas quânticos.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.hartreefock
no-loc:
- Q#
- $$v
ms.openlocfilehash: 53d6e4342e5b58886528e89871591e57d8e70c82
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835354"
---
# <a name="hartreefock-theory"></a>Teoria hartree-Fock

Talvez a quantidade mais importante na simulação da química quântica seja o estado do solo, que é o eigenvector energético mínimo da matriz hamiltoniana.
Isto porque para a maioria das moléculas em quantidades de temperatura ambiente, tais como taxas de reação, são dominadas por diferenças energéticas livres entre estados quânticos que descrevem o início e o fim de um passo numa via de reação e à temperatura ambiente tais estados intermédios são geralmente estados terrestres.
Embora o estado do solo seja tipicamente muito difícil de aprender (mesmo com um computador quântico) porque é uma distribuição sobre um número exponencialmente grande de configurações.
Quantidades como a energia do estado do solo podem ser aprendidas.
Por exemplo, se $\ket{\psi}$ é qualquer estado quântico puro então \start{equação} E = \bra{ \\ \hat{H} \ket{\psi} \end{equação} dá a energia média que o sistema tem nesse estado.
O estado terrestre é então o estado que dá o menor valor. Como resultado, escolher um estado o mais próximo possível do verdadeiro estado terrestre é vital para estimar a energia diretamente (como é feito em eigensolvers variacionais) ou através da estimativa de fase.

A teoria hartree-Fock dá uma maneira simples de construir o estado inicial para sistemas quânticos. Produz uma única aproximação determinante de Slater ao estado terrestre de um sistema quântico. Para tal, encontra uma rotação dentro do espaço Fock que minimiza a energia do estado do solo. Em particular, para um sistema de eletrões $N$ o método executa a rotação \start{equação} \prod_{j=0}^{N-1} a^\dagger_j \ket {0} \mapsto \prod_{j=0}^{N-1} e^1} e^\\ket \ket \mapsto \prod_{j=0}^{N-1} e^1} e^\\ket \ket \mapsto \prod_{j=0}^{N-1} e^-1} {u} a^\dagger_j e^{-u} \ket {0} \defeq\prod_{j=0}^{N-1} \widetilde{a}^\dagger_j \ket {0} , \end{equation} com um anti-hermitiano (i.e. $u= -u^\dagger$) matriz $u = \sum_{pq} u_{pq} a^\dagger_p a_q$. Note-se que a matriz $u$ representa as rotações orbitais e $\widetilde{a}^\\dagger_j$ e $\widetilde{a}_j$ representam operadores de criação e aniquilação para eletrões que ocupam os orbitais de rotação molecular Hartree-Fock.


A matriz $u$ é então otimizada para minimizar a energia esperada $\bra {0} \prod_{j=0}^{N-1} \widetilde{a} \_ j H \prod \_ {k=0}^{N-1} \widetilde{a}\\dagger_k\ket {0} $. Embora tais problemas de otimização possam ser genericamente difíceis, na prática o algoritmo Hartree-Fock tende a convergir rapidamente para uma solução quase ideal para o problema de otimização, especialmente para moléculas de concha fechada nas geometrias do equilíbrio. Podemos especificar estes estados como um exemplo do `FermionWavefunction` objeto. Por exemplo, o estado $a^\dagger_ {1} a^\dagger_ {2} a^\dagger_ {6} \ket $ é {0} instantâneo na biblioteca de química da seguinte forma.
```csharp
// Create a list of integer indices of the creation operators
var indices = new[] { 1, 2, 6 };

// Convert the list of indices to a `FermionWavefunction` object.
// In this case, the indices are integers, so we use the `int`
// type specialization.
var wavefunction = new FermionWavefunction<int>(indices);
```
Também é possível indexar funções de onda com `SpinOrbital` índices, e depois converter estes índices em inteiros da seguinte forma.
```csharp
// Create a list of spin orbital indices of the creation operators
var indices = new[] { (0, Spin.d), (1,Spin.u), (3, Spin.u) };

// Convert the list of indices to a `FermionWavefunction` object.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(indices.ToSpinOrbitals());

// Convert a wavefunction indexed by spin orbitals to
// one indexed by integers
var wavefunctionInt = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

A característica mais marcante sobre a teoria hartree-Fock é que produz um estado quântico que não tem qualquer emaranhamento entre os eletrões.
Isto significa que muitas vezes fornece uma descrição qualitativa adequada das propriedades dos sistemas moleculares. 

O estado de Hartree-Fock também pode ser reconstruído da `FermionHamiltonian`  seguinte forma.
```csharp
// We initialize a fermion Hamiltonian.
var fermionHamiltonian = new FermionHamiltonian();

// Create a Hartree-Fock state from the Hamiltonian 
// with, say, `4` occupied spin orbitals.
var wavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons: 4);
```

No entanto, obter resultados precisos, especialmente para sistemas fortemente correlacionados, requer estados quânticos que vão além da teoria hartree-Fock.
