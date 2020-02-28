---
title: Aplicações nas bibliotecas padrão Q#
description: Saiba mais sobre duas aplicações fundamentais na computação quântica - simulação hamiltoniana e algoritmo de pesquisa de Shor.
author: QuantumWriter
uid: microsoft.quantum.libraries.applications
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: b7c46b634c6d691c067c0dd995301395408c85ca
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907227"
---
# <a name="applications"></a>Aplicações #

## <a name="hamiltonian-simulation"></a>Simulação Hamiltoniana ##

A simulação dos sistemas quânticos é uma das aplicações mais excitantes da computação quântica.
Num computador clássico, a dificuldade de simular a mecânica quântica, em geral, escala com a dimensão $N$ da sua representação vetorial do estado.
À medida que esta representação cresce exponencialmente com o número de qubits de $n$ $N=2^n$, um traço também conhecido como [a maldição da dimensionalidade](xref:microsoft.quantum.concepts.multiple-qubits), a simulação quântica no hardware clássico é intratável.

No entanto, a situação pode ser muito diferente no hardware quântico. A variação mais comum da simulação quântica é chamada de problema de simulação hamiltoniana independente do tempo. Ali, é fornecida uma descrição do sistema Hamiltonian $H$, que é uma matriz hermitiana, e algum estado quântico inicial $\ket{\psi(0)}$ que é codificado em alguma base com qubits de $n$ num computador quântico. À medida que os estados quânticos em sistemas fechados evoluem sob a equação de Schrödinger $$ \begin{align} i\frac {d \ket{\psi(t)}}{d} & = H \ket{\psi(t)}, \end{align} $$ o objetivo é implementar o operador unitário de evolução do tempo $U(t)=={{-iHt}$ em algum momento fixo $t$ , onde $\ket{\psi(t)}=U(t)\ket{\psi(0)}}$ resolve a equação de Schrödinger.
Analogamente, o problema de simulação hamiltoniana dependente do tempo resolve a mesma equação, mas com $H(t)$ agora uma função do tempo.

A simulação hamiltoniana é um componente importante de muitos outros problemas de simulação quântica, e as soluções para o problema da simulação hamiltoniana são algoritmos que descrevem uma sequência de portas quânticas primitivas para sintetizar um aproximando unitário $\tilde{U}$ com erro $\\\tilde{U} - U(t)\\\le \epsilon$ na [norma espectral](xref:microsoft.quantum.concepts.matrix-advanced). A complexidade destes algoritmos depende muito de como uma descrição do hamiltoniano de interesse é tornada acessível por um computador quântico. Por exemplo, no pior dos casos, se $H$ agindo sobre qubits de $n$ fosse fornecido como uma lista de números de $2^n \times 2^n$, um para cada elemento matriz, simplesmente ler os dados já exigiria tempo exponencial. Na melhor das hipóteses, pode-se assumir o acesso a uma caixa preta unitária que $O\ket{t}\ket{\psi(0)}=\ket{t}U(t)ket{\psi(0)}$ resolve trivialmente o problema. Nenhum destes modelos de entrada é particularmente interessante -- o primeiro, uma vez que não é melhor do que as abordagens clássicas, e este último como a caixa preta esconde a complexidade primitiva do portão da sua implementação, que pode ser exponencial no número de qubits.

### <a name="descriptions-of-hamiltonians"></a>Descrições dos hamiltonianos ###

Por conseguinte, são necessários pressupostos adicionais do formato da entrada. Deve ser alcançado um bom equilíbrio entre os modelos de entrada suficientemente descritivos para abranger hamiltonianos interessantes, tais como os de sistemas físicos realistas ou problemas computacionais interessantes, e modelos de entrada suficientemente restritivos ser eficientemente implementável num computador quântico. Uma variedade de modelos de entrada não triviais pode ser encontrado na literatura, e variam de quantum a clássico. 

Como exemplos de modelos de entrada quântica, a [simulação hamiltoniana baseada em amostras](http://www.nature.com/articles/s41534-017-0013-7) pressupõe o acesso à caixa preta a operações quânticas que produzem cópias de uma matriz de densidade $\rho$, que são tomadas como a Hamiltonian $H$. No modelo de [acesso unitário](https://arxiv.org/abs/1202.5822) supõe-se que o Hamiltonian em vez disso se decompõe numa soma de unitários $$ \start{align} H & = \sum^{d-1}\_{j=0} a\_j \hat{U}\_j, \end{align} $$ onde $a\_j>0$ são coeficientes, e $\hat{U}\_j$ são unitaries. Presume-se então que se tem acesso à caixa preta ao oráculo unitário $V=\sum^{d-1}\_{j=0}\ket{j}\bra{j}\otimes \hat{U}\_j$ que seleciona o desejado $\hat{U}\_j$, e o oráculo $A\ket{0}=\sum^{d-1}\_{j=0}\sqrt{a\_j/\sum^{d-1}\_{k=0}\alfa\_j}\ket{j}$ que criam um estado quântico codificando estes coeficientes. No caso de [escassa simulação hamiltoniana,](https://arxiv.org/abs/quant-ph/0301023)supõe-se que o Hamiltonian é uma matriz escassa com apenas $d=\mathcal{O}(/text{polylog}(N)$ não-zero elemento em cada linha. Além disso, assume-se a existência de circuitos quânticos eficientes que produzem a localização destes elementos não zero, bem como os seus valores. A complexidade dos algoritmos de [simulação hamiltoniana](xref:microsoft.quantum.more-information) é avaliada em termos de número de consultas a estas caixas negras, e a complexidade primitiva do portão depende muito da dificuldade de implementar estas caixas negras.

> [!NOTE]
> A notação big-O é comumente usada para descrever a complexidade da escala de algoritmos. Tendo em conta duas funções reais $f,g$, a expressão $g(x)=\mathcal{O}(f(x))$ significa que existe uma constante absolutamente positiva $x\_0, c>0$ de tal forma que $g(x) \le c f(x)$ para todos os $x\ge x\_0$. 

Na maioria das aplicações práticas a implementar num computador quântico, estas caixas pretas devem ser eficientemente implementáveis, isto é, com $\mathcal{O}(\text{polylog}(N)$ portas quânticas primitivas. Mais fortemente, os hamiltonianos eficientemente simulados devem ter uma descrição clássica suficientemente escassa. Numa dessas formulações, presume-se que o Hamiltonian decompõe-se numa soma de partes hermitianas $$ \start{align} H & = \sum^{d-1}_{j=0} H_j.
\end{align} $$ Além disso, presume-se que cada parte, um Hamiltonian $H\_j$, é fácil de simular. Isto significa que o $e unitário^{-iH\_j t}$ por qualquer momento $t$ pode ser implementado exatamente usando $\mathcal{O}(1)$ portas quânticas primitivas. Por exemplo, isto é verdade no caso especial em que cada $H\_j$ são operadores pauli locais, o que significa que são de produtos tensores de $\mathcal{O}(1)$ operadores pauli não-identitários que agem em qubits espacialmente fechados. Este modelo é particularmente aplicável aos sistemas físicos com interação limitada e local, uma vez que o número de termos é $d=\mathcal{O}(\text{polylog}(N)$, e pode ser claramente escrito, ou seja, descrito clássicamente, em tempo polinómio.

> [!TIP]
> Os hamiltonianos que se decompõem numa soma de peças podem ser descritos usando a biblioteca Dynamical Generator Representation. Para mais informações, consulte a secção de Representação dinâmica do gerador nas estruturas de [dados](xref:microsoft.quantum.libraries.data-structures).

### <a name="simulation-algorithms"></a>Algoritmos de Simulação ###

Um algoritmo de simulação quântica converte uma descrição de um Hamiltonian numa sequência de portas quânticas primitivas que, no seu conjunto, aproximam-se da evolução do tempo por parte de Hamiltonian.

No caso especial em que o Hamiltoniano se decompõe numa soma de partes hermitias, a decomposição Trotter-Suzuki é um algoritmo particularmente simples e intuitivo para simular hamiltonianos que se decompõem numa soma de componentes hermitianos. Por exemplo, um integrador de primeira ordem desta família aproxima-se de $$ \begin{ U(t) & = \left( e^{-iH\_0 t / r} e^{-iH\_1 t / r} \cdots e^{-iH\_{d-1} t / r} \right){r} + \mathcal{O}(d^\\max_j 2 H\_j\\^2 t^2/r), \end{align} $$ usando um produto de termos $r d$. 

> [!TIP]
> As aplicações do algoritmo de simulação Trotter-Suzuki estão cobertas nas amostras.
> Para o modelo Ising utilizando apenas as operações intrínsecas fornecidas por cada máquina-alvo, consulte a amostra [ **Simpleising** ](https://github.com/microsoft/Quantum/blob/master/samples/simulation/ising/simple).
> Para o modelo Ising utilizando a estrutura de controlo da biblioteca Trotter-Suzuki, consulte a amostra [ **IsingTrotter** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/trotter-evolution).
> Para hidrogénio molecular utilizando a estrutura de controlo da biblioteca Trotter-Suzuki, consulte a amostra de [ **simulação H2** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line).

Em muitos casos, gostaríamos de implementar o algoritmo de simulação, mas não estamos interessados nos detalhes da sua implementação. Por exemplo, o integrador de segunda ordem aproxima-se de $$ \begin{align} U(t) & = \left( e^{-iH\_0 t / 2r} e^{-iH\_1 t / 2r} \cdots e^{-iH\_{d-1} t / 2r} e^{-iH\_{d-d-1} t / 2r} \cdots e^{-iH\_1 t / 2r} e^{-iH\_0 t / 2r} \right}{r} + \mathcal{O}(d^3 \max_j\\/ H\_j\\^3 t^3/r^2), \end{align} $$ usando um produto de termos de $2º$. Encomendas maiores envolverão ainda mais termos e variantes otimizadas podem exigir encomendas altamente não triviais sobre os exponenciais. Outros algoritmos avançados também podem envolver o uso de qubits acessórias em passos intermédios. Assim, embalamos algoritmos de simulação no cânion como o tipo definido pelo utilizador

```qsharp
newtype SimulationAlgorithm = ((Double, EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl);
```

O primeiro parâmetro `Double` é o tempo de simulação, o segundo parâmetro `EvolutionGenerator`, coberto na secção dinâmica de representação do gerador de estruturas de [dados,](xref:microsoft.quantum.libraries.data-structures)é uma descrição clássica de um Hamiltonian independente do tempo embalado com instruções sobre como cada termo no Hamiltonian pode ser simulado por um circuito quântico. Os tipos desta forma aproximam-se da operação unitária $e^{-iHt}$ no terceiro parâmetro `Qubit[]`, que é o registo que armazena o estado quântico do sistema simulado. Da mesma forma para o caso dependente do tempo, definimos um tipo definido pelo utilizador com um tipo `EvolutionSchedule`, que é uma descrição clássica de um Hamiltonian dependente do tempo.

```qsharp
newtype TimeDependentSimulationAlgorithm = ((Double, EvolutionSchedule, Qubit[]) => Unit : Adjoint, Controlled);
```

Como exemplo, a decomposição Trotter-Suzuki pode ser chamada usando as seguintes funções canon, com parâmetros `trotterStepSize` modificando a duração da simulação em cada exponencial, e `trotterOrder` para a ordem do integrador desejado.

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
> As aplicações da biblioteca de simulação estão cobertas nas amostras. Para obter uma estimativa de fase no modelo Ising utilizando `SimulationAlgorithm`, consulte a amostra de estimativa de [ **fase de isingphase .** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation)
> Para a preparação do estado adiabaático no modelo Ising utilizando `TimeDependentSimulationAlgorithm`, consulte a amostra de [ **AdiabaticIsing** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/adiabatic).


### <a name="adiabatic-state-preparation--phase-estimation"></a>Preparação e Estimativa do Estado Adiabatic ###

Uma aplicação comum da simulação hamiltoniana é a preparação do estado adiabático. Aqui, um é fornecido com dois Hamiltonians $H\_{\text{start}}$ e $H\_{\text{end}}$, e um estado quântico $\ket{\psi(0)}} que é um estado de base do início Hamiltonian $H\_{\text{start}}$. Tipicamente, $H\_{\text{start}}$ é escolhido de tal forma que $\ket{\psi(0)}$ é fácil de preparar a partir de um estado computacional $\ket{0\cdots 0}$. Ao interpolar entre estes Hamiltonians no problema de simulação dependente do tempo suficientemente lentamente, é possível acabar, com alta probabilidade, num estado de terra do último $H Hamiltonian\_{\text{end}}$. Embora preparar boas aproximações aos estados terrestres hamiltonianos poderia prosseguir desta forma, invocando algoritmos de simulação hamiltonianos dependentes do tempo como uma subrotina, outras abordagens conceptualmente diferentes, como o quântico variacional eigensolver são possíveis.

Outra aplicação ubíqua na química quântica está a estimar a energia do estado terrestre dos hamiltonianos que representam os passos intermédios da reação química. Tal esquema poderia, por exemplo, contar com a preparação do Estado adiabático para criar o estado terrestre, e, em seguida, incorporar a simulação hamiltoniana independente do tempo como uma subrotina na caracterização de estimativa de fase para extrair esta energia com algum erro finito e probabilidade de sucesso. 

Resumindo algoritmos de simulação à medida que os tipos definidos pelo utilizador `SimulationAlgorithm` e `TimeDependentSimulationAlgorithm` permitem incorporar convenientemente a sua funcionalidade em algoritmos quânticos mais sofisticados. Isto motiva-nos a fazer o mesmo por estas subrotinas comumente usadas.

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

Isto devolve uma operação unitária que implementa todas as etapas de preparação do Estado adiabático. O primeiro parâmetro `interpolatedTime` define o tempo sobre o qual interpolamos linearmente entre o início que Hamiltonian descrito pelo segundo parâmetro `evolutionGeneratorStart` e o final hamiltoniano descrito pelo terceiro parâmetro `evolutionGeneratorEnd`. O quarto parâmetro `timeDependentSimulationAlgorithm` é onde se faz a escolha do algoritmo de simulação. Note-se que se `interpolatedTime` for tempo suficiente, um estado de terra inicial permanece um estado terrestre instantâneo do Hamiltonian durante toda a duração da simulação dependente do tempo, e assim termina no estado terrestre do final Hamiltonian.

Também definimos uma operação útil que executa automaticamente todos os passos de uma experiência típica de química quântica. Por exemplo, temos o seguinte, que devolve uma estimativa energética do Estado produzida pela preparação do Estado adiabático:

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

`nQubits` é o número de qubits usados para codificar o estado quântico inicial. `statePrepUnitary` prepara o estado de partida a partir da base computacional $\ket{0\cdots 0}$. `adiabaticUnitary` é a operação unitária que implementa a preparação do Estado adiabático, como produzida pela função `InterpolatedEvolution`. `qpeUnitary` é a operação unitária que é usada para realizar estimativas de fase no estado quântico resultante. `phaseEstAlgorithm` é a nossa escolha de algoritmo de estimativa de fase.

> [!TIP]
> As aplicações de preparação do Estado adiabático estão cobertas nas amostras. Para o modelo Ising utilizando uma implementação manual da preparação do estado adiabático versus utilização da função `AdiabaticEvolution`, consulte a amostra [ **adiabaticIsing** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/adiabatic).
> Para a estimativa de fasee e preparação do estado adiabaático no modelo Ising, consulte a amostra [ **isingPhaseEstimation** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation).

> [!TIP]
> A [simulação do hidrogénio molecular](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line) é uma amostra interessante e breve. O modelo e os resultados experimentais relatados em [O'Malley et. al.](https://arxiv.org/abs/1512.06860) apenas requer matrizes Pauli e assume a forma $\hat H = g\_{0}eu\_0I\_1+g\_1{Z\_0}+g\_2{Z\_1}+g\_3{Z\_0}{Z\_1}+g\_4{Y\_0}{Y\_1}+g\_5{X\_0}0{X\_1}$. Este é um Hamiltonian eficaz que requer apenas 2 qubits, onde as constantes $g$ são calculadas à distância $R$ entre os dois átomos de Hidrogénio. Utilizando funções canonárias, os Paulis são convertidos em unitários e depois evoluíram durante curtos períodos de tempo usando a decomposição Trotter-Suzuki. Uma boa aproximação ao estado de terra $H_2$ pode ser criada sem a preparação do estado adiabático, e assim a energia do estado terrestre pode ser encontrada diretamente utilizando a estimativa de fase do cânone.

## <a name="shors-algorithm"></a>Algoritmo de Shor ##
O algoritmo de Shor continua a ser um dos desenvolvimentos mais significativos na computação quântica porque mostrou que os computadores quânticos poderiam ser usados para resolver problemas importantes, atualmente clássicamente difíceis.
O algoritmo de Shor fornece uma maneira rápida de fatorizar grandes números usando um computador quântico, um problema chamado *factoring*.
A segurança de muitos criptosistemas atuais baseia-se no pressuposto de que não existe algoritmo rápido para factoring.
Assim, o algoritmo de Shor teve um profundo impacto na forma como pensamos sobre a segurança num mundo pós-quântico.

O algoritmo de Shor pode ser considerado um algoritmo híbrido.
O computador quântico é usado para executar uma tarefa computacionalmente difícil conhecida como descoberta de período.
Os resultados da constatação do período são então processados clássicamente para estimar os fatores.
Revemos estes dois passos abaixo.

### <a name="period-finding"></a>Constatação do período ###

Tendo visto como o quantum Fourier transforma e calcula a fase (ver [algoritmos quânticos),](xref:microsoft.quantum.libraries.standard.algorithms)podemos usar estas ferramentas para resolver um problema computacional clássico chamado de descoberta de *períodos.*  Na próxima secção, veremos como aplicar a constatação do período à ponderação.

Tendo em conta dois inteiros $a$ e $N$, onde $a<N$, o objetivo de encontrar o período, também chamado de conclusão de encomendas, é encontrar a _ordem_ $r$ de $a$ modulo $N$, onde $r$ é definido como o inteiro menos positivo que $a^r \equiv 1 \text{ mod } N$.  

Para encontrar a encomenda usando um computador quântico, podemos usar o algoritmo de estimativa de fase aplicado ao seguinte operador unitário $U_a$: $U_a\ket{x} \equiv \ket {(ax)\text{ mod }N} .$$ Os eigenvectores de $U_a$ são para $s de suportes e $0\leq s \leq r - 1$, $$\ket{x_s} \equiv 1 / \sqrt{r} \sum\_{k=0}^{r-1} e^{{frac{-2\pi i sk}{{r}} \ket{a^k\text{ mod }N},$$ são _eigenstates_ de $U_a$.
Os valores eigen de $U_a$ são $$ U\_um \ket{x\_s} = e^2\pi i s / r} \ket{x\_s} . $$

A estimativa de fase produz assim os valores eigen$e^{2\pi i s/ r}$ a partir do qual $r$ pode ser aprendido eficientemente usando [frações contínuas](https://en.wikipedia.org/wiki/Continued_fraction) de $s/r$.

O diagrama de circuito para a descoberta do período quântico é:

![Diagrama de circuito para a descoberta do período quântico](./../../media/QPE.svg)

Aqui os qubits de $2n$ são inicializados para $\ket{0}$ e $n$ qubits são inicializados para $\ket{1}$.
O leitor pode voltar a perguntar-se porque é que o registo quântico para deter os eigenstates é inicializado para $\ket{1}$.
Como não se sabe a encomenda $r$ com antecedência, não podemos realmente preparar os estados de x_s x_s}$ de $\ket.
Felizmente, verifica-se que $1/\sqrt{r} \sum\_{s=0}^{r-1} \ket{x\_s} = \ket{1}$.
Não precisamos de preparar $\ket{x}$!
Podemos preparar um registo quântico de qubits de $n$ no Estado $\ket{1}$. 

O circuito contém o QFT e vários portões controlados.
O portão QFT foi descrito [anteriormente](xref:microsoft.quantum.libraries.standard.algorithms).
O portão controlado-$U_a$ mapeia $\ket{x}$ para $\ket{(ax)\text{ mod } N}$ se o qubit de controlo for $\ket{1}$, e mapeia $\ket{x}$ para $\ket{x}$ de outra forma.

Para conseguir $(a^nx)\text { mod } N$, podemos simplesmente aplicar $U controlado_{a^n}$, onde calculamos $a^n \text{ mod } N$ clássicamente para ligar ao circuito quântico.  
Os circuitos para alcançar tal aritmética modular foram descritos na [documentação aritmética quântica,](./algorithms.md#arithmetic)especificamente exigimos um circuito de exponenciação modular para implementar as operações de $U controladas\_{a^i}$.

Embora o circuito acima corresponda à Estimativa de [Fase Quântica](xref:microsoft.quantum.characterization.quantumphaseestimation) e permita explicitamente a descoberta da ordem, podemos reduzir o número de qubits necessários. Podemos seguir o método de descoberta de encomendas de Beauregard como descrito [na página 8 do arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8), ou usar uma das rotinas de estimativa de fase disponíveis na Microsoft.Quantum.Characterization. Por exemplo, [a Robust Phase Estimation](xref:microsoft.quantum.characterization.robustphaseestimation) também utiliza um qubit extra.
 
### <a name="factoring"></a>Factoring ###
O objetivo de factoring é determinar os dois fatores principais do inteiro $N$, onde $N$ é um número $n$bit.  
Factoring consiste nos passos descritos abaixo. Os passos dividem-se em três partes: uma rotina clássica de pré-processamento (1-4); uma rotina de computação quântica para encontrar a ordem de $a \text{ mod } N$ (5); e uma rotina clássica de pós-processamento para derivar os fatores primos da ordem (6-9).

A rotina clássica de pré-processamento consiste nos seguintes passos:
1. Se $N$ é igual, devolva o fator principal $2$.
2. Se $N=p^q$ por $p\geq1$, $q\geq2$, devolva o fator principal $p$.  Este passo é realizado clássicamente.
3. Escolha um número aleatório $a$ de tal forma que $1 < a < N-1$.
4. Se $\text{gcd}(a,N)>1$, devolva o fator principal $\text{gcd}(a,N)$. Este passo é calculado usando o algoritmo de Euclid.
Se nenhum fator principal foi devolvido, procedemos à rotina quântica:
5. Ligue para o algoritmo de encontrar o período quântico para calcular a ordem $r$ de $a \text{ mod } N$. Use $r$ na rotina clássica de pós-processamento para determinar os fatores principais:
6. Se $r$ for estranho, volte ao passo de pré-processamento (3).
7. Se $r$ for equilibrado e $a^{r/2} = -1\text{ mod }N$, volte ao passo de pré-processamento (3).
8. Se $\text{gcd}(a^{r/2}+1, N)$ é um fator não trivial de $N$, devolver $\text{gcd}(a{r/2}+1, N)$.
9. Se $\text{gcd}(a^{r/2}-1, N)$ é um fator não trivial de $N$, devolver $\text{gcd}(a{r/2}-1, N)$.


O algoritmo de factoring é probabilístico: pode ser demonstrado que, com probabilidade, pelo menos metade que $r$ será uniforme e $a^{r/2} \neq -1 \text { mod }N$, produzindo assim um fator primordial.  (Consulte o [documento original de Shor](https://doi.org/10.1109/SFCS.1994.365700) para obter mais detalhes, ou um dos textos básicos de *computação quântica* em For more [information).](xref:microsoft.quantum.more-information)
Se um fator principal não for devolvido, então simplesmente repetimos o algoritmo do passo (1).  Depois de $n$ tenta, a probabilidade de todas as tentativas terem falhado é no máximo $2^{-n}$.
Assim, depois de repetir o algoritmo, um pequeno número de vezes o sucesso é praticamente assegurado.
