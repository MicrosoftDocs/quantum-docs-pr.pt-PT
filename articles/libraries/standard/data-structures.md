---
title: 'P # bibliotecas padrão-estruturas de dados | Microsoft Docs'
description: 'P # bibliotecas padrão-estruturas de dados'
author: QuantumWriter
uid: microsoft.quantum.libraries.data-structures
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: e8b28561f1aba37cb5bf41c6176386d19bfacf06
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184513"
---
# <a name="data-structures-and-modeling"></a>Estruturas de dados e modelagem #

## <a name="classical-data-structures"></a>Estruturas de dados clássicas ##

Juntamente com tipos definidos pelo usuário para representar conceitos de Quantum, a Canon também fornece operações, funções e tipos para trabalhar com dados clássicos usados no controle de sistemas Quantum.
Por exemplo, a função <xref:microsoft.quantum.arrays.reversed> usa uma matriz como entrada e retorna a mesma matriz na ordem inversa.
Isso pode ser usado em uma matriz do tipo `Qubit[]` para evitar a necessidade de aplicar Gates $ \operatorname{SWAP} $ desnecessários ao converter entre representações de Quantum de inteiros.
Da mesma forma, vimos na seção anterior que tipos do formulário `(Int, Int -> T)` podem ser úteis para representar coleções de acesso aleatório, de modo que a função <xref:microsoft.quantum.arrays.lookupfunction> fornece uma maneira convienent de construir tais tipos de tipos de matriz.

### <a name="pairs"></a>Pares ###

A Canon dá suporte à notação de estilo funcional para pares, complementando o acesso a tuplas por desconstrução:

```qsharp
let pair = (PauliZ, register); // type (Pauli, Qubit[])
ApplyToEach(H, Snd(pair)); // No need to deconstruct to access the register.
```

### <a name="arrays"></a>Storage ###

A Canon fornece várias funções para manipular matrizes.
Essas funções são de tipo parametrizado e, portanto, podem ser usadas com matrizes de qualquer tipo Q #.
Por exemplo, a função <xref:microsoft.quantum.arrays.reversed> retorna uma nova matriz cujos elementos estão na ordem inversa de sua entrada.
Isso pode ser usado para alterar como um registro de Quantum é representado ao chamar operações:

```qsharp
let leRegister = LittleEndian(register);
// QFT expects a BigEndian, so we can reverse before calling.
QFT(BigEndian(Reversed(leRegister!)));
// This is how the LittleEndianAsBigEndian function is implemented:
QFT(LittleEndianAsBigEndian(leRegister));
```

Da mesma forma, a função <xref:microsoft.quantum.arrays.subarray> pode ser usada para reordenar ou pegar subconjuntos dos elementos de uma matriz:

```qsharp
// Applies H to qubits 2 and 5.
ApplyToEach(H, Subarray([2, 5], register));
```

Quando combinado com o controle de fluxo, as funções de manipulação de matriz, como <xref:microsoft.quantum.arrays.zip>, podem fornecer uma maneira poderosa para expressar os programas da Quantum:

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

## <a name="oracles"></a>Oracle ##

Na [estimativa da fase](https://en.wikipedia.org/wiki/Quantum_phase_estimation_algorithm) e na [amplificação da amplitude](https://en.wikipedia.org/wiki/Amplitude_amplification) , o conceito de um Oracle é exibido com frequência.
Aqui, o termo Oracle se refere a uma sub-rotina Quantum Blackbox que age em um conjunto de qubits e retorna a resposta como uma fase.
Essa sub-rotina muitas vezes pode ser considerada como uma entrada para um algoritmo Quantum que aceita o Oracle, além de alguns outros parâmetros, e aplica uma série de operações Quantum e tratando uma chamada para essa sub-rotina Quantum como se fosse um portão fundamental.
Obviamente, para realmente implementar o algoritmo maior, uma decomposição concreta do Oracle em Gates fundamentais deve ser fornecida, mas essa decomposição não é necessária para entender o algoritmo que chama o Oracle.
Em Q #, essa abstração é representada usando essas operações são valores de primeira classe, de modo que as operações podem ser passadas para implementações de algoritmos Quantum de uma maneira preta.
Além disso, os tipos definidos pelo usuário são usados para rotular as diferentes representações do Oracle de forma segura, dificultando acidentalmente a definição de diferentes tipos de operações de caixa preta.

Esses Oracle são exibidos em vários contextos diferentes, incluindo exemplos famosos, como os algoritmos de simulação de pesquisa e Quantum [do Grover](https://en.wikipedia.org/wiki/Grover%27s_algorithm) .
Aqui, nos concentramos nos Oracle necessários apenas para dois aplicativos: amplificação de amplitude e estimativa de fase.
Primeiro, discutiremos a amplitude de amplificações Oracle antes de se propassar à estimativa de fase.

### <a name="amplitude-amplification-oracles"></a>Soluções de amplificação de amplitude Oracle ###

O algoritmo de amplificação amplitude visa executar uma rotação entre um estado inicial e um estado final aplicando uma sequência de reflexos do estado.
Para que o algoritmo funcione, ele precisa de uma especificação de ambos os Estados.
Essas especificações são dadas por dois Oracle.
Esses Oracle funcionam dividindo as entradas em dois espaços, um subespaço "de destino" e um subespaço "inicial".
Os Oracle identificam esses subespaços, semelhante ao modo como os operadores de Pauli identificam dois espaços, aplicando uma fase de $ \pm $1 a esses espaços.
A principal diferença é que esses espaços não precisam conter semiespaços neste aplicativo.
Observe também que esses dois subespaços geralmente não são mutuamente exclusivos: haverá vetores que são membros de ambos os espaços.
Se isso não fosse verdade, a amplificação de amplitude não teria nenhum efeito, portanto, precisamos que o subespaço inicial tenha uma sobreposição diferente de zero com o subespaço de destino.

Indicaremos a primeira Oracle que precisamos para que a amplificação de amplitude seja $P\_$0, definida para ter a ação a seguir.  Para todos os Estados $ \ket{x} $ no subespaço "inicial" $P\_0 \ket{x} =-\ket{x} $ e para todos os Estados $ \ket{y} $ que não estão nesse subespaço, temos $P\_0 \ket{y} = \ket{y} $.
O Oracle que marca o subespaço de destino, $P _1 $, assume exatamente a mesma forma.
Para todos os Estados $ \ket{x} $ no subespaço de destino (ou seja, para todos os Estados que você deseja que o algoritmo gere), $P _1 \ ket {x} =-\ket{x} $.
Da mesma forma, para todos os Estados $ \ket{y} $ que não estão no subespaço de destino $P _1 \ ket {y} = \ket{y} $.
Esses dois reflexos são então combinados para formar um operador que atue em uma única etapa de amplificação de amplitude, $Q =-P_0 P_1 $, em que o sinal de subtração geral é apenas importante para considerar em aplicativos controlados.
Em seguida, a amplificação de amplitude prossegue com um estado inicial, $ \ket{\psi} $, que está no subespaço inicial e, em seguida, executa $ \ket{\psi} \mapsto Q ^ m \ket{\psi} $.
A execução dessa iteração garante que, se uma começar com um estado inicial que tenha a sobreposição de $ \sin ^ 2 (\theta) $ com o espaço marcado, depois de $m $ iterações essa sobreposição se tornará $ \sin ^ 2 ([2m + 1] \theta) $.
Portanto, normalmente desejamos escolher $m $ para ser um parâmetro gratuito, de modo que $ [2m + 1] \theta = \ pi/2 $; no entanto, essas opções rígidas não são tão importantes para algumas formas de amplificação de amplitude, como amplificação de amplitude de ponto fixo.
Esse processo nos permite preparar um estado no subespaço marcado usando, de forma quadrática, menos consultas para a função de marcação e a função de preparação de estado do que seria possível em um dispositivo estritamente clássico.
É por isso que a amplificação de amplitude é um bloco de construção significativo para muitos aplicativos de computação Quantum.

Para entender como usar o algoritmo, é útil fornecer um exemplo que fornece uma construção dos Oracle...  Considere executar o algoritmo do Grover para pesquisas de banco de dados nessa configuração.
Na pesquisa do Grover, o objetivo é transformar o estado $ \ket{+} ^ {\otimes n} = H ^ {\otimes n} \ket{0}$ em um (potencialmente) muitos Estados marcados.
Para simplificar ainda mais, vamos apenas examinar o caso em que o único estado marcado é $ \ket{0}$.
Em seguida, temos o design de dois Oracle: um que marca o estado inicial $ \ket{+} ^ {\otimes n} $ com um sinal de menos e outro que marca o estado marcado $ \ket{0}$ com um sinal de subtração.
A última porta pode ser implementada usando a seguinte operação de processo, usando as operações de fluxo de controle na Canon:

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

Esse Oracle é, então, um caso especial da operação de <xref:microsoft.quantum.canon.rall1>, que permite a rotação por uma fase arbitrária em vez do caso de reflexão $ \phi = \pi $.
Nesse caso, `RAll1` é semelhante à operação <xref:microsoft.quantum.intrinsic.r1> prelúdio, pois ele gira aproximadamente $ \ket{11\cdots1} $ em vez do estado single-qubit $ \ket{1}$.

A Oracle que marca o subespaço inicial pode ser construída da mesma forma.
No pseudocódigo:

1. Aplique $H $ Gates a cada qubit.
2. Aplique $X $ Gates a cada qubit.
3. Aplique uma $Z $-Gate controlada pelo $n-$1 ao $n ^ {\Text{th}} $ qubit.
4. Aplique $X $ Gates a cada qubit.
5. Aplique $H $ Gates a cada qubit.

Desta vez, também demonstramos o uso de <xref:microsoft.quantum.canon.applywith> junto com a operação <xref:microsoft.quantum.canon.rall1> discutida acima:

```qsharp
operation ReflectAboutInitial(register : Qubit[]) : Unit
is Adj + Ctl {
    ApplyWithCA(ApplyToEach(H, _), ApplyWith(ApplyToEach(X, _), RAll1(_, PI()), _), register);
}
```

Em seguida, podemos combinar esses dois Oracle juntos para girar entre os dois Estados e transformar de forma determinística $ \ket{+} ^ {\otimes n} $ para $ \ket{0}$ usando várias camadas de Hadamard Gates que é proporcional a $ \sqrt{2 ^ n} $ (IE $m \propto \sqrt{2 ^ n} $) versus as aproximadamente $2 ^ n $ camadas que seriam necessárias para preparar de forma não determinística o estado de{0}$ $ \ket $ preparando e medindo o estado inicial até que o resultado $0 $ seja observado.

### <a name="phase-estimation-oracles"></a>Estimativa de fase Oracle ###

Para a estimativa de fase, os Oracle são um pouco mais naturais.
A estimativa de objetivo na fase é criar uma sub-rotina capaz de amostragem da eigenvalues de uma matriz unitário.
Esse método é indispensáveis na simulação do Quantum porque, para muitos problemas físicos em química e ciência de material, esses eigenvalues fornecem o energias de estado de terra de sistemas Quantum que fornece informações valiosas sobre os diagramas de fase do dinâmica de materiais e reação para moléculas.
Cada tipo de estimativa de fase precisa de uma entrada unitário.
Essa unitário é normalmente descrita por um dos dois tipos de Oracle.

> [!TIP]
> Os dois tipos de Oracle descritos abaixo são abordados nos exemplos.
> Para saber mais sobre Oracle de consulta contínua, consulte o exemplo de [ **PhaseEstimation** ](https://github.com/Microsoft/Quantum/tree/master/Samples/src/PhaseEstimation).
> Para saber mais sobre Oracle de consulta discreta, consulte o exemplo de [ **IsingPhaseEstimation** ](https://github.com/Microsoft/Quantum/tree/master/Samples/src/IsingPhaseEstimation).

O primeiro tipo de Oracle, que chamamos de uma consulta discreta da Oracle e que representam com o tipo definido pelo usuário <xref:microsoft.quantum.oracles.discreteoracle>, simplesmente envolve uma matriz unitário.
Se $U $ é o unitário cujo eigenvalues desejamos estimar, o Oracle for $U $ é simplesmente um substituto para uma sub-rotina que implementa $U $.
Por exemplo, é possível pegar $U $ para ser o Oracle $Q $ definido acima para a estimativa de amplitude.
O eigenvalues dessa matriz pode ser usado para estimar a sobreposição entre os Estados inicial e de destino, $ \sin ^ 2 (\theta) $, usando, de forma quadrática, menos amostras do que uma delas precisaria.
Isso ganha a aplicação da estimativa de fase usando o Grover Oracle $Q $ como entrada do moniker de estimativa de amplitude.
Outro aplicativo comum, amplamente usado no Quantum metrologia, envolve a estimativa de um pequeno ângulo de rotação.
Em outras palavras, desejamos estimar $ \theta $ para uma porta de rotação desconhecida do formulário $R _z (\theta) $.
Nesses casos, a sub-rotina com a qual gostaríamos de interagir para aprender esse valor fixo de $ \theta $ para a porta é $ $ \begin{align} U & = R_z (\theta) \\\\ & = \begin{bmatrix} e ^ {-i \theta/2} & 0 \\\\ 0 & e ^ {i \ teta/2} \end{bmatrix}.
\end{align} $ $

O segundo tipo de Oracle usado na estimativa de fase é a consulta contínua Oracle, representada pelo tipo de <xref:microsoft.quantum.oracles.continuousoracle>.
Uma consulta contínua Oracle para estimativa de fase assume a forma $U (t) $, em que $t $ é um número real conhecido.
Se permitirmos que $U $ seja um unitário fixo, a consulta contínua Oracle usará a forma $U (t) = U ^ t $.
Isso nos permite consultar matrizes, como $ \sqrt{U} $, que não puderam ser implementadas diretamente no modelo de consulta discreto.

Esse tipo de Oracle é valioso quando você não está investigando um determinado unitário, mas deseja aprender as propriedades do gerador do unitário.
Por exemplo, na simulação do Quantum dinâmico, a meta é planejar os circuitos da Quantum que aproximam $U (t) = e ^ {-i H} $ para uma matriz Hermitian $H $ e tempo de evolução $t $.
O eigenvalues de $U (t) $ está diretamente relacionado ao eigenvalues de $H $.
Para ver isso, considere um eigenvector de $H $: $H \ket{E} = E\ket {E} $ em seguida, é fácil ver a partir da definição da série de energia do exponencial de matriz que $U (t) \ket{E} = E ^ {i\phi} \ ket {E} = e ^ {-iEt} \ket{E} $.
Assim, estimar o eigenphase de $U (t) $ dá ao eigenvalue $E $ supondo que eigenvector $ \ket{E} $ seja inserido no algoritmo estimativa de fase.
No entanto, nesse caso, o valor $t $ pode ser escolhido de acordo com o critério do usuário, pois para qualquer valor suficientemente pequeno de $t $ eigenvalue $E $ pode ser unicamente invertido por meio de $E =-\ Phi/t $.
Como os métodos de simulação do Quantum fornecem a capacidade de executar uma evolução fracionária, isso concede aos algoritmos de estimativas de fase uma liberdade adicional ao consultar o unitário, especificamente enquanto o modelo de consulta discreto permite apenas unidades do formulário $U ^ j $ para aplicado a inteiro $j $ a consulta contínua Oracle nos permite aproximar as unidades do formulário $U ^ t $ para qualquer $t com valor real.
Isso é importante para preencher todos os últimos onças de eficiência dos algoritmos de estimativa de fase, pois eles nos permitem escolher precisamente o experimento que forneceria a maioria das informações sobre $E $; enquanto os métodos baseados em consultas discretas devem fazer com a comprometetion escolhendo o melhor número inteiro de consultas no algoritmo.

Como um exemplo concreto disso, considere o problema de estimar não o ângulo de rotação de um portão, mas a frequência de processamento de um sistema Quantum rotativo.
O unitário que descreve tal dinâmica de Quantum é $U (t) = R_z (2 \ ômega t) $ para tempo de evolução $t $ e frequência desconhecida $ \omega $.
Nesse contexto, podemos simular $U (t) $ para qualquer $t $ usando uma única porta de $R _z $ e, como tal, não é necessário se restringir a apenas consultas discretas para o unitário.
Esse modelo contínuo também tem a propriedade que as frequências maiores que $2 \ PI $ podem ser aprendidas dos processos de estimativa de fase que usam consultas contínuas, pois as informações da fase que, de outra forma, seriam mascaradas pelos recortes de ramificação da função logarítmica podem ser revelado dos resultados de experimentos executados em valores não proporcionals de $t $.
Portanto, para problemas como esses modelos de consulta contínua para a estimativa de fase, o Oracle não é apenas apropriado, mas também é preferível ao modelo de consulta discreto.
Por esse motivo, Q # tem funcionalidade para ambos os formulários de consultas e deixá-lo para o usuário decidir sobre um algoritmo de estimativa de fase para atender às suas necessidades e o tipo de Oracle que está disponível.

## <a name="dynamical-generator-modeling"></a>Modelagem de gerador dinâmico ##

Geradores de tempo-evolução descrevem como os Estados evoluem ao longo do tempo. Por exemplo, o Dynamics de um estado Quantum $ \ket{\psi} $ é regido pela equação Schrödinger $ $ \begin{align} i\frac {d \ket{\psi (t)}} {d t} & = H \ket{\psi (t)}, \end{align} $ $ com uma matriz Hermitian $H $, conhecida como Hamiltonian, como o gerador de Motion. Devido a um estado inicial $ \ket{\psi (0)} $ at time $t = $0, a solução formal para esta equação no tempo $t $ pode ser, em princípio, escrita $ $ \begin{align} \ket{\psi (t)} = U (t) \ket{\psi (0)}, \end{Align} $ $, em que a $U exponencial (t) = e ^ {-i H} $ é conhecido como o operador de tempo unitário-evolução. Embora possamos nos concentrar nos geradores desse formulário nos seguintes, enfatizamos que o conceito se aplica mais amplamente, como a simulação de sistemas Quantum abertos ou a equações diferenciais mais abstratas.

Um objetivo principal da simulação dinâmica é implementar o operador tempo-evolução em algum estado Quantum codificado em qubits de um computador Quantum.  Em muitos casos, o Hamiltonian pode ser dividido em uma soma de alguns termos $d $ mais simples

$ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} H_j, \end{align} $ $

onde a evolução de tempo de cada termo sozinho é fácil de implementar em um computador Quantum. Por exemplo, se $H _J $ for um operador Pauli $X _1X_2 $ atuando nos elementos 1 e 2 do `qubits`de registro de qubit, a evolução do tempo por ti para qualquer momento $t $ pode ser implementado simplesmente chamando a operação `Exp([PauliX,PauliX], t, qubits[1..2])`, que tem assinatura `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`. Conforme discutido posteriormente na simulação de Hamiltonian, uma solução é aproximar a evolução do tempo por $H $ com uma sequência de operações mais simples

$ $ \begin{align} U (t) & = \left (e ^ {-iH\_0 t/r} e ^ {-iH\_1 t/r} \cdots e ^ {-iH\_{d-1} t/r} \right) ^ {r} + \mathcal{O} (d ^ 2 \max_j \\| H\_j\\| ^ 2 t ^ 2/r), \end{align} $ $

em que o inteiro $r > $0 controla o erro de aproximação.

A biblioteca de modelagem de gerador dinâmico fornece uma estrutura para codificar sistematicamente geradores complicados em termos de geradores mais simples. Essa descrição pode então ser passada para, digamos, a biblioteca de simulações para implementar a evolução do tempo por um algoritmo de simulação de escolha, com muitos detalhes automaticamente resolvidos.

> [!TIP]
> A biblioteca de gerador dinâmico descrita abaixo é abordada nos exemplos. Para obter um exemplo baseado no modelo Ising, consulte o exemplo [ **IsingGenerators** ](https://github.com/Microsoft/Quantum/tree/master/Samples/src/IsingGenerators).
> Para obter um exemplo baseado em molecular Hydrogen, consulte os exemplos de [**H2SimulationCmdLine**](https://github.com/Microsoft/Quantum/tree/master/Samples/src/H2SimulationCmdLine) e [**H2SimulationGUI**](https://github.com/Microsoft/Quantum/tree/master/Samples/src/H2SimulationGUI) .

### <a name="complete-description-of-a-generator"></a>Descrição completa de um gerador ###

No nível superior, uma descrição completa de um Hamiltonian está contida no tipo de `EvolutionGenerator` definido pelo usuário que tem dois componentes.:

```qsharp
newtype EvolutionGenerator = (EvolutionSet, GeneratorSystem);
```

O tipo de `GeneratorSystem` definido pelo usuário é uma descrição clássica do Hamiltonian.

```qsharp
newtype GeneratorSystem = (Int, (Int -> GeneratorIndex));
```

O primeiro elemento `Int` da tupla armazena o número de termos $d $ no Hamiltonian, e o segundo elemento `(Int -> GeneratorIndex)` é uma função que mapeia um índice de número inteiro em $\{0, 1,..., d-1\}$ para um tipo de `GeneratorIndex` definido pelo usuário que identifica exclusivamente cada um termo primitivo no Hamiltonian. Observe que, ao expressar a coleção de termos no Hamiltonian como uma função, em vez de como uma matriz `GeneratorIndex[]`, isso permite a computação imediata da `GeneratorIndex`, o que é especialmente útil ao descrever Hamiltonians com um grande número de termos.

Crucialmente, não impõem uma Convenção sobre quais termos primitivos identificados pela `GeneratorIndex` são fáceis de simular. Por exemplo, os termos primitivos podem ser operadores Pauli como discutidos acima, mas também podem ser Fermionic Annihilation e operadores de criação comumente usados na simulação química do Quantum. Por si só, um `GeneratorIndex` não faz sentido, pois não descreve como a evolução do tempo pelo termo que ele aponta pode ser implementada como um circuito Quantum.

Isso é resolvido especificando um tipo de `EvolutionSet` definido pelo usuário que mapeia qualquer `GeneratorIndex`, extraído de algum conjunto canônico, para um operador unitário, o `EvolutionUnitary`, expresso como um circuito Quantum. A `EvolutionSet` define a Convenção de como uma `GeneratorIndex` é estruturada e também define o conjunto de `GeneratorIndex`possíveis.

```qsharp
newtype EvolutionSet = (GeneratorIndex -> EvolutionUnitary);
```

### <a name="pauli-operator-generators"></a>Geradores do operador Pauli ###

Um exemplo concreto e útil de geradores são Hamiltonians que são uma soma dos operadores Pauli, cada um possivelmente com um coeficiente diferente.
$ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} a_j H_j, \end{Align} $ $, em que cada $ \hat H_j $ agora é desenhado do grupo Pauli. Para esses sistemas, fornecemos o `PauliEvolutionSet()` do tipo `EvolutionSet` que define uma Convenção de como um elemento do grupo Pauli e um coeficiente pode ser identificado por um `GeneratorIndex`, que tem a assinatura a seguir.

```qsharp
newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```

Em nossa codificação, o primeiro parâmetro `Int[]` especifica uma cadeia de caracteres Pauli, em que $ \hat I\rightarrow $0, $ \hat X\rightarrow $1, $ \hat Y\rightarrow $2 e $ \hat Z\rightarrow $3. O segundo parâmetro `Double[]` armazena o coeficiente da cadeia de caracteres Pauli no Hamiltonian. Observe que apenas o primeiro elemento dessa matriz é usado. O terceiro parâmetro `Int[]` indexa o qubits em que essa cadeia de caracteres Pauli atua e não deve ter nenhum elemento duplicado. Portanto, o Hamiltonian Term $0.04 \hat X_0 \hat Y_8\hat I_2\hat Z_1 $ pode ser representado como

```qsharp
let generatorIndexExample = GeneratorIndex(([1,2,0,3], [0.4]]), [0,8,2,1]);
```

O `PauliEvolutionSet()` é uma função que mapeia qualquer `GeneratorIndex` deste formulário para um `EvolutionUnitary` com a assinatura a seguir.

```qsharp
newtype EvolutionUnitary = ((Double, Qubit[]) => Unit is Adj + Ctl);
```

O primeiro parâmetro representa um tempo de duração, que será multiplicado pelo coeficiente no `GeneratorIndex`, da evolução unitário. O segundo parâmetro é o qubit registrar o unitário em que atua. 

### <a name="time-dependent-generators"></a>Geradores dependentes de tempo ###

Em muitos casos, também estamos interessados em geradores dependentes de tempo de modelagem, como pode ocorrer na equação Schrödinger $ $ \begin{align} i\frac {d \ket{\psi (t)}} {d t} & = \hat H (t) \ket{\psi (t)}, \end{align} $ $ em que o gerador $ \hat H (t) $ é agora depende do tempo. A extensão dos geradores independentes de tempo acima desse caso é simples. Em vez de ter um `GeneratorSystem` fixo descrevendo o Hamiltonian para todos os horários $t $, em vez disso, temos o tipo de `GeneratorSystemTimeDependent` definido pelo usuário.

```qsharp
newtype GeneratorSystemTimeDependent = (Double -> GeneratorSystem);
```

O primeiro parâmetro é um parâmetro de agendamento contínuo $s na [0, 1] $ e as funções desse tipo retornam um `GeneratorSystem` para esse agendamento. Observe que o parâmetro de agendamento pode estar linearmente relacionado ao parâmetro de tempo físico, por exemplo, $s = t/T $, para algum tempo total de simulação $T $. No entanto, em geral, esse não precisa ser o caso.

Da mesma forma, uma descrição completa desse gerador requer uma `EvolutionSet`e, portanto, definimos um tipo de `EvolutionSchedule` definido pelo usuário.

```qsharp
newtype EvolutionSchedule = (EvolutionSet, GeneratorSystemTimeDependent);
```
