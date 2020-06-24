---
title: Aplicações nas bibliotecas padrão Q#
description: Saiba mais sobre duas aplicações fundamentais na computação quântica - simulação hamiltoniana e algoritmo de pesquisa de Shor.
author: QuantumWriter
uid: microsoft.quantum.libraries.applications
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 25b06ac697c958b15a756191fb8a4ac49644edd7
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275796"
---
# <a name="applications"></a>Aplicações #

## <a name="hamiltonian-simulation"></a>Simulação Hamiltoniana ##

A simulação dos sistemas quânticos é uma das aplicações mais excitantes da computação quântica.
Num computador clássico, a dificuldade em simular mecânica quântica, em geral, escala com a dimensão $N$ da sua representação de vetores de estado.
À medida que esta representação cresce exponencialmente com o número de qubits $n$ $N=2^n$, um traço conhecido também como a [maldição da dimensionalidade,](xref:microsoft.quantum.concepts.multiple-qubits)a simulação quântica no hardware clássico é intratável.

No entanto, a situação pode ser muito diferente no hardware quântico. A variação mais comum da simulação quântica é chamada o problema de simulação hamiltoniana independente do tempo. Lá, um é fornecido com uma descrição do sistema Hamiltonian $H$, que é uma matriz hermitiana, e algum estado quântico inicial $\ket{\psi(0)}} que é codificado em alguma base em $n$ qubits em um computador quântico. À medida que os estados quânticos em sistemas fechados evoluem sob a equação de Schrödinger $\ \begin{align} i\frac{d \ket{\psi(t)}}}}}}}}}}}}}}}}d} & = H\ket{\psi(t)}, \end{align} $$ O objetivo é implementar o operador unitário de evolução do tempo $U(t)=e^{-iHt}$ em algum momento fixo $t$, onde $\ket{\psi(t)}=U(t)\ket{\psi(0)}} resolve a equação de Schrödinger.
Análogamente, o problema de simulação hamiltoniano dependente do tempo resolve a mesma equação, mas com $H(t)$ agora uma função do tempo.

A simulação hamiltoniana é um dos principais componentes de muitos outros problemas de simulação quântica, e as soluções para o problema de simulação hamiltoniana são algoritmos que descrevem uma sequência de portões quânticos primitivos para sintetizar uma aproximação unitária $\tilde{U}$ com erro $ \\ \\tilde{U} - U(t) \\ \ [spectral norm](xref:microsoft.quantum.concepts.matrix-advanced) A complexidade destes algoritmos depende muito fortemente de como uma descrição do interesse hamiltoniano é acessível por um computador quântico. Por exemplo, no pior dos casos, se $H$ agindo em $n$ qubits seriam fornecidos como uma lista de $2^n \times números de 2^n$ , um para cada elemento matricial, simplesmente ler os dados já exigiria tempo exponencial. Na melhor das hipóteses, pode-se assumir o acesso a uma caixa preta unitária que $O\ket{t}ket{\psi(0)}*ket{t}U(t)\ket{\psi(0)}} trivialmente resolve o problema. Nenhum destes modelos de entrada é particularmente interessante - o primeiro, uma vez que não é melhor do que abordagens clássicas, e este último como a caixa preta esconde a complexidade primitiva do portão da sua implementação, que poderia ser exponencial no número de qubits.

### <a name="descriptions-of-hamiltonians"></a>Descrições de Hamiltonians ###

Por conseguinte, são necessários pressupostos adicionais do formato da entrada. Deve ser alcançado um bom equilíbrio entre modelos de entrada suficientemente descritivos para abranger os hamiltonianos interessantes, como os de sistemas físicos realistas ou problemas computacionais interessantes, e modelos de entrada suficientemente restritivos para serem eficientemente implementáveis num computador quântico. Uma variedade de modelos de entrada não triviais podem ser encontrados na literatura, e variam de quantum a clássico. 

Como exemplos de modelos de entrada quântica, [a simulação hamiltoniana baseada em amostras](http://www.nature.com/articles/s41534-017-0013-7) pressupõe o acesso à caixa preta para operações quânticas que produzem cópias de uma matriz de densidade $\rho$, que são consideradas a $H$. No [modelo de acesso unitário](https://arxiv.org/abs/1202.5822) supõe-se que o Hamiltonian, em vez disso, se decompõe numa soma de unitários $$ \start{align} H & = \sum^{d-1} \_ {j=0} a \_ j\hat{U} \_ j, \end{align} $$ onde $a \_ j>0$ são coeficientes, e $\hat{U} \_ j$ são unidades. Presume-se então que se tem acesso a caixa preta ao oráculo unitário $V=\sum^{d-1} \_ {j=0}\ket{j}bra{j}\otimes \hat{U} \_ j$ que seleciona o desejado $\hat{U} \_ j$, e o oráculo $A\ket {0} =\sum^{d-1} \_ {j=0}\sqrt{a \_ j/\sum^{d-1} \_ {k=0}alpha \_ j}\ket{j}$ que criam um estado quântico codificando estes coeficientes. No caso de [simulação hamiltoniana escassa,](https://arxiv.org/abs/quant-ph/0301023)assume-se que o Hamiltonian é uma matriz escassa com apenas $d=\mathcal{O}(\text{polylog}(N)$ elemento não-zero em cada linha. Além disso, assume-se a existência de circuitos quânticos eficientes que desloquem a localização destes elementos não nulos, bem como os seus valores. A complexidade dos algoritmos de [simulação hamiltonianos](xref:microsoft.quantum.more-information) é avaliada em termos de número de consultas a estas caixas negras, e a complexidade primitiva do portão depende muito da dificuldade de implementar estas caixas negras.

> [!NOTE]
> A notação big-O é comumente usada para descrever a complexidade do escalonamento de algoritmos. Tendo em conta duas funções reais $f,g$, a expressão $g(x)=\mathcal{O}(f(x)$ significa que existe uma constante absolutamente positiva $x \_ 0, c>0$ tal que $g(x) \le c f(x)$ para todos os $x\ge x \_ 0$. 

Na maioria das aplicações práticas a implementar num computador quântico, estas caixas pretas devem ser eficientemente implementáveis, isto é, com portas quânticas primitivas $\mathcal{O}(\text{polylog}(N)$ portas quânticas primitivas. Mais fortemente, os hamiltonianos eficientemente simuladores devem ter uma descrição clássica suficientemente escassa. Numa dessas formulações, presume-se que o Hamiltonian se decompõe numa soma de partes hermitianas $$ \start{align} H & = \sum^{d-1}__j=0} H_j.
\end{align} $$ Além disso, presume-se que cada parte, uma $H \_ hamiltoniana j$, é fácil de simular. Isto significa que o $e^{-iH \_ j t}$ por qualquer momento $t$ pode ser implementado exatamente usando $\mathcal{O}(1)$ portões quânticos primitivos. Por exemplo, isto é verdade no caso especial em que cada $H \_ j$ são operadores locais da Pauli, o que significa que são de produtos tensores de operadores Pauli sem identidade que atuam em qubits espaciais próximos. Este modelo é particularmente aplicável a sistemas físicos com interação limitada e local, uma vez que o número de termos é $d=\mathcal{O}(\text{polylog}(N)$, e pode claramente ser escrito, ou seja, clássicamente descrito, em tempo polinomial.

> [!TIP]
> Os hamiltonianos que se decompõem numa soma de peças podem ser descritos usando a biblioteca de representação do gerador dinâmico. Para mais informações, consulte a secção de Representação do Gerador Dinâmico nas [estruturas de dados.](xref:microsoft.quantum.libraries.data-structures)

### <a name="simulation-algorithms"></a>Algoritmos de simulação ###

Um algoritmo de simulação quântica converte uma descrição dada de um Hamiltonian numa sequência de portões quânticos primitivos que, no seu conjunto, aproximam a evolução do tempo por dito Hamiltonian.

No caso especial em que o Hamiltonian se decompõe numa soma de partes hermitianas, a decomposição Trotter-Suzuki é um algoritmo particularmente simples e intuitivo para simular hamiltonianos que se decompõem numa soma de componentes eremitas. Por exemplo, um integrador de primeira ordem desta família aproxima -$ \start{align} U(t) & = \esquerda( e^{-iH \_ 0 t / r} e^{-iH \_ 1 t / r} \cdots e^{-iH \_ {d-1} t / r} \right)^{r} + \mathcal{O}(d^2 \max_j \\ H \_ j \\ [^2 t^2/r), \end{align} $$ usando um produto de $r d$ termos. 

> [!TIP]
> As aplicações do algoritmo de simulação Trotter-Suzuki estão cobertas nas amostras.
> Para o modelo Ising utilizando apenas as operações intrínsecas fornecidas por cada máquina-alvo, consulte a amostra [ **SimpleIsing** ](https://github.com/microsoft/Quantum/blob/master/samples/simulation/ising/simple).
> Para o modelo Ising utilizando a estrutura de controlo da biblioteca Trotter-Suzuki, consulte a amostra [ **isingTrotter** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/trotter-evolution).
> Para hidrogénio molecular utilizando a estrutura de controlo da biblioteca Trotter-Suzuki, consulte a amostra [ **de simulação H2** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line).

Em muitos casos, gostaríamos de implementar o algoritmo de simulação, mas não estamos interessados nos detalhes da sua implementação. Por exemplo, o integrador de segunda ordem aproxima -$ \start{align} U(t) & = \esquerda (e^{-iH \_ 0 t / 2r} e^{-iH \_ 1 t / 2r} \cdots e^{-iH \_ {d-1} t / 2r} e^{-iH \_ {d-1} t / 2r} \cdots e^{-iH \_ 1 t / 2r} e^{-iH \_ 0 t / 2r} \right)^{r} + \mathcal{O}(d^3 \max_j \\ / H \_ j \\ [^3 t^3/r^2), \end{align} $$ usando um produto de termos de $2º$ Encomendas maiores envolverão ainda mais termos e variantes otimizadas podem exigir encomendas altamente não triviais nos exponencials. Outros algoritmos avançados também podem envolver o uso de qubits de ancilla em passos intermédios. Assim, embalamos algoritmos de simulação no cânone como o tipo definido pelo utilizador

```qsharp
newtype SimulationAlgorithm = ((Double, EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl);
```

O primeiro parâmetro `Double` é o tempo de simulação, o segundo parâmetro , coberto na secção de `EvolutionGenerator` Representação do Gerador Dinâmico das estruturas [de dados](xref:microsoft.quantum.libraries.data-structures), é uma descrição clássica de um hamiltoniano independente do tempo embalado com instruções sobre como cada termo no Hamiltonian pode ser simulado por um circuito quântico. Os tipos deste formulário aproximam a operação unitária $e^{-iHt}$ no terceiro parâmetro `Qubit[]` , que é o registo que armazena o estado quântico do sistema simulado. Da mesma forma para o caso dependente do tempo, definimos um tipo definido pelo utilizador com um `EvolutionSchedule` tipo, que é uma descrição clássica de um Hamiltonian dependente do tempo.

```qsharp
newtype TimeDependentSimulationAlgorithm = ((Double, EvolutionSchedule, Qubit[]) => Unit : Adjoint, Controlled);
```

A título de exemplo, a decomposição Trotter-Suzuki pode ser chamada utilizando as seguintes funções canónicas, com parâmetros `trotterStepSize` que modificam a duração da simulação em cada exponencial, e `trotterOrder` para a ordem do integrador pretendido.

```qsharp
function TrotterSimulationAlgorithm(
    trotterStepSize : Double, 
    trotterOrder : Int) 
: SimulationAlgorithm {
    ...
}

function TimeDependentTrotterSimulationAlgorithm(
    trotterStepSize : Double, 
    trotterOrder : Int) 
: TimeDependentSimulationAlgorithm {
    ...
}
```

> [!TIP]
> As aplicações da biblioteca de simulação estão cobertas nas amostras. Para uma estimativa de fase no modelo Ising `SimulationAlgorithm` utilizando, consulte a amostra [ **IsingPhaseEstimation** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation).
> Para preparar o estado adiabático no modelo Ising `TimeDependentSimulationAlgorithm` utilizando, consulte a amostra [ **de AdiabaticIsing** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/adiabatic).


### <a name="adiabatic-state-preparation--phase-estimation"></a>Preparação do Estado Adiabático & estimativa da fase ###

Uma aplicação comum da simulação hamiltoniana é a preparação do estado adiabático. Aqui, um é fornecido com dois Hamiltonians $H \_ {\text{start}} e $H \_ {\text{end}},,$H. \_ Tipicamente, $H \_ {\text{start}} é escolhido de tal forma que $\ket{\psi(0)}$ é fácil de preparar a partir de um estado de base computacional $\ket{0\cdots 0}$. Ao interpolar entre estes Hamiltonianos no problema de simulação dependente do tempo suficientemente lentamente, é possível acabar, com elevada probabilidade, num estado terrestre do $H hamiltoniano final \_ {\text{end}}... Embora a preparação de boas aproximações aos estados terrestres de Hamiltonian possa prosseguir desta forma, invocando algoritmos de simulação hamiltoniano dependentes do tempo como uma subbroutina, outras abordagens conceptualmente diferentes, como o eigensolver quântico variacional, são possíveis.

Outra aplicação ubíqua na química quântica está estimando a energia do estado terrestre dos hamiltonianos que representam os passos intermédios da reação química. Tal esquema poderia, por exemplo, contar com a preparação do estado adiabático para criar o estado terrestre e, em seguida, incorporar uma simulação hamiltoniana independente do tempo como uma sub-rotina na caracterização da estimativa de fase para extrair esta energia com algum erro finito e probabilidade de sucesso. 

Abstrair algoritmos de simulação como os tipos definidos pelo utilizador `SimulationAlgorithm` e `TimeDependentSimulationAlgorithm` permitir-nos incorporar convenientemente a sua funcionalidade em algoritmos quânticos mais sofisticados. Isto motiva-nos a fazer o mesmo por estas sub-rotinas comumente utilizadas.

Assim, definimos a função conveniente

```qsharp
function InterpolatedEvolution(
        interpolationTime : Double, 
        evolutionGeneratorStart : EvolutionGenerator,
        evolutionGeneratorEnd : EvolutionGenerator,
        timeDependentSimulationAlgorithm : TimeDependentSimulationAlgorithm)
: (Qubit[] => Unit is Adj + Ctl) {
        ...
}
 
```

Isto devolve uma operação unitária que implementa todas as etapas da preparação do estado adiabático. O primeiro parâmetro `interpolatedTime` define o tempo sobre o qual interpolamos linearmente entre o início hamiltoniano descrito pelo segundo parâmetro e o final `evolutionGeneratorStart` Hamiltonian descrito pelo terceiro parâmetro `evolutionGeneratorEnd` . O quarto parâmetro `timeDependentSimulationAlgorithm` é onde se faz a escolha do algoritmo de simulação. Note que se `interpolatedTime` for tempo suficiente, um estado inicial permanece um estado terrestre instantâneo do Hamiltonian durante toda a duração da simulação dependente do tempo, e assim termina no estado térreo do hamiltoniano final.

Também definimos uma operação útil que executa automaticamente todos os passos de uma experiência típica de química quântica. Por exemplo, temos o seguinte, que devolve uma estimativa energética do estado produzido pela preparação do estado adiabático:

```qsharp
operation EstimateAdiabaticStateEnergy(
    nQubits : Int,
    statePrepUnitary : (Qubit[] => Unit),
    adiabaticUnitary : (Qubit[] => Unit),
    qpeUnitary: (Qubit[] => Unit is Adj + Ctl),
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double))
: Double {
...
}
```

`nQubits`é o número de qubits usados para codificar o estado quântico inicial. `statePrepUnitary`prepara o estado de partida a partir da base computacional $\ket{0\cdots 0}$. `adiabaticUnitary`é a operação unitária que implementa a preparação do estado adiabático, tal como produzido pela `InterpolatedEvolution` função. `qpeUnitary`é a operação unitária que é usada para realizar a estimativa de fase no estado quântico resultante. `phaseEstAlgorithm`é a nossa escolha de algoritmo de estimativa de fase.

> [!TIP]
> As aplicações de preparação do estado adiabático são abrangidas pelas amostras. Para o modelo Ising utilizando uma implementação manual da preparação do estado adiabático versus utilização da `AdiabaticEvolution` função, consulte a amostra [ **de AdiabaticIsing** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/adiabatic).
> Para a estimativa de fase e preparação do estado adiabático no modelo Ising, consulte a amostra [ **isingPhaseEstimation** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation).

> [!TIP]
> A [simulação do hidrogénio molecular](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line) é uma amostra interessante e breve. O modelo e os resultados experimentais reportados em [O'Malley et al.](https://arxiv.org/abs/1512.06860) apenas requer matrizes Pauli e toma o formulário $\hat H = g \_ {0} I \_ 0I \_ 1+g \_ 1{Z \_ 0}+g \_ 2{Z \_ 1}+g \_ 3{Z \_ 0}z \_ 1}+g \_ 4{Y \_ 0}{Y \_ 1}+g \_ 5{X \_ 0}{X \_ 1}.. Este é um Hamiltonian eficaz que requer apenas 2 qubits, onde as constantes $g$ são calculadas à distância $R$ entre os dois átomos de Hidrogénio. Utilizando funções canónicas, os Paulis são convertidos em unitários e depois evoluíram ao longo de curtos períodos de tempo usando a decomposição Trotter-Suzuki. Uma boa aproximação ao estado terrestre de $H_2$ pode ser criada sem a utilização de preparação do estado adiabático, pelo que a energia do estado do solo pode ser encontrada diretamente utilizando a estimativa de fase do cânone.

## <a name="shors-algorithm"></a>Algoritmo de Shor ##
O algoritmo de Shor continua a ser um dos desenvolvimentos mais significativos na computação quântica porque mostrou que os computadores quânticos poderiam ser usados para resolver problemas importantes, atualmente clássicos, intrigantes.
O algoritmo de Shor fornece uma forma rápida de factorar grandes números usando um computador quântico, um problema chamado *factoring*.
A segurança de muitos criptosistemas atuais baseia-se no pressuposto de que não existe algoritmo rápido para factoring.
Assim, o algoritmo de Shor teve um profundo impacto na forma como pensamos sobre a segurança num mundo pós-quântico.

O algoritmo de Shor pode ser considerado como um algoritmo híbrido.
O computador quântico é usado para executar uma tarefa computacionalmente difícil conhecida como descoberta de período.
Os resultados da constatação do período são então processados clássicamente para estimar os fatores.
Revemos estes dois passos abaixo.

### <a name="period-finding"></a>Constatação do período ###

Tendo visto como o quantum Fourier transforma e o trabalho de estimativa de fase (ver [algoritmos quânticos), podemos](xref:microsoft.quantum.libraries.standard.algorithms)usar estas ferramentas para resolver um problema computacional clássico chamado *period finding*.  Na secção seguinte, veremos como aplicar o período de visão ao factoring.

Tendo em conta dois inteiros $a$ e $N$, onde $a<N$, o objetivo da descoberta do período, também chamado de descoberta de encomendas, é encontrar a _encomenda_ $r$ de $a$ modulo $N$, onde $r$ é definido como o número inteiro menos positivo, tal que $a^r \equiv 1 \equiv 1 \text} mod }  

Para encontrar a encomenda usando um computador quântico, podemos usar o algoritmo de estimativa de fase aplicado ao seguinte operador unitário $U_a$: $$ U_a\ket{x} \equiv \ket{(ax)\text} mod }N} .$$ Os eigenvectors de $U_a$ são para o integer $s$ e $0 $$\ket{x_s} \equiv 1 / \sqrt{r} \soma \_ {k=0}^{r-1} e^{\frac{-2\pi i sk}}} \ket{a^k\text{ mod},$$ são _eigenstates_ of $U_a$.
Os valores eigenvalues de $U_a$ são $$ U \_ a \ket{x \_ s} = e^{2\pi i s / r} \ket{x \_ s} . $$

A estimativa de fases assim produz os eigenvalues $e^{2\pi i s / r}$ a partir do qual $r$ pode ser aprendido eficientemente usando [frações contínuas](https://en.wikipedia.org/wiki/Continued_fraction) de $s /r$.

O diagrama do circuito para a descoberta do período quântico é:

![Diagrama de circuito para a descoberta do período quântico](~/media/QPE.svg)

Aqui, os qubits de $2n$ são inicializados para $\ket {0} $ e $n$ qubits são inicializados para $\ket {1} $.
O leitor pode voltar a perguntar-se porque é que o registo quântico para deter os estados eigenes é inicializado para $\ket {1} $.
Como não se sabe a encomenda $r$ com antecedência, não podemos realmente preparar estados de $\ket{x_s}$ diretamente.
Felizmente, verifica-se que $1/\sqrt{r} \soma \_ {s=0}^{r-1} \ket{x \_ s} = \ket {1} $.
Não precisamos de preparar $\ket{x}$!
Podemos preparar um registo quântico de $n dólares qubits no estado $\ket {1} $. 

O circuito contém o QFT e vários portões controlados.
O portão QFT foi descrito [anteriormente](xref:microsoft.quantum.libraries.standard.algorithms).
O portão controlado $U_a$ mapeia $\ket{x}$ para $\ket{(ax)\text} mod} {1}

Para obter $(a^nx)\text{ mod} N$, podemos simplesmente aplicar $U_{a^n}$, onde calculamos $a^n \text} mod } N$ clássicamente para ligar ao circuito quântico.  
Os circuitos para alcançar tal aritmética modular foram descritos na [documentação aritmética quântica](./algorithms.md#arithmetic), especificamente exigimos um circuito de exponenciação modular para implementar as operações de $U controlada \_ {a^i}$ .

Embora o circuito acima corresponda à [Estimativa da Fase Quântica](xref:microsoft.quantum.characterization.quantumphaseestimation) e permita explicitamente a descoberta da ordem, podemos reduzir o número de qubits necessários. Podemos seguir o método de descoberta de encomendas de Beauregard, conforme descrito [na página 8 do arXiv:quant-ph/0205095v3,](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)ou usar uma das rotinas de estimativa de fase disponíveis na Microsoft.Quantum.Characterization. Por exemplo, [a Estimativa de Fase Robusta](xref:microsoft.quantum.characterization.robustphaseestimation) também usa um qubit extra.
 
### <a name="factoring"></a>Factoring ###
O objetivo do factoring é determinar os dois fatores primos do inteiro $N$, onde $N$ é um número de $n$-bit.  
O factoring consiste nos passos descritos abaixo. Os passos são divididos em três partes: uma rotina clássica de pré-processamento (1-4); uma rotina de computação quântica para encontrar a ordem de $a \text{ mod } N$ (5); e uma rotina clássica de pós-processamento para derivar os fatores primos da ordem (6-9).

A rotina clássica de pré-processamento consiste nos seguintes passos:
1. Se $N$ estiver em patamar, devolva o fator principal $2$.
2. Se $N=p^q$ por $p\geq1$, $q\geq2$, devolva o fator principal $p$.  Este passo é realizado clássicamente.
3. Escolha um número aleatório $a$ de modo que $1 < por < N-1$.
4. Se $\text{gcd}(a,N)>1$, devolva o fator principal $\text{gcd}(a,N)$. Este passo é calculado usando o algoritmo de Euclid.
Se nenhum fator principal foi devolvido, prosseguimos para a rotina quântica:
5. Ligue para o algoritmo de encontrar o período quântico para calcular a ordem $r$ de $a \text{{ mod } N$. Utilize $r$ na rotina clássica de pós-processamento para determinar os fatores primos:
6. Se $r$ for estranho, volte ao passo de pré-processamento (3).
7. Se $r$ estiver em patamar e $a^{r/2} = -1\text{ mod }N$, volte ao passo de pré-processamento (3).
8. Se $\text{gcd}(a^{r/2}+1, N)$ é um fator não trivial de $N$, devolva $\text{gcd}(a^{r/2}+1, N)$.
9. Se $\text{gcd}(a^{r/2}-1, N)$ é um fator não trivial de $N$, devolva $\text{gcd}(a^{r/2}-1, N)$.


O algoritmo de factoring é probabilístico: pode-se demonstrar que com probabilidade pelo menos metade do que $r$ será uniforme e $a^{r/2} \neq -1 \text{ mod}N$, produzindo assim um fator principal.  (Consulte o [papel original de Shor](https://doi.org/10.1109/SFCS.1994.365700) para mais detalhes, ou um dos textos básicos *de computação quântica* em para obter mais [informações).](xref:microsoft.quantum.more-information)
Se um fator principal não for devolvido, então simplesmente repetimos o algoritmo do passo (1).  Depois de $n tentativas de dólar, a probabilidade de todas as tentativas falharem é, no máximo, $2^{-n}$.
Assim, depois de repetir o algoritmo, um pequeno número de vezes o sucesso é virtualmente assegurado.
