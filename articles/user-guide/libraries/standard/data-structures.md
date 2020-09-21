---
title: Estruturas de dados nas Q# bibliotecas padrão
description: Conheça as estruturas de dados, oráculos e geradores dinâmicos nas Q# bibliotecas padrão da Microsoft.
author: QuantumWriter
uid: microsoft.quantum.libraries.data-structures
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 51eb52d0b8ace972f6a425edba400ca9a8916d2e
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835592"
---
# <a name="data-structures-and-modeling"></a>Estruturas de Dados e Modelação #

## <a name="classical-data-structures"></a>Estruturas clássicas de dados ##

Juntamente com tipos definidos pelo utilizador para representar conceitos quânticos, o cânone também fornece operações, funções e tipos para trabalhar com dados clássicos utilizados no controlo de sistemas quânticos.
Por exemplo, a <xref:microsoft.quantum.arrays.reversed> função toma uma matriz como entrada e devolve a mesma matriz em ordem inversa.
Isto pode então ser usado numa matriz de tipo para evitar ter de `Qubit[]` aplicar portões desnecessários de $\operatorname{SWAP}$ ao converter entre representações quânticas de inteiros.
Da mesma forma, vimos na secção anterior que os tipos do formulário `(Int, Int -> T)` podem ser úteis para representar coleções de acesso aleatório, pelo que a <xref:microsoft.quantum.arrays.lookupfunction> função fornece uma maneira conveniente de construir tais tipos a partir de tipos de matrizes.

### <a name="pairs"></a>Pares ###

O cânone suporta a notação de estilo funcional para pares, complementando o acesso a tuples por desconstrução:

```qsharp
let pair = (PauliZ, register); // type (Pauli, Qubit[])
ApplyToEach(H, Snd(pair)); // No need to deconstruct to access the register.
```

### <a name="arrays"></a>Matrizes ###

O cânone fornece várias funções para manipular matrizes.
Estas funções são de tipo parametrizado, e assim podem ser usadas com matrizes de qualquer Q# tipo.
Por exemplo, a <xref:microsoft.quantum.arrays.reversed> função devolve uma nova matriz cujos elementos estão em ordem inversa a partir da sua entrada.
Isto pode ser usado para alterar a forma como um registo quântico é representado ao chamar operações:

```qsharp
let leRegister = LittleEndian(register);
// QFT expects a BigEndian, so we can reverse before calling.
QFT(BigEndian(Reversed(leRegister!)));
// This is how the LittleEndianAsBigEndian function is implemented:
QFT(LittleEndianAsBigEndian(leRegister));
```

Da mesma forma, a <xref:microsoft.quantum.arrays.subarray> função pode ser usada para reencomendar ou tomar subconjuntos dos elementos de uma matriz:

```qsharp
// Applies H to qubits 2 and 5.
ApplyToEach(H, Subarray([2, 5], register));
```

Quando combinado com o controlo de fluxo, funções de manipulação de matrizes tais como <xref:microsoft.quantum.arrays.zip> podem fornecer uma forma poderosa de expressar programas quânticos:

```qsharp
// Applies X₃ Y₁ Z₇ to a register of any size.
ApplyToEach(
    ApplyPauli(_, register),
    Map(
        EmbedPauli(_, _, Length(register)),
        Zip([PauliX, PauliY, PauliZ], [3, 1, 7])
    )
);
```

## <a name="oracles"></a>Oráculos ##

Na [fase de estimativa](https://en.wikipedia.org/wiki/Quantum_phase_estimation_algorithm) e [amplificação](https://en.wikipedia.org/wiki/Amplitude_amplification) da literatura o conceito de um oráculo aparece frequentemente.
Aqui o termo oráculo refere-se a uma blackbox subbroutina quântica que age sobre um conjunto de qubits e devolve a resposta como uma fase.
Esta sub-rotina pode muitas vezes ser considerada como uma entrada para um algoritmo quântico que aceita o oráculo, além de alguns outros parâmetros, e aplica uma série de operações quânticas e tratando uma chamada para esta subbroutina quântica como se fosse um portão fundamental.
Obviamente, para implementar o algoritmo maior, deve ser fornecida uma decomposição concreta do oráculo em portões fundamentais, mas tal decomposição não é necessária para entender o algoritmo que chama o oráculo.
Em Q# , esta abstração é representada por usar que as operações são valores de primeira classe, de modo que as operações podem ser passadas para implementações de algoritmos quânticos de forma de caixa preta.
Além disso, os tipos definidos pelo utilizador são utilizados para rotular as diferentes representações do oráculo de uma forma tipo segura, dificultando a conflação acidental de diferentes tipos de operações de caixa preta.

Tais oráculos aparecem em vários contextos diferentes, incluindo exemplos famosos como [a pesquisa de Grover](https://en.wikipedia.org/wiki/Grover%27s_algorithm) e algoritmos de simulação quântica.
Aqui focamo-nos nos oráculos necessários para apenas duas aplicações: amplificação de amplitude e estimativa de fase.
Primeiro discutiremos os oráculos de amplificação de amplitude antes de procedermos à estimativa de fase.

### <a name="amplitude-amplification-oracles"></a>Oráculos de amplificação da amplitude ###

O algoritmo de amplificação da amplitude visa realizar uma rotação entre um estado inicial e um estado final, aplicando uma sequência de reflexões do estado.
Para que o algoritmo funcione, precisa de uma especificação de ambos os estados.
Estas especificações são dadas por dois oráculos.
Estes oráculos funcionam quebrando as entradas em dois espaços, um subespaço "alvo" e um subespaço "inicial".
Os oráculos identificam esses subespaços, à semelhança da forma como os operadores da Pauli identificam dois espaços, aplicando uma fase $\pm 1$ a estes espaços.
A principal diferença é que estes espaços não precisam de ser semi-espaços nesta aplicação.
Note também que estes dois subespaços não são geralmente mutuamente exclusivos: haverá vetores que são membros de ambos os espaços.
Se isso não fosse verdade, então a amplificação da amplitude não teria qualquer efeito, por isso precisamos que o subespaço inicial tenha uma sobreposição não-zero com o subespaço alvo.

Vamos denotar o primeiro oráculo que precisamos para que a amplificação da amplitude seja $P \_ 0$, definida para ter a seguinte ação.  Para todos os estados $\ket{x}$ no subespaço "inicial" $P \_ 0 \ket{x} = -\ket{x}$ e para todos os estados $\ket{y}$ que não estão neste subespaço temos $P \_ 0 \ket{y} = \ket{y}$.
O oráculo que marca o subespaço alvo, $P_1$, assume exatamente a mesma forma.
Para todos os estados $\ket{x}$ no subespaço alvo (i.e., para todos os estados que gostaria que o algoritmo fosse despahá-lo), $P_1\ket{x} = -\ket{x}$.
Da mesma forma, para todos os estados $\ket{y}$ que não estão no subespaço alvo $P_1\ket{y} = \ket{y}$.
Estas duas reflexões são então combinadas para formar um operador que decreta um único passo de amplificação de amplitude, $Q = -P_0 P_1$, onde o sinal de menos geral só é importante a considerar em aplicações controladas.
A amplificação amplitude prossegue tomando um estado inicial, $\ket{\psi}$ que está no subespaço inicial e, em seguida, executa $\ket{\psi} \mapsto Q^m \ket{\psi}$.
A realização de tal iteração garante que se começar com um estado inicial que se sobreponha a $\sin^2 (\theta)$ com o espaço marcado, então depois de $m$ iterações esta sobreposição torna-se $\sin^2 ([2m + 1] \theta)$.
Por isso, normalmente queremos escolher $m$ para ser um parâmetro gratuito de tal forma que $[2m+1]\theta = \pi/2$; no entanto, tais escolhas rígidas não são tão importantes para algumas formas de amplificação da amplitude, tais como amplificação da amplitude fixa do ponto.
Este processo permite-nos preparar um estado no subespaço marcado utilizando quadraticamente menos consultas à função de marcação e à função de preparação do estado do que seria possível num dispositivo estritamente clássico.
É por isso que a amplificação da amplitude é um importante bloco de construção para muitas aplicações de computação quântica.

Para entender como usar o algoritmo, é útil fornecer um exemplo que dá uma construção dos oráculos.  Considere executar o algoritmo de Grover para pesquisas de base de dados nesta definição.
Na pesquisa de Grover, o objetivo é transformar o estado $\ket{+}{{\otimes n} = H^{\otimes n} \ket {0} $ em um dos (potencialmente) muitos estados marcados.
Para simplificar ainda mais, vamos apenas olhar para o caso em que o único estado marcado é $\ket {0} $.
Em seguida, temos dois oráculos: um que apenas marca o estado inicial $\ket{+}^{\otimes n}$ com um sinal de menos e outro que marca o estado marcado $\ket {0} $ com um sinal de menos.
Este último portão pode ser implementado utilizando a seguinte operação de processo, utilizando as operações de fluxo de controlo no cânone:

```qsharp
operation ReflectAboutAllZeros(register : Qubit[]) : Unit 
is Adj + Ctl {

    // Apply $X$ gates to every qubit.
    ApplyToEach(X, register);

    // Apply an $n-1$ controlled $Z$-gate to the $n^{\text{th}}$ qubit.
    // This gate will lead to a sign flip if and only if every qubit is
    // $1$, which happens only if each of the qubits were $0$ before step 1.
    Controlled Z(Most(register), Tail(register));

    // Apply $X$ gates to every qubit.
    ApplyToEach(X, register);
}
```

Este oráculo é então um caso especial da <xref:microsoft.quantum.canon.rall1> operação, que permite rodar por uma fase arbitrária em vez do caso de reflexão $\phi = \pi$.
Neste caso, `RAll1` é semelhante à operação do <xref:microsoft.quantum.intrinsic.r1> prelúdio, na medida em que gira cerca de $\ket{11\cdots1}$ em vez do estado de um único qubit $\ket {1} $.

O oráculo que marca o subespaço inicial pode ser construído da mesma forma.
Em pseudocódigo:

1. Aplique $H de portas a cada qubit.
2. Aplique $X de portais a cada qubit.
3. Aplique um $n-1$ controlado $Z$-gate no $n^{\text{th}} qubit.
4. Aplique $X de portais a cada qubit.
5. Aplique $H de portas a cada qubit.

Desta vez, demonstramos também a utilização <xref:microsoft.quantum.canon.applywith> em conjunto com a <xref:microsoft.quantum.canon.rall1> operação acima discutida:

```qsharp
operation ReflectAboutInitial(register : Qubit[]) : Unit
is Adj + Ctl {
    ApplyWithCA(ApplyToEach(H, _), ApplyWith(ApplyToEach(X, _), RAll1(_, PI()), _), register);
}
```

Podemos então combinar estes dois oráculos para rodar entre os dois estados e transformar deterministicamente $\ket{+}\{\otimes n}$ a $\ket {0} $ usando uma série de camadas de portões Hadamard que é proporcional a $\sqrt{2^n}$ (ou seja, $m\propto \sqrt{2^n}$) contra as camadas de cerca de $2^n$ que seriam necessárias para preparar não deterministicamente o estado de $\ket$ {0} preparando e medindo o estado inicial até que o resultado seja observado $0$

### <a name="phase-estimation-oracles"></a>Oráculos de estimativa de fase ###

Para a estimativa de fase, os oráculos são um pouco mais naturais.
O objetivo na estimativa de fase é conceber uma subrotina capaz de amostrar dos valores de uma matriz unitária.
Este método é indispensável na simulação quântica porque para muitos problemas físicos na química e na ciência dos materiais estes valores eigenvalues dão as energias do estado terrestre dos sistemas quânticos que nos fornecem informações valiosas sobre os diagramas de fase de materiais e dinâmicas de reação para moléculas.
Cada sabor da estimativa de fase precisa de uma entrada unitária.
Este unitário é habitualmente descrito por um de dois tipos de oráculos.

> [!TIP]
> Ambos os tipos de oráculo descritos abaixo estão cobertos nas amostras.
> Para saber mais sobre oráculos de consulta contínua, consulte a amostra [ **phaseEstimation** ](https://github.com/microsoft/Quantum/tree/main/samples/characterization/phase-estimation).
> Para saber mais sobre oráculos de consulta discreta, consulte a amostra [ **isingPhaseEstimation** ](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/phase-estimation).

O primeiro tipo de oráculo, a que chamamos um oráculo de consulta discreta e que representa com o tipo definido pelo <xref:microsoft.quantum.oracles.discreteoracle> utilizador, envolve simplesmente uma matriz unitária.
Se $U$ é o unitário cujos valores eigen valorizamos, então o oráculo para $U$ é simplesmente um substituto para uma sub-rotina que implementa $U$.
Por exemplo, pode-se levar $U$ para ser o oráculo $Q$ definido acima para estimação de amplitude.
Os valores eigenvalues desta matriz podem ser usados para estimar a sobreposição entre os estados iniciais e alvo, $\sin^2(\theta)$, usando quadráticamente menos amostras do que seria necessário de outra forma.
Isto ganha a aplicação de estimativa de fase usando o oráculo Grover $Q$ como entrada o apelido de estimativa de amplitude.
Outra aplicação comum, amplamente utilizada na metrologia quântica, envolve estimar um pequeno ângulo de rotação.
Por outras palavras, queremos estimar $\theta$ para um portão de rotação desconhecido do formulário $R_z(\theta)$.
Nesses casos, a sub-rotina com a qual interagiríamos para aprender este valor fixo de $\theta$ para o portão é $$ \start{align} U & = R_z(\theta) \\ \\ & = \begin{bmatrix} e^{{-i \theta / 2} & \\ \\ 0 0 & e^{i\ita/2 \end{bmat}}
\end{align} $$

O segundo tipo de oráculo utilizado na estimativa de fase é o oráculo de consulta contínua, representado pelo <xref:microsoft.quantum.oracles.continuousoracle> tipo.
Um oráculo de consulta contínua para estimativa de fase toma a forma $U(t)$ onde $t$ é um número real clássico conhecido.
Se deixarmos $U$ ser um unitário fixo, então o oráculo de consulta contínua toma a forma $U(t) = U^t$.
Isto permite-nos consultar matrizes como $\sqrt{U}$, que não poderia ser implementada diretamente no modelo de consulta discreta.

Este tipo de oráculo é valioso quando não se está a sondar um determinado unitário, mas sim deseja aprender as propriedades do gerador do unitário.
Por exemplo, na simulação quântica dinâmica o objetivo é conceber circuitos quânticos que se aproximem intimamente $U(t)=e^{-i H t}$ para uma matriz hermitiana $H$ e tempo de evolução $t$.
Os valores de eigen de $U(t)$ estão diretamente relacionados com os valores de $H$.
Para ver isto, considere um eigenvector de $H$: $H \ket{E} = E\ket{E}$ então é fácil ver a partir da definição da série de potência da matriz expoente que $U(t) \ket{E} = e^i\phi}\ket{E}= e^{-iEt}}ket(t{E{E}.}
Assim, estimando a fase eigense de $U(t)$ dá o $E do eigenvalue $E$ assumindo que o eigenvector $\ket{E}$ é a entrada no algoritmo de estimativa de fase.
No entanto, neste caso, o valor $t$ pode ser escolhido a critério do utilizador, uma vez que para qualquer valor suficientemente pequeno de $t$ o $E$ pode ser invertido exclusivamente através de $E=-\phi/t$.
Uma vez que os métodos de simulação quântica proporcionam a capacidade de realizar uma evolução fracionada, isto concede aos algoritmos de estimativa de fase uma liberdade adicional ao consultar o unitário, especificamente enquanto o modelo de consulta discreta permite que apenas unitários da forma $U^j$ se apliquem para o número inteiro $j$ a consulta contínua oráculo permite-nos aproximar unitários da forma $U^t$ para qualquer valor real $t$.
Isto é importante para espremer cada gota de eficiência fora dos algoritmos de estimativa de fase porque nos permite escolher precisamente a experiência que forneceria mais informações sobre $E$; que os métodos baseados em consultas discretas devem fazer com que se comprometam escolhendo o melhor número inteiro de consultas no algoritmo.

Como exemplo concreto disso, considere o problema de estimar não o ângulo de rotação de um portão, mas a frequência de procissão de um sistema quântico rotativo.
O unitário que descreve tal dinâmica quântica é $U(t)=R_z (2\omega t)$ para o tempo de evolução $t$ e frequência desconhecida $\omega$.
Neste contexto, podemos simular $U(t)$ para qualquer $t$ usando um único portão de $R_z$ e, como tal, não precisamos de nos restringir apenas a consultas discretas ao unitário.
Tal modelo contínuo também tem a propriedade que frequências superiores a $2\pi$ podem ser aprendidas a partir de processos de estimativa de fase que usam consultas contínuas porque informações de fase que de outra forma seriam mascaradas pelos cortes de ramo da função logaritmo podem ser reveladas a partir dos resultados de experiências realizadas em valores não proporcionais de $t$.
Assim, para problemas como este modelo de consulta contínua para a estimativa de fase oráculo não só são adequados, como também são preferíveis ao modelo de consulta discreta.
Por esta razão Q# tem funcionalidade para ambas as formas de consultas e deixa ao utilizador decidir sobre um algoritmo de estimativa de fase para adequar as suas necessidades e o tipo de oráculo que está disponível.

## <a name="dynamical-generator-modeling"></a>Modelação dinâmica do gerador ##

Os geradores da evolução do tempo descrevem como os estados evoluem através do tempo. Por exemplo, a dinâmica de um estado quântico $\ket{\psi}$ é regida pela equação schrödinger $\ \start{end{d\ket{\psi(t)}}{d} & = H\ket{\psi(t)}, \end{align} $$ com uma matriz eremita $H$, conhecida como o Hamiltonian, como o gerador. Dado um estado inicial $\ket{\psi(0)}$ no momento $t=0$, a solução formal para esta equação no momento $t$ pode ser, em princípio, escrito $$ \start{align} \ket{\psi(t)} = U(t)\ket{\psi(0)}, \end{align} $$ onde a matriz exponencial $U(t)=e^{-i H t}} é conhecida como o operador unitário de evolução temporal. Embora nos concentremos em geradores desta forma na seguinte, sublinhamos que o conceito se aplica mais amplamente, como a simulação de sistemas quânticos abertos, ou a equações diferenciais mais abstratas.

Um objetivo primário da simulação dinâmica é implementar o operador de evolução temporal em algum estado quântico codificado em qubits de um computador quântico.  Em muitos casos, o Hamiltonian pode ser dividido em uma soma de alguns $d$ termos mais simples

$$ \begin{align} H & = \sum^{d-1}_{j=0} H_j, \end{align} $$

onde a evolução do tempo por cada termo por si só é fácil de implementar num computador quântico. Por exemplo, se $H_j$ for um operador Pauli $X_1X_2$ agindo nos 1º e 2º elementos do registo qubit, a `qubits` evolução temporal por ele $t pode ser implementada simplesmente chamando a operação `Exp([PauliX,PauliX], t, qubits[1..2])` , que tem assinatura `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` . Como discutido mais tarde na Simulação hamiltoniana, uma solução então é aproximar a evolução do tempo por $H$ com uma sequência de operações mais simples

$$ \begin{align} U(t) & = \esquerda( e^{-iH \_ 0 t / r} e^{-iH \_ 1 t / r} \cdots e^{-iH \_ {d-1} t / r} \right){r} + \mathcal{O}(d^2\max_j \\ # H \_ j \\ [^2 t^2/r), \end{align} $$

onde o inteiro $r > 0$ controla o erro de aproximação.

A biblioteca de modelação de geradores dinâmicos fornece uma estrutura para codificar sistematicamente geradores complicados em termos de geradores mais simples. Tal descrição pode então ser passada para, digamos, a biblioteca de simulação para implementar a evolução do tempo através de um algoritmo de simulação de escolha, com muitos detalhes automaticamente tratados.

> [!TIP]
> A biblioteca dinâmica do gerador descrita abaixo está coberta nas amostras. Para um exemplo baseado no modelo Ising, consulte a amostra [ **isingGenerators** ](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/generators).
> Para um exemplo baseado em hidrogénio molecular, consulte as [**amostras H2SimulationCmdLine**](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/command-line) e [**H2SimulationGUI.**](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/gui)

### <a name="complete-description-of-a-generator"></a>Descrição completa de um gerador ###

No nível superior, uma descrição completa de um Hamiltonian está contida no `EvolutionGenerator` tipo definido pelo utilizador que tem dois componentes.:

```qsharp
newtype EvolutionGenerator = (EvolutionSet, GeneratorSystem);
```

O `GeneratorSystem` tipo definido pelo utilizador é uma descrição clássica do Hamiltonian.

```qsharp
newtype GeneratorSystem = (Int, (Int -> GeneratorIndex));
```

O primeiro elemento `Int` da tuple armazena o número de termos $d$ no Hamiltonian, e o segundo elemento `(Int -> GeneratorIndex)` é uma função que mapeia um índice inteiro em \{ $0,...,d-1$ \} para um tipo definido pelo utilizador que identifica `GeneratorIndex` exclusivamente cada termo primitivo no Hamiltonian. Note que ao expressar a coleção de termos no Hamiltonian como uma função e não como uma `GeneratorIndex[]` matriz, isto permite a computação on-the-fly do `GeneratorIndex` que é especialmente útil ao descrever os hamiltonianos com um grande número de termos.

Crucialmente, não impomos uma convenção sobre os termos primitivos identificados pelos `GeneratorIndex` são fáceis de simular. Por exemplo, os termos primitivos podem ser operadores de Pauli como discutido acima, mas também podem ser operadores de aniquilação e criação fermiónicas comumente usados na simulação de química quântica. Por si só, um não é insignificante, uma `GeneratorIndex` vez que não descreve como a evolução do tempo pelo termo que aponta pode ser implementada como um circuito quântico.

Isto é resolvido especificando um tipo definido pelo `EvolutionSet` utilizador que mapeia qualquer `GeneratorIndex` , extraído de algum conjunto canónico, para um operador unitário, o `EvolutionUnitary` , expresso como um circuito quântico. O `EvolutionSet` define a convenção de como um é `GeneratorIndex` estruturado, e também define o conjunto de possíveis `GeneratorIndex` .

```qsharp
newtype EvolutionSet = (GeneratorIndex -> EvolutionUnitary);
```

### <a name="pauli-operator-generators"></a>Geradores de Operador Pauli ###

Um exemplo concreto e útil de geradores são os hamiltonianos que são uma soma de operadores Pauli, cada um possivelmente com um coeficiente diferente.
$$ \start{align} H & = \sum^{d-1}_{j=0} a_j H_j, \end{align} $$ onde cada $\hat H_j$ é agora retirado do grupo Pauli. Para estes sistemas, fornecemos o `PauliEvolutionSet()` tipo que define uma `EvolutionSet` convenção de como um elemento do grupo Pauli e um coeficiente podem ser identificados por um `GeneratorIndex` , que tem a seguinte assinatura.

```qsharp
newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```

Na nossa codificação, o primeiro parâmetro `Int[]` especifica uma corda Pauli, onde $\hat I\rightarrow 0$, $\hat X\rightarrow 1$, $\hat Y\rightarrow 2$, e $\hat Z\rightarrow 3$. O segundo parâmetro `Double[]` armazena o coeficiente da corda Pauli no Hamiltonian. Note que apenas o primeiro elemento desta matriz é usado. O terceiro parâmetro `Int[]` indexa os qubits em que esta corda Pauli age, e não deve ter elementos duplicados. Assim, o termo Hamiltonian $0,4 \hat X_0 \hat Y_8\hat I_2\hat Z_1$ pode ser representado como

```qsharp
let generatorIndexExample = GeneratorIndex(([1,2,0,3], [0.4]]), [0,8,2,1]);
```

É `PauliEvolutionSet()` uma função que mapeia qualquer `GeneratorIndex` um deste formulário para uma com a seguinte `EvolutionUnitary` assinatura.

```qsharp
newtype EvolutionUnitary = ((Double, Qubit[]) => Unit is Adj + Ctl);
```

O primeiro parâmetro representa uma duração temporal, que será multiplicada pelo coeficiente na `GeneratorIndex` evolução unitária. O segundo parâmetro é o registo qubit em que os atos unitários. 

### <a name="time-dependent-generators"></a>Geradores dependentes do tempo ###

Em muitos casos, também estamos interessados em modelar geradores dependentes do tempo, como pode ocorrer na equação schrödinger $$ \start{{d\ket{\psi(t)}}{d t} & = \hat H(t) \ket{\psi(t)}, \end{align} $$ onde o gerador $\hat H(t)$ é agora dependente do tempo. A extensão dos geradores independentes do tempo acima para este caso é simples. Em vez de termos uma descrição fixa `GeneratorSystem` do Hamiltonian para sempre $t$, em vez disso temos o `GeneratorSystemTimeDependent` tipo definido pelo utilizador.

```qsharp
newtype GeneratorSystemTimeDependent = (Double -> GeneratorSystem);
```

O primeiro parâmetro é um parâmetro de agenda contínua $s\in [0,1]$, e funções deste tipo devolvem um `GeneratorSystem` para esse horário. Note que o parâmetro do horário pode estar relacionado linearmente com o parâmetro de tempo físico, por exemplo, $s = t / T$, durante algum tempo total de simulação $T$. No entanto, em geral, este não deve ser o caso.

Da mesma forma, uma descrição completa deste gerador requer um `EvolutionSet` , e assim definimos um tipo definido `EvolutionSchedule` pelo utilizador.

```qsharp
newtype EvolutionSchedule = (EvolutionSet, GeneratorSystemTimeDependent);
```
