---
title: Segunda Quantificação
description: Conheça a segunda abordagem quantização à modelação de estruturas electrónicas na programação quântica.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.secondquantization
ms.openlocfilehash: e17c97767b05395af46a82c4035337406c7e3218
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907346"
---
# <a name="second-quantization"></a>Segunda Quantificação

A segunda quantificação analisa o problema da estrutura electrónica através de uma lente diferente.
Em vez de atribuir cada um dos eletrões $N_e$ a um estado específico (ou orbital), a segunda quantificação rastreia cada orbital e armazena se existe um eletrão presente em cada um deles e, ao mesmo tempo, assegura automaticamente propriedades de simetria do função de onda correspondente.
Isto é importante porque permite especificar os modelos de química quântica sem ter que se preocupar com a anti-simmetrização do estado de entrada (como é necessário para fermiões) e também porque a segunda quantificação permite que tais modelos sejam simulados usando um pequeno quantum computadores.

Como exemplo de segunda quantificação em ação, vamos assumir que $\psi_0\cdots \psi_{N-1}$ são um conjunto ortonormal de orbitais espaciais.
Estes orbitais são escolhidos para representar o sistema o mais precisamente possível dentro do conjunto de base finita considerado.
Um exemplo comum desses orbitais são os orbitais atómicos que formam uma base eigenpara o átomo de hidrogénio.
Como os eletrões têm dois estados de rotação, dois eletrões podem ser amontoados em cada um desses orbitais espaciais.
Ou seja, os estados de base válidas são do formulário $\psi_{0,\uparrow},\ldots,\psi_{N-1,\uparrow}, \psi_{{0,\downarrow},\ldots,\psi_{N-1,\downarrow}$ onde $\uparrow$ e $downarrow$ são rótulos que especificam os dois eigenstates do grau de centrifugação liberdade.
Este índice combinado de $(j,\sigma)$ para $\sigma \in \{\uparrow,\downarrow\}$ é chamado de spin-orbital porque armazena tanto o espaço como o grau de rotação da liberdade.
Na biblioteca de química, os orbitais de rotação são armazenados numa estrutura de dados `SpinOrbital`, e são criados da seguinte forma.

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

Isto significa que podemos pensar formalmente na base tanto para a parte giratória como para a parte espacial da função de onda como $\psi_{0} \cdots \psi_ {2N-1}$ onde cada um dos índices agora é uma enumeração de um $(j,\sigma)$.
Uma possível enumeração é $g (j,\sigma) = j+N\sigma'$.
Outra possível enumeração é $h (j,\sigma) = 2*j + \sigma$.
A biblioteca de química quântica pode usar estas convenções, e os orbitais de rotação em tal codificação podem ser instantâneos da seguinte forma.

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

Para os sistemas fermiónicos, o princípio da exclusão de Pauli impede que mais do que um eletrão esteja presente em qualquer rotação-orbital ao mesmo tempo.
Isto significa que podemos escrever os dois estados legais por $\psi_1$ como \{equação} \psi_1 \seta direita \start{cases} \ket{0}_1 & \text{if $\psi_1$ is not ocupado,} \\\
\ket{1}_1 & \text{if $\psi_1$ is ocupado.} \end{cases} \end{equation} Esta codificação é ótima para computadores quânticos porque significa que podemos armazenar a ocupação electrónica como uma única bit quântica.

A ocupação indica que os orbitais de rotação de $2N$ podem igualmente ser armazenados em qubits de $2N$.
Como exemplo, se $N=2$ então o Estado $${0} \ket{1} \ket{1} \ket{0}, $$

corresponderia aos orbitais de giro $1$ e $2$ sendo ocupados com o restante vazio.
Da mesma forma, o estado $$ \ket{0} \equiv \ket{0} _{0} \cdots \ket{0}_ {N-1}, $$

não tem eletrões e é conhecido como o "estado de vácuo".

Um belo efeito colateral da segunda quantificação é que já não temos de acompanhar explicitamente a anti-simetria do estado quântico.
Isto porque, como veremos, a anti-simetria do Estado representa-se, em vez disso, através das regras anti-comutação dos operadores que criam e destroem as ocupações electrónicas de um orbital de rotação.

## <a name="fermionic-operators"></a>Operadores fermiónicos

Os dois operadores fundamentais que atuam sobre os vetores de base segundo quantificado são conhecidos como operadores de criação e aniquilação.
Estes operadores inserem ou destroem eletrões num determinado local.
Estes são denotados $a^\dagger_j$ e $a_j$ respectivamente.

Por exemplo, \start{align} a^\dagger_1 \ket{0}_1 = \ket{1}_1,quad a^\dagger_1 \ket{1}_1 = 0,\quad a_1 \ket{0}_1 = 0,\quad a_1 \ket{1}_1 = \ket{0}_1.
\end{align} Note que aqui $a^\dagger_1 \ket{1}_1=0$ e $a_1 \ket{0}_1$ rendimento do vetor zero e não $\ket{0}_1$.
Por conseguinte, estes operadores não são hermitianos nem unitários.
Representamos operadores gerais de criação e aniquilação utilizando o tipo <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1>.
Por exemplo, um único operador de criação é representado como segue.

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

Também usando tais operadores podemos expressar $$ \ket{0} \ket{1} \ket{1} \ket{0} = a^\dagger_1 a^\dagger_2 \ket{0}{{\otimes 4}.
$$ Esta sequência de operadores seria construída dentro C# da biblioteca de simulação hamiltoniana usando código semelhante ao caso orbital de rotação única acima considerado:
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

Para um sistema de $k$ Fermions, em segunda quantificação a ação do operador de criação $a^\dagger_i$ é dada por $$ a^\dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k } = (-1)^{S_i} \ket{n_1, n_2, \ldots, 1_i , \ldots, n_k}, $$ e $$ a^\dagger_i \ket{n_1, n_2, \ldots, \ldots 1_i, \ldots, n_k } = 0, $$ onde $S_i = \sum_{j<i} a^\dagger_j a_j$ mede o número total de Fermions que estão no estado de uma única partícula e que têm um índice $j < i$.

Um terceiro operador também é frequentemente utilizado em segundas representações quantificadas.
Este operador é conhecido como o operador de números e é definido por \start{equation} n_i = a^\dagger_i a_i.
\end{equation} Este operador conta a ocupação de um dado orbital de centrifugação, ou seja, \start{align} n_i{0}_i & 0\nonumber\\\
n_i \ket{1}_i &= \ket{1}_i.
\end{align} Semelhante aos exemplos acima `FermionTerm`, este operador de número é construído da seguinte forma.
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

Uma subtileza surge quando se utilizam operadores de criação ou aniquilação em sistemas fermiónicos.
Exigimos que qualquer estado quântico válido seja antissimétrico sob troca de rótulos.
Isto significa que $$ a^\dagger_2 a^\dagger_1 \ket{0} = -a^\dagger_1 a^\dagger_2 \ket{0}.
$$ Estes operadores são ditos 'anti-comutação' e, em geral, para qualquer $i, j$ temos que \begin{align} a^\dagger_i a^\dagger_j = -(1-\delta_{i,j})a^\dagger_j a^\dagger_i,quad a^\dagger_i a_j =\delta_{i,j} - a_j a^\dagger_i.
\end{align} Assim, as duas seguintes <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> casos são consideradas inequivalentes
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

A exigência de que cada um dos operadores de criação anti-deslocação significa que a utilização de uma segunda representação quantificada obvia os desafios enfrentados pela anti-simetria dos Fermions.
Em vez disso, o desafio ressurge na nossa definição de operadores de criação. 

Utilizando as regras anti-comutação, algumas `LadderSequence` casos correspondem à mesma sequência de operadores fermiónicos, às vezes até um sinal negativo.
Por exemplo, considere o $a_0^\dagger hamiltonian a_1^\punhal a_1 a_0 = - a_1\dagger a_0^\dagger a_0^\dagger a_1 a_0$.
Isto motiva-nos a definir uma encomenda canónica para cada `FermionTerm`.
Qualquer `FermionTerm` é automaticamente colocada em ordem canónica da seguinte forma.
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

## <a name="second-quantized-fermionic-hamiltonian"></a>Segundo-quantificado Fermionic Hamiltonian

Talvez não seja de estranhar que o Hamiltonian em [Modelos Quânticos de Sistemas Eletrónicos](xref:microsoft.quantum.chemistry.concepts.quantummodels) possa ser escrito em termos de criação e aniquilação dos operadores.
Em particular, se $\psi\_j$ são os orbitais de rotação que formam a base então

\begin{equation} \hat{H} = \soma\_{pq} h\_{pq}a^\dagger\_p a\_q + \frac{1}{2}\sum\_{pqrs} h\_{pqrs}a^\dagger\_p a^\dagger\_q a\_ra\_s +h\_{\textrm nuc},\label{eq:totalHam} \end{equation} onde $h\_{\textrm nuc}$ é a energia nuclear (que é uma constante sob a aproximação born-oppenheimer) e

\begin{align} h\_{pq} &= \int\_{-\infty}\infty\infty \psi^ \_\*p(x\_1) \left(-\frac{\nabla^2}{2} +V(x\_1)\direita) \psi\_q(x\_1)\mathrm{d}^3x\_1, \end align{}

onde $V(x)$ é o potencial médio-campo, e

\begin{align} h\_{pqrs} &= \int\_{-\infty}^\int\_{-\infty}\infty\infty\infty\psi\_p^\*(x\_1)\psi\_q^\*(x\_2) \left(\frac{1}{/x_1-x_2} \right)\psi\_r(x\_2)\psi\_s(x\_1)\mathrm{d}^3x\_1\mathrm{d}^3x\_2.\label{eq :integrals} \end{align}

Os termos $h\_{pq}$ são referidos como integrales de um eletrão, porque todos esses termos envolvem apenas eletrões simples e $h\_{pqrs}$ são os integrais de dois eletrões.
São chamados integrais porque a computação dos valores destes coeficientes requer uma integral.
Os termos de um eletrão descrevem a energia cinética dos eletrões individuais e as suas interações com os campos elétricos dos núcleos.
Os dois eletrões integrais, por outro lado, descrevem as interações entre os eletrões.

Uma intuição para o que estes termos significam pode ser recolhida a partir da criação e da aniquilação dos operadores que compõem cada um deles.
Por exemplo, $h_{pq}a^\dagger_p a_q$ descreve o eletrão pulando de $q orbital de rotação para girar orbital $p$.
Da mesma forma, o termo $h_{pqrs} a^\dagger_p a^\dagger_q a_r a_s$ (para $p distintos, q,r,s$) descreve dois eletrões em orbitais de rotação $r$ e $s$ espalhando-se uns dos outros e acabando em órbitas de rotação $p$ e $q$.
Se $r=q$ e $p=s$ então $h_{prrp} a^\dagger_p a^\dagger_r a_p a_r = h_{prrp} n_p n_r$ dá a penalidade energética associada aos dois eletrões que estão perto um do outro, mas não descreve um processo dinâmico.

Podemos representar esses Hamiltonians usando a classe `FermionHamiltonian`, que é essencialmente uma lista contendo todos os casos `FermionTerm` desejados.
Como os hamiltonianos são hermitianos por definição, indexamos termos usando o tipo mais especializado `HermitianFermionTerm` que também usa simetria hermitiana ao verificar se os termos são equivalentes.

Construamos alguns exemplos ilustrativos.
Considere o Hamiltonian $\hat{H} = a_0^\dagger a_1 + a_1^\dagger a_0$.
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
Podemos simplificar esta construção utilizando o facto de os operadores hamiltonianos serem operadores hermitianos.
Ao adicionar termos ao Hamiltonian usando `Add`, qualquer termo não eremitício como `fermionTerm0` é assumido ser emparelhado com o seu conjugado hermitário.
Assim, o seguinte corte representa também o mesmo Hamiltonian:
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

Utilizando as regras anti-comutação, alguns `FermionTerm` casos no Hamiltonian correspondem à mesma sequência de operadores fermiónicos, às vezes até um sinal negativo.
Por exemplo, considere o $H hamiltoniano=a_0^\punhal a_1^\punhal a_1 a_0 - a_1\dagger a_0^a punhal a_1 a_0 =2a_0^\dagger a_1^\dagger a_1 a_0$, que é uma soma de termos construídos acima.
Pode nem sempre ser claro para o utilizador que estes são termos equivalentes, pelo que podem ser adicionados ao Hamiltonian separadamente.
Em alternativa, pode-se estar interessado em modificar os termos já existentes no Hamiltoniano.
Nestes casos, podemos combinar termos equivalentes os seguintes.
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
Mais tarde, isto reduz o número de portões quânticos necessários para simular o Hamiltonian.

### <a name="internal-representation"></a>Representação Interna

Um Hamiltonian fermiónico com interações de um e dois corpos é representado em notação de segundo quantificado como

$$ \start{align} H=\sum\_{pq}h\_{pq}a^dagger\_{p}a\_{q}+\frac {2}{1} \sum\_{pqrs}h\_{pqrs}a^\dagger\_{p}a^\aapunhal\_{q}a\_{r}\_a {s}.
\end{align} $$

Nesta notação, existem no máximo coeficientes $N^2+N^4$.
No entanto, muitos destes coeficientes podem ser recolhidos, uma vez que correspondem ao mesmo operador.
Por exemplo, no caso em que $p,q,r,s$ são índices distintos, podemos usar as regras anti-comutação para mostrar que: $$ a^\dagger\_{p}a^a\dagger\_{q}a\_{r}a\_{s} = -a^\dagger\_{q}a^\dagger\_{p}a\_{r }a\_{s} = -a^\dagger\_{p}a^\dagger\_{q}a\_{s}a\_{r} = a^\dagger\_{q}a^\dagger\_{p}a\_{s}a\_{r}.
$$

Além disso, como $H$ é hermitiano, todos os operadores fermiónicos não hermitianos, dizem $h\_{pqrs}a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}$, tem um conjugado Hermitiano que também é encontrado em $H$. A fim de indexar exclusivamente grupos de termos caracterizados por estas simetrias, definimos uma encomenda canónica nos índices $(i\_1,\cdots,i\_n,j\_1,\cdots,j\_m)$ de qualquer sequência de operadores fermiónico $as\_\_s $n+m$ $a^\dagger\_{i\_1}\cdots a^\\_\_\_\_aada :
-   Todos os operadores de criação $a^\dagger\_{i\_\cdot}$ são colocados antes que todos os operadores de aniquilação $a\_{j\_\cdot}$.
-   Todos os índices de operadores de criação estão classificados em ordem ascendente, ou seja, $i\_1< i\_2< \cdots < i\_n$.
-   Todos os índices de aniquilação do operador estão classificados em ordem descendente, ou seja, $j\_1> j\_2 \cdots > j\_m$.
-   O índice mais à esquerda é inferior ou igual ao índice mais à direita, que é $i\_1\le j\_m$.

Identifiquemos este conjunto de índices ordenados canonicamente como $$ \begin {align} (i\_1,\cdots,i\_n,j\_1,\cdots,j\_m) \in S\_{n,m}.
\end{align} $$

Com esta ordem canónica, o Hamiltonian fermiónico pode ser expresso como $$ \start{align} H=\sum\_{(p,q)\em S\_{1,1}}h'\_{pq}\frac{a^\dagger\_{p}a\_{q}+a^\a^\dagger\_{q}a\_{p}}{2}+\soma\_{(p,q,r,s)\em S\_{2,2}}h'\_{pqrs}\frac{a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}+a^\a^\a^\a^\\_a^\a apunhal\_{r}a\_{q}a\_{p}}{2}, \end{align} $$ com integrals de um e dois eletrões adaptados $h'\_{pq}$ e $h'\_{pqrs}$, respectivamente.

