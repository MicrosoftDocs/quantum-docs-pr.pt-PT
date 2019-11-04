---
title: Segunda quantização | Microsoft Docs
description: Documentos conceituais de segunda quantificação
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.secondquantization
ms.openlocfilehash: b3cc7eb8139d2df6e02de371ccf7a423e58ea76d
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73210403"
---
# <a name="second-quantization"></a>Segunda quantificação

A segunda quantificação analisa o problema da estrutura eletrônica por meio de uma lente diferente.
Em vez de atribuir cada uma das $N _E $ elétrons a um estado específico (ou orbital), a segunda quantificação rastreia cada orbital e armazena se há uma eletrônica presente em cada uma delas e, ao mesmo tempo, garante automaticamente as propriedades de simetria do função de Wave correspondente.
Isso é importante porque permite que os modelos de química da Quantum sejam especificados sem a necessidade de se preocupar com a symmetrizing do estado de entrada (conforme necessário para fermions) e também porque a segunda quantificação permite que esses modelos sejam simulados usando Quantum pequeno nos.

Como um exemplo da segunda quantificação em ação, vamos supor que $ \psi_0\cdots \psi_{N-1} $ seja um conjunto orthonormal de órbitas espaciais.
Esses órbitas são escolhidos para representar o sistema o mais precisamente possível dentro do conjunto de base finito considerado.
Um exemplo comum de tais órbitas são os órbitas atômicos que formam um eigenbasis para o hydrogen atom.
Como elétrons têm dois Estados de rotação, dois elétrons podem ser amontoadodos em cada orbital espacial.
Isso significa que os Estados de base válidos estão no formato $ \psi_{0, \uparrow}, \ldots, \psi_{N-1, \uparrow}, \psi_{0, \downarrow}, \ldots, \psi_{N-1, \downarrow} $, em que $ \uparrow $ e $ \downarrow $ são rótulos que especificam os dois eigenstates do grau de rotação de livre.
Esse índice combinado de $ (j, \sigma) $ para $ \sigma na \{\uparrow, \downarrow\}$ é chamado de spin-orbital porque armazena a espacial, bem como o grau de liberdade.
Na biblioteca de química, as órbitas giradas são armazenadas em uma estrutura de dados `SpinOrbital` e são criadas da seguinte maneira.

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

Isso significa que podemos imaginar a base para a parte de rotação e espacial da função de onda como $ \psi_{0} \cdots \psi_{2N-1} $, em que cada um dos índices agora é uma enumeração de $ (j, \sigma) $.
Uma enumeração possível é $g (j, \sigma) = j + N\sigma ' $.
Outra Enumeração possível é $h (j, \sigma) = 2 * j + \sigma $.
A biblioteca química do Quantum pode usar essas convenções, e as rotações giradas em tal codificação podem ser instanciadas da seguinte maneira.

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

Para sistemas fermionic, o princípio de exclusão de Pauli impede que mais de um horário de uso de um sistema de informações em qualquer orbital de rotação seja exibido ao mesmo tempo.
Isso significa que podemos escrever os dois Estados legais para $ \psi_1 $ como \begin{Equation} \psi_1 \rightarrow \begin{cases} \ket{0}_1 & \Text{If $ \psi_1 $ não está ocupado,} \\\
\ket{1}_1 & \Text{If $ \psi_1 $ está ocupado.} \end{cases} \end{Equation} essa codificação é excelente para computadores Quantum porque significa que podemos armazenar a ocupação eletrônica como um único bit Quantum.

Os Estados de ocupação para as órbitas de rotação de $2N $ podem ser armazenados de forma semelhante em $2N $ qubits.
Por exemplo, se $N = $2, então o estado $ $ \ket{0} \ket{1} \ket{1} \ket{0}, $ $

corresponderia às órbitas de giro $1 $ e $2 $ sendo ocupadas com o restante vazio.
Da mesma forma, o estado $ $ \ket{0} \equiv \ket{0} _{0} \cdots \ket{0}_ {N-1}, $ $

Não tem nenhum elétrons e é conhecido como ' estado de vácuo '.

Um lindo efeito colateral da segunda quantificação é que não precisamos mais controlar explicitamente a antisimetria do estado do Quantum.
Isso ocorre porque, como veremos, a antisimetria do estado representa a si mesmo por meio das regras de commutação dos operadores que criam e destróim a ocupação eletrônica de uma orbital de rotação.

## <a name="fermionic-operators"></a>Operadores Fermionic

Os dois operadores fundamentais que atuam nos vetores de base mais quantificados são conhecidos como operadores de criação e Annihilation.
Esses operadores inserem ou destruim elétrons em um local específico.
Eles são indicados $a ^ \dagger_j $ e $a _J $ respectivamente.

Por exemplo, \begin{align} a ^ \dagger_1 \ket{0}_1 = \ket{1}_1, \quad a ^ \dagger_1 \ket{1}_1 = 0, \quad a_1 \ket{0}_1 = 0, \quad a_1 \ket{1}_1 = \ket{0}_1.
\end{align} Observe que aqui $a ^ \dagger_1 \ket{1}_1 = 0 $ e $a _1 \ket{0}_1 $ yield o vetor zero, não $ \ket{0}_1 $.
Esses operadores, portanto, não são Hermitian nem unitário.
Representamos operadores de criação e Annihilation gerais usando o tipo de <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1>.
Por exemplo, um único operador de criação é representado como a seguir.

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

Usando também esses operadores, podemos expressar $ $ \ket{0} \ket{1} \ket{1} \ket{0} = a ^ \dagger_1 a ^ \dagger_2 \ket{0}^ {\otimes 4}.
$ $ Esta sequência de operadores seria construída na biblioteca de simulação de Hamiltonian usando C# código semelhante ao caso de orbital de rotação única considerado acima acima:
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

Para um sistema de $k $ fermions, na segunda Quantification, a ação do operador de criação $a ^ \dagger_i $ é fornecida por $ $ a ^ \dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k} = (-1) ^ {S_i} \ket{n_1, n_2, \ldots, 1_i , \ldots, n_k}, $ $ e $ $ a ^ \dagger_i \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k} = 0, $ $ Where $S _i = \sum_{j < i} a ^ \dagger_j a_j $ mede o número total de fermions que estão no estado de uma partícula única e que têm um índice $j < i $.

Um terceiro operador também é geralmente usado em segundo representações quantificadas.
Esse operador é conhecido como o operador Number e é definido por \begin{Equation} n_i = a ^ \dagger_i a_i.
\end{Equation} esse operador conta a ocupação de um determinado orbital de rotação, que é dizer \begin{align} n_i \ket{0}_i & = 0 \ nonumber\\\
n_i \ket{1}_i & = \ket{1}_i.
\end{align} semelhante aos exemplos de `FermionTerm` acima, esse operador Number é construído da seguinte maneira.
```csharp
    // Let us use a new method to compactly create a sequence of ladder
    // operators. Note that we have ommitted specifying whether the 
    // operators are raising or lowering. In this case, the first half
    // will be raising operators, and the second half will be lowering 
    // operators.
    var indices = new[] { 1, 1 }.ToLadderSequence();

    // We now construct a `FermionTerm` representing an annihilation operator
    // on the index 1 followed by the creation operator on the index 1.
    var fermionTerm0 = new FermionTerm(indices);
```

Algumas sutilezas surgem ao usar operadores de criação ou Annihilation em sistemas fermionic.
Exigimos que qualquer estado de Quantum válido seja antisimétrico em troca de rótulos.
Isso significa que $ $ a ^ \dagger_2 a ^ \dagger_1 \ket{0} =-a ^ \dagger_1 a ^ \dagger_2 \ket{0}.
$ $ Esses operadores são considerados "antimudo" e, em geral, para qualquer $i, j $ temos esse \begin{align} ^ \dagger_i a ^ \dagger_j =-(1-\delta_{i, j}) um ^ \dagger_j a ^ \dagger_i, \quad a ^ \dagger_i a_j = \delta_{i, j}-a_j a ^ \dagger_i.
\end{align} assim, as duas instâncias de <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> a seguir são consideradas inequivalentes
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

O requisito de que cada um dos operadores de criação anti-mudo significa que usar uma segunda representação quantificada eliminar os desafios enfrentados pela antisimetria do fermions.
Em vez disso, o desafio se resurgirá em nossa definição dos operadores de criação. 

Usando as regras de antimutação, algumas instâncias de `LadderSequence` correspondem à mesma sequência de operadores fermionic, às vezes, até um sinal de menos.
Por exemplo, considere o Hamiltonian $a _0 ^ \dagger a_1 ^ \dagger a_1 a_0 =-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 $.
Isso nos motiva a definir uma ordenação canônica para cada `FermionTerm`.
Qualquer `FermionTerm` é automaticamente colocada em ordem canônica, como a seguir.
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

## <a name="second-quantized-fermionic-hamiltonian"></a>Segundo-quantificar Fermionic Hamiltonian

Talvez seja insurpreendente que o Hamiltonian em [modelos de Quantum para sistemas eletrônicos](xref:microsoft.quantum.chemistry.concepts.quantummodels) possa ser escrito em termos de criação e operadores Annihilation.
Em particular, se $ \psi\_j $ são as órbitas de rotação que formam a base

\begin{Equation} \hat{H} = \sum\_{pq} H\_{pq} a ^ \dagger\_p a\_q + \frac{1}{2}\sum\_{PQRS} H\_{PQRS} a ^ \dagger\_p a ^ \dagger\_q a\_ra\_s + h\_{\textrm NUC}, \label{EQ:} \end{Equation} em que $h\_{\textrm NUC} $ é a energia nuclear (que é uma constante sob a aproximação de-Oppenheimer) e

\begin{align} h\_{pq} & = \int\_{-\infty} ^ \infty \psi ^\*\_p (x\_1) \left (-\frac{\nabla ^ 2}{2} + V (x\_1) \right) \psi\_q (x\_1) \mathrm{d} ^ 3x @no__ t_9_ 1, \end{align}

onde $V (x) $ é o potencial de campo médio e

\begin{align} h\_{PQRS} & = \int\_{-\infty} ^ \infty \int\_{-\infty} ^ \infty\psi\_p ^\*(x\_1) \psi\_q ^\*(x\_2) \left (\frac{1}{| x_1-x_2 |} \ direita) \psi\_r (x\_2) \psi\_s (x\_1) \mathrm{d} ^ 3x\_1 \ mathrm {d} ^ 3x\_2. \ rótulo {EQ: integrals} \end{align}

Os termos $h\_{pq} $ são referenciados como integrantes de um único-único, pois todos esses termos envolvem apenas elétrons únicos e, da mesma forma, $h\_{PQRS} $ são os integrantes de ambos.
Eles são chamados de integrals porque a computação dos valores desses coeficientes requer um integral.
Os termos de uma única pessoa descrevem a energia Kinetic do elétrons individual e suas interações com os campos elétricos do nuclei.
Os dois integrais de ambos os outros, por outro lado, descrevem as interações entre o elétrons.

Uma intuição do que esses termos significam pode ser obtida dos operadores de criação e Annihilation que compõem cada um deles.
Por exemplo, $h _ {pq} a ^ \dagger_p a_q $ descreve a salto de US $s de rotação orbital $q $ para spin orbital $p $.
Da mesma forma, o termo $h _ {PQRS} a ^ \dagger_p a ^ \dagger_q A_R A_S $ (para DISTINCT $p, q, r, s $) descreve dois elétrons em órbitas de rotação $r $ e $s $ dispersão entre si e terminando em órbitas de rotação $p $ e $q $.
Se $r = q $ e $p = s $, então $h _ {PRRP} a ^ \dagger_p a ^ \dagger_r A_R a_p = h_ {PRRP} n_p n_r $ oferece a penalidade de energia associada às duas elétrons que estão perto umas das outras, mas não descreve um processo dinâmico.

Podemos representar tal Hamiltonians usando a classe `FermionHamiltonian`, que é essencialmente uma lista que contém todas as instâncias de `FermionTerm` desejadas.
Como Hamiltonians são Hermitian por definição, indexamos termos usando o tipo mais especializado `HermitianFermionTerm` que também usa simetria de Hermitian ao verificar se os termos são equivalentes.

Vamos criar alguns exemplos ilustrativos.
Considere o Hamiltonian $ \hat{H} = a_0 ^ \dagger a_1 + a_1 ^ \dagger a_0 $.
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
Podemos simplificar essa construção usando o fato de que operadores Hamiltonian são operadores Hermitian.
Ao adicionar termos ao Hamiltonian usando `Add`, qualquer termo não Hermitian como, por exemplo, `fermionTerm0` será considerado emparelhado com seu conjugado Hermitian.
Portanto, o trecho a seguir também representa o mesmo Hamiltonian:
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

Usando as regras de antimutação, algumas instâncias de `FermionTerm` no Hamiltonian realmente correspondem à mesma sequência de operadores fermionic, às vezes, até um sinal de menos.
Por exemplo, considere o Hamiltonian $H = a_0 ^ \dagger a_1 ^ \dagger a_1 a_0-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 = 2a_0 ^ \dagger a_1 ^ \dagger a_1 a_0 $, que é uma soma dos termos construídos acima.
Nem sempre pode ser claro para o usuário que eles são termos equivalentes e, portanto, podem ser adicionados ao Hamiltonian separadamente.
Como alternativa, talvez você esteja interessado em modificar os termos já existentes no Hamiltonian.
Nesses casos, podemos combinar os termos equivalentes da seguinte maneira.
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
Ao combinar coeficientes de termos equivalentes, reduzimos o número total de termos no Hamiltonian.
Posteriormente, isso reduz o número de Gates Quantum necessários para simular o Hamiltonian.

### <a name="internal-representation"></a>Representação interna

Um Hamiltonian fermionic com interações de um e dois corpo é representado em uma notação de segundo quantificação como

$ $ \begin{align} H = \sum\_{pq} H\_{pq} a ^ \dagger\_{p} a\_{q} + \frac{1}{2}\sum\_{PQRS} H\_{PQRS} a ^ \dagger\_{p} a ^ \dagger\_{q} a @no__ t_10_ {r} um\_{s}.
\end{align} $ $

Nessa notação, há no máximo $N ^ 2 + N ^ 4 $ coeficientes.
No entanto, muitos desses coeficientes podem ser coletados, pois correspondem ao mesmo operador.
Por exemplo, no caso em que $p, q, r, s $ são índices distintos, podemos usar as regras de antimutação para mostrar que: $ $ a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{r} a\_{s} =-a ^ \dagger\_{q} a ^ \dagger\_{ p} a\_{r} a\_{s} =-a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{s} a\_{r} = a ^ \dagger\_{q} a ^ \dagger\_{p} a\_{s} a\_{r}.
$$

Além disso, como $H $ é Hermitian, todos os operadores de fermionic não Hermitian, digamos $h\_{PQRS} um ^ \dagger\_{p} a ^ \dagger\_{q} a\_{r} a\_{s} $, tem um conjugado Hermitian que também é encontrado em $H $. Para indexar exclusivamente os grupos de termos caracterizados por esses Symmetries, definimos uma ordenação canônica nos índices $ (i\_1, \cdots, i\_n, j\_1, \cdots, j\_m) $ de qualquer sequência de operadores $n + m $ fermionic $a ^ \dagger\_{i\_1} \cdots ^ \dagger\_{i\_n} um\_{j\_1} \cdots a\_{j\_m} $as segue:
-   Todos os operadores de criação $a ^ \dagger\_{i\_\cdot} $ são colocados antes de todos os operadores de Annihilation $a\_{j\_\cdot} $.
-   Todos os índices do operador de criação são classificados em ordem crescente, $i\_1 < i\_2 < \cdots < eu\_n $.
-   Todos os índices do operador Annihilation são classificados em ordem decrescente, $j\_1 > j\_2 \cdots > j\_m $.
-   O índice mais à esquerda é menor ou igual ao índice mais à direita, $i\_1 \ Le j\_m $.

Vamos identificar esse conjunto de índices ordenados de forma canônica como $ $ \begin{align} (i\_1, \cdots, i\_n, j\_1, \cdots, j\_m) na S\_{n, m}.
\end{align} $ $

Com essa ordenação canônica, o fermionic Hamiltonian pode ser expresso como $ $ \begin{align} H = \sum\_{(p, q) na S\_{1,1}} H '\_{pq} \frac{a ^ \dagger\_{p} a\_{q} + a ^ \dagger\_{q} a\_{ p}}{2}+ \sum\_{(p, q, r, s) na S\_{2,2}} h '\_{PQRS} \frac{a ^ \dagger\_{p} a ^ \dagger\_{q} a\_{r} a\_{s} + a ^ \dagger\_{s} a ^ \ Dagger\_{r} a\_{q} a\_{p}}{2}, \end{align} $ $ com adaptado adequadamente um-e dois inteiros de $h '\_{pq} $ e $h '\_{PQRS} $, respectivamente.

