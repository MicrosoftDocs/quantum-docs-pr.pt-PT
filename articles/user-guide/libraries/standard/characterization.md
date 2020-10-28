---
title: Caracterização quântica e estatísticas
description: Saiba como as estatísticas de medição das estimativas de fase são usadas para estimar os valores dos resultados na programação quântica.
author: bradben
uid: microsoft.quantum.libraries.characterization
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 51e7b3bcf4402a4d0ba5647643f284e9f10c3bb3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692147"
---
# <a name="quantum-characterization-and-statistics"></a>Caracterização quântica e Estatística #

É fundamental ser capaz de caracterizar os efeitos das operações de forma a desenvolver algoritmos quânticos úteis.
Isto é um desafio porque cada medição de um sistema quântico produz, no máximo, um pouco de informação.
Para aprender um valor eigenvalue, muito menos um estado quântico, os resultados de muitas medições devem ser costurados em conjunto para que o utilizador possa recolher as muitas informações necessárias para representar estes conceitos.
Os Estados quânticos são especialmente irritantes porque o [teorema da não clonagem](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) afirma que não há forma de aprender um estado quântico arbitrário a partir de uma única cópia do Estado, porque fazê-lo permitir-lhe-ia fazer cópias do Estado.
Esta obfuscação do estado quântico do utilizador reflete-se no facto de Q# que não expõe nem sequer define o que *é* um Estado aos programas quânticos.
Assim, abordamos a caracterização quântica, tratando as operações e os Estados como caixa negra; esta abordagem partilha muito em comum com a prática experimental de caracterização quântica, verificação e validação (QCVV).

A caracterização é distinta de muitas das outras bibliotecas discutidas anteriormente.
O objetivo aqui é menos aprender informação clássica sobre o sistema, em vez de realizar uma transformação unitária em um vetor de estado.
Estas bibliotecas devem, portanto, misturar o processamento de informação clássica e quântica.


## <a name="iterative-phase-estimation"></a>Estimativa da fase iterativa ##

Ver a programação quântica em termos de caracterização quântica sugere uma alternativa útil à estimativa da fase quântica.
Isto é, em vez de preparar um registo de $n$-qubit para conter uma representação binária da fase como na estimativa da fase quântica, podemos ver a estimativa de fase como o processo pelo qual um agente *clássico* aprende propriedades de um sistema quântico através de medições.
Procedemos como no caso quântico, usando o recuo de fase para transformar as aplicações de uma operação de caixa preta em rotações por um ângulo desconhecido, mas mediremos o qubit de ancilla que giramos em cada passo imediatamente após a rotação.
Isto tem a vantagem de que só precisamos de um único qubit adicional para realizar o recuo de fase descrito no caso quântico, pois então aprendemos a fase a partir dos resultados da medição em cada passo de forma iterativa.  
Cada um dos métodos propostos abaixo utiliza uma estratégia diferente para conceber experiências e diferentes métodos de processamento de dados para aprender a fase.  Cada um deles tem uma vantagem única que vai desde ter limites de erro rigorosos, até às capacidades de incorporar informações prévias, tolerar erros ou executar em computadores clássicos limitados pela memória.

Ao discutir a estimativa da fase iterativa, consideraremos um $U$ unitário dado como uma operação de caixa preta.
Conforme descrito na secção sobre oráculos em [estruturas de dados,](xref:microsoft.quantum.libraries.data-structures)os Q# modelos canónicos tais operações pelo <xref:Microsoft.Quantum.Oracles.DiscreteOracle> tipo definido pelo utilizador, definidos pelo tipo tuple `((Int, Qubit[]) => Unit : Adjoint, Controlled)` .
Concretamente, `U : DiscreteOracle` se, em seguida, `U(m)` implementar $U^m$ para `m : Int` .

Com esta definição em vigor, cada passo da estimativa de fase iterativa prossegue preparando um qubit auxiliar no estado de $\ket{+}, juntamente com o estado inicial $\ket{\phi}$ que assumimos ser um [eigenvector](xref:microsoft.quantum.concepts.matrix-advanced) de $U(m)$, i.e. $U(m)\ket{\phi}= e^{im\phi\phi}}  
Em seguida, é utilizada uma aplicação controlada `U(m)` que prepara o estado $\left(R \_ 1(m\phi) \ket{+}\right)\ket{\phi}$.
Tal como no caso quântico, o efeito de uma aplicação controlada do oráculo `U(m)` é precisamente o mesmo que o efeito da aplicação de $R_1$ para a fase desconhecida em $\ket{+}$,de modo que podemos descrever os efeitos de $U$ desta forma mais simples.
Opcionalmente, o algoritmo roda então o qubit de controlo aplicando $R_1 (-m\theta)$ para obter um estado $\ket{\psi}=\left(R \_ 1 (m [\phi-\theta]) \ket{+}\right)\ket{\phi}$.$.$.$.$.\ket{\phi}$.$.$.$.\ket{\phi}$.$..\ket{\phi}$.$..\\$..\ket{\phi}$.$...\\ket{\phi}$.$.$..\\ket{\phi}$.$.$.\\ket{\phi}$.$.$.$.$.$.\ket{\phi}$.$.$..\ket{\phi}$.$.$..$.$.\ket{\phi}$.
O qubit auxiliar utilizado como controlo `U(m)` é então medido na base $X$ para obter um único clássico `Result` .

Neste ponto, a reconstrução da fase a partir dos `Result` valores obtidos através da estimativa de fase iterativa é um problema clássico de inferência estatística.
Encontrar o valor de $m$ que maximiza a informação obtida, dado um método de inferência fixa, é simplesmente um problema nas estatísticas.
Salientamos isto descrevendo brevemente a estimativa da fase iterativa a nível teórico no formalismo de estimativa de parâmetros bayesiano antes de continuar a descrever os algoritmos estatísticos fornecidos no Q# cânone para resolver este problema clássico de inferência.

### <a name="iterative-phase-estimation-without-eigenstates"></a>Estimativa de fase iterativa sem Estados-Eigen ###

Se for fornecido um estado de entrada que não seja um eigenstate, ou seja, se $U(m)\ket{\phi \_ j} = e^{im\phi \_ j}} então o processo de estimativa de fase não deterministicamente guia o estado quântico em direção a um único estado de eigenação energética.  O eigenstate a que, em última análise, converge é o eigenstate que é mais provável produzir o observado `Result` .

Especificamente, um único passo de PE executa a seguinte transformação não unitária num estado \start{align} \sum_j \sqrt{\Pr(\phi \_ j)} \ket{\phi \_ j} \mapsto \sum \_ j\frac{\sqrt{\Pr\\Pr\\\\mapesto \soma j\frac{\sqrt{\Pr\\Pr\\\mapesto \soma j\frac{\sqrt{\Pr\\Pr\\\mapsto \soma j\frac{\sqrt{\Pr\\Pr(\Pr\\mapas para \soma j\frac{\sqrt{\Pr\Pr(\Pr\Pr\\\mapas para \soma j\frac{\sqrt{\Pr\\\mapear \soma j\frac{\sqrt{\Pr\\Pr\\\mapsto \soma j\phi \_ j)}}\sqrt{\Pr(\text{Result}/\phi \_ j)}}}}}} \_ \_ \_ \_
\end{align} À medida que este processo é iterado sobre `Result` vários valores, os estados eigenstates que não têm valores máximos de $\prod_k\Pr(\text{Result} \_ k/\phi \_ j)$ serão exponencialmente suprimidos.
Como resultado, o processo de inferência tenderá a convergir para estados com um único eigenvalue se as experiências forem escolhidas corretamente.

O teorema de Bayes sugere ainda que o estado que resulta da estimativa da fase seja escrito no formulário \start{align} \frac{\sqrt{\Pr(\phi \_ j)}}\sqrt{\Pr(\text{Result}/\phi \_ j)}\ket{\phi\phi\phi\phi\phi\phi\phi\phi\phi\phi\phi\phi\phi\phi\phi\phi\phi\phi\phi\phi\phi\phi\phi\phi\phi\phi\phi\phi\phi\phi\phi\phi\phi\phi\phi\\phi\phi\\phi\phi\phi\phi\phi\phi\phi\phi\phi\phi\phi\phi \_ j}}{\sqrt{\Pr(\phi \_ j)\sum \_ j \Pr (\text{Result}/phi \_ j)}}}=}}}=}}=sum_j \_ \sqrt{\Pr\text{result}}} \ket{\phi j}} \ket{\phi \_ j}}
\end{align} Aqui $\Pr(\phi \_ j/\text{Result})$ pode ser interpretado como a probabilidade que se atribuiria a cada hipótese sobre os estados eigenados dado:

1. conhecimento do estado quântico antes da medição,
2. conhecimento dos estados eigen de $U$ e,
3. conhecimento dos valores eigen de $U$.

Aprender estas três coisas é muitas vezes exponencialmente difícil num computador clássico.
A utilidade da estimativa de fase surge, em grande medida, do facto de poder realizar uma tarefa de aprendizagem quântica sem conhecer nenhuma delas.
A estimativa de fase por esta razão aparece dentro de uma série de algoritmos quânticos que fornecem acelerações exponenais.

### <a name="bayesian-phase-estimation"></a>Estimativa da Fase Bayesiana ###

> [!TIP]
> Para obter mais detalhes sobre a estimativa da fase bayesiana na prática, consulte a amostra [**phaseEstimation.**](https://github.com/microsoft/Quantum/tree/main/samples/characterization/phase-estimation)

A ideia da estimativa da fase bayesiana é simples.
Recolhe estatísticas de medição do protocolo de estimativa de fase e, em seguida, processa os resultados usando a inferência bayesiana e fornece uma estimativa do parâmetro.
Este processamento dá-lhe uma estimativa do valor do eigen, bem como a incerteza nessa estimativa.
Também lhe permite realizar experiências adaptativas e utilizar informações prévias.
O principal inconveniente dos métodos é que é computacionalmente exigente.

Para entender como funciona este processo de inferência bayesiana, considere o caso do processamento de um único `Zero` resultado.
Note que $X = \ket{+}\bra{+} - \ket {-} \bra {-} $, tal que $\ket{+}} é o único eigenstate positivo de $X$ correspondente a `Zero` .
A probabilidade de observar `Zero` uma [ `PauliX` medição](xref:microsoft.quantum.concepts.pauli) no primeiro qubit dado um estado de entrada $\ket{\psi}\ket}\ket{\phi}$ é assim \start{equação} \Pr(\texttt{Zero} / \psi) = \braket{+ \ \psi} \right/2.
\end{equation} No caso de estimativa de fase iterativa, temos que $\ket{\psi} = R_1(m [\phi-\theta]) \ket{+}$,, de modo que \start{align} \Pr(\texttt{Zero} / \phi; m,\theta) & = \/ \braket{+ R_1[m[\phi-\theta]) +} \direita/^2 \\ \\ & = \à esquerda \ frac12 \bra {0} + \bra {1} \bra \direita) \ket {0} + e^{i m [\phi-\theta]} \ket {1} \right) \right/2 \\ \\ & = \esquerda \ frac \ \frac {1 + e^{i m [\phi-\theta]}} {2} \direita /^2 \\ \\ & = \cos^2 (m [\phi-\theta] / 2) \tag{★} \label{eq:phase-est-probabilidade}.
\end{align} Isto é, a estimativa da fase iterativa consiste em aprender a frequência de oscilação de uma função sinusoidal, dada a capacidade de lançar uma moeda com um viés dado por esse sinusoid.
Seguindo a terminologia clássica tradicional, chamamos $\eqref{eq:phase-est-probabilidade}$ a *função de probabilidade* para a estimativa da fase iterativa.

Tendo observado uma `Result` função de probabilidade de estimativa de fase iterativa, podemos então usar a regra de Bayes para prescrever o que devemos acreditar que a fase está a seguir essa observação.
Concretamente, \start{equação} \Pr(\phi [ d) = \frac{\Pr(d \ \phi) \Pr(\phi)}}\\Pr\phi\ \Pr(\phi){\mathrm d}\phi} \Pr(\phi), \end{equação $d} \\ \texttt{One} \\ }$ é um `Result` , e onde $\Pr(\phi)$ descreve as nossas crenças anteriores sobre $\phi$.
Isto torna então explícita a natureza iterativa da estimativa de fase iterativa, uma vez que a distribuição posterior $\Pr(\phi [ d)$ descreve as nossas crenças imediatamente antes da nossa observação do próximo `Result` .

Em qualquer ponto durante este procedimento, podemos reportar a fase $\hat{\phi}$ inferida pelo controlador clássico como \start{equação} \hat{\phi} \mathrel{:=} \expect[\phi [ text{data}] = \int \\\\Pr\\\\text{text{data}) {\mathrm d\phi, \end{equation} where $\text{data}$ representa todo o registo de todos os `Result` valores obtidos.

A inferência bayesiana exata é, na prática, intratável.
Para ver esta imagem, queremos aprender uma variável $n$-bit $x$.
A distribuição prévia $\Pr(x)$ tem suporte superior a $2^n$ valores hipotéticos de $x$.
Isto significa que se precisarmos de uma estimativa muito precisa de $x$ então a estimativa da fase bayesiana pode precisar de memória proibitiva e tempo de processamento.
Embora para algumas aplicações, como a simulação quântica, a precisão limitada necessária não impeça tais métodos de outras aplicações, tais como o algoritmo de Shor, não podem usar a inferência bayesiana exata dentro do seu passo de estimativa de fase.  Por esta razão, também fornecemos implementações para métodos aproximados bayesianos, tais como [estimativa aleatória de fase de caminhada (RWPE)](xref:Microsoft.Quantum.Research.Characterization.RandomWalkPhaseEstimation) e também abordagens não-bayesianas, tais como estimativa de fase [robusta.](xref:Microsoft.Quantum.Characterization.RobustPhaseEstimation)

### <a name="robust-phase-estimation"></a>Estimativa de fase robusta ###

Uma reconstrução *máxima a posteriori* bayesiana de uma estimativa de fase dos resultados da medição é exponencialmente difícil no pior dos casos. Assim, a maioria dos algoritmos de estimativa de fase prática sacrificam alguma qualidade na reconstrução, em troca de uma quantidade de pós-processamento clássico que, em vez disso, escala polinicamente com o número de medições feitas.

Um desses exemplos com um passo clássico de pós-processamento eficiente é o robusto algoritmo de [estimativa de fase,](https://arxiv.org/abs/1502.02677)com a sua assinatura e entradas acima mencionadas. Assume que as caixas pretas unitárias de entrada $U$ são embaladas como `DiscreteOracle` tipo, e, portanto, apenas questiona os poderes inteiros de $U$. Se o estado de entrada no `Qubit[]` registo for um eigenstate $U\ket{\psi}=e^{i\phi}\ket{\psi}$, o algoritmo de estimativa de fase robusta devolve uma estimativa de $\hat{\phi}\in[\pi,\pi)$ de $\\phi$ como a `Double` .

A característica mais importante da estimativa de fase robusta, que é partilhada com a maioria das outras variantes úteis, é que a qualidade de reconstrução de $\hat{\phi}$ é, de certa forma, limitada por Heisenberg. Isto significa que se o desvio de $\hat{\phi}$ do valor verdadeiro for $\sigma$, então as escalas de $\sigma$ inversamente proporcional ao número total de consultas $Q$ feitas para $U$, ou seja, $\sigma=\mathcal{O}(1/Q)$. Agora, a definição de desvio varia entre diferentes algoritmos de estimativa. Em alguns casos, pode significar que, com pelo menos $\mathcal{O}(1)$ probabilidade, o erro de estimativa $\hat{\phi}-\phi phi \_ \circ\le \sigma$ em alguma medida circular $\circ$. Para uma estimativa de fase robusta, o desvio é precisamente a variação $\sigma^2 = \mathbb{E} \_ \hat{\phi}[\mod \_ {2\pi}(\hat{\phi}-\\phi +\pi)-\pi)^2]$ se desembrulharmos as fases periódicas num único intervalo finito (-\pi,\pi]. Mais precisamente, o desvio padrão na estimativa de fase robusta satisfaz as desigualdades $\ \start{align} 2.0 \pi / Q \le \sigma \le 2\pi / 2^{n} \le 10,7\pi / Q, \end{align} $$ onde o limite inferior é atingido no limite de $Q de tamanhos assinticamente grandes, e o limite superior é garantido até mesmo para pequenas amostras.  Note que $n$ selecionado pela `bitsPrecision` entrada, que define implicitamente $Q$.

Outros detalhes relevantes incluem, digamos, a pequena sobrecarga de espaço de apenas $1$ ancilla qubit, ou que o procedimento não é adaptável, o que significa que a sequência necessária de experiências quânticas é independente dos resultados da medição intermédia. Neste e nos próximos exemplos em que a escolha do algoritmo de estimativa de fase é importante, deve-se consultar a documentação como @"microsoft.quantum.characterization.robustphaseestimation" e as publicações referenciadas nelas para mais informações e para a sua implementação.

> [!TIP]
> Há muitas amostras onde é utilizada uma estimativa de fase robusta. Para uma estimativa de fase na extração da energia do estado do solo de vários sistemas físicos, consulte a amostra [ **de simulação H2,**](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/command-line)a amostra [ **SimpleIsing**](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/simple)e a amostra do [ **modelo Hubbard**](https://github.com/microsoft/Quantum/tree/main/samples/simulation/hubbard).


### <a name="continuous-oracles"></a>Oráculos contínuos ###

Também podemos generalizar a partir do modelo oráculo usado acima para permitir oráculos de tempo contínuo, modelados pelo tipo <xref:Microsoft.Quantum.Oracles.ContinuousOracle> canónico.
Considere que em vez de um único operador unitário $U$, temos uma família de operadores unitários $U(t)$ para $t \in \mathbb{R}$ tal que $U(t) U(s)$ = $U(t + s)$.
Esta é uma afirmação mais fraca do que no caso discreto, uma vez que podemos construir um <xref:Microsoft.Quantum.Oracles.DiscreteOracle> restringindo $t = m \, \delta t$ para alguns $\delta t$.
By [Stone's teorema](https://en.wikipedia.org/wiki/Stone%27s_theorem_on_one-parameter_unitary_groups), $U(t) = \exp(i H t)$ para algum operador $H$, onde $\exp$ é a matriz exponencial como descrito em [matrizes avançadas](xref:microsoft.quantum.concepts.matrix-advanced).
Um eigenstate $\ket{\phi}$ de $H$ tal que $H \ket{\phi} = \phi \phi\ket{\phi}$ é então também um eigenstate de $U(t)$ para todos os $t$, \start{equação} U(t) \ket{\phi} = e^{i phi}
\end{equação}

A mesma análise discutida para [a estimativa da fase bayesiana](#bayesian-phase-estimation) pode ser aplicada, e a função de probabilidade é precisamente a mesma para este modelo oráculo mais geral: $$ \Pr(\texttt{Zero} / \phi; t,\theta)=\cos^2\esquerda(\frac{t[\phi -\theta]} {2} \direita).
Além disso, se $U$ é uma simulação de um gerador dinâmico, como é o caso da [simulação hamiltoniana,](xref:microsoft.quantum.libraries.applications#hamiltonian-simulation)interpretamos $\phi$ como uma energia.
Assim, a estimativa de fase com consultas contínuas permite-nos aprender o espectro energético simulado [de moléculas,](https://arxiv.org/abs/quant-ph/0604193) [materiais](https://arxiv.org/abs/1510.03859) ou [teorias de campo](https://arxiv.org/abs/1111.3633v2) sem ter de comprometer a nossa escolha de experiências exigindo $t$ para ser um inteiro.

### <a name="random-walk-phase-estimation"></a>Estimativa aleatória da fase de caminhada ###

Q# fornece uma aproximação útil da estimativa da fase bayesiana projetada para uso próximo de dispositivos quânticos que funcionam condicionando uma caminhada aleatória no registo de dados obtido a partir da estimativa da fase iterativa.
Este método é simultaneamente adaptável e totalmente determinístico, permitindo uma escala quase ótima de erros na fase estimada $\hat{\phi}$ com sobrecargas de memória muito baixas.

O protocolo usa um método aproximado de inferência bayesiana que pressupõe que a distribuição anterior é gaussiana.
Esta suposição gaussiana permite-nos usar uma fórmula analítica para a experiência que minimiza a variação posterior.
O algoritmo, então com base no resultado dessa experiência, muda a estimativa de $\phi$ à esquerda ou à direita por uma quantia pré-determinada e diminui a variação por uma quantia pré-determinada.
Esta média e variação dão toda a informação necessária para especificar um gaussiano anterior em $\phi$ para a próxima experiência.
Falhas de medição inesperadas, ou o verdadeiro resultado na cauda do prior inicial, podem fazer com que este método falhe.
Recupera do fracasso através da realização de experiências para testar se a média atual e o desvio padrão são adequados para o sistema.
Se não estiverem, então o algoritmo faz um passo inverso da caminhada e o processo continua.
A capacidade de andar para trás também permite que o algoritmo aprenda mesmo que o desvio padrão inicial seja inapropriadamente pequeno.

## <a name="calling-phase-estimation-algorithms"></a>Algoritmos de estimativa de fase de chamada ##

Cada operação de estimativa de fase fornecida com o Q# cânone requer um conjunto diferente de entradas parametrizando a qualidade que exigimos fora da estimativa final $\hat{\phi}$.
Estas várias entradas, no entanto, todas partilham várias entradas em comum, de modo que a aplicação parcial sobre os parâmetros de qualidade resulta numa assinatura comum.
Por exemplo, a <xref:Microsoft.Quantum.Characterization.RobustPhaseEstimation> operação discutida na secção seguinte tem a seguinte assinatura:

```qsharp
operation RobustPhaseEstimation(bitsPrecision : Int, oracle : DiscreteOracle, eigenstate : Qubit[])  : Double
```

A `bitsPrecision` entrada é única `RobustPhaseEstimation` para, enquanto `oracle` `eigenstate` estão em comum.
Assim, como visto em **H2Sample,** uma operação pode aceitar um algoritmo de estimativa de fase iterativa com uma entrada do formulário `(DiscreteOracle, Qubit[]) => Unit` para permitir que um utilizador especifique algoritmos de estimativa de fase arbitrária:

```qsharp
operation H2EstimateEnergy(
    idxBondLength : Int,
    trotterStepSize : Double,
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double))
: Double
```

Estes algoritmos de estimativa de fase miríade são otimizados para diferentes propriedades e parâmetros de entrada, que devem ser entendidos para fazer a melhor escolha para a aplicação alvo. Por exemplo, alguns algoritmos de estimativa de fase são adaptáveis, o que significa que os passos futuros são clássicamente controlados pelos resultados da medição de passos anteriores. Alguns exigem a capacidade de exponenciar o seu oráculo unitário de caixa preta por poderes reais arbitrários, e outros apenas requerem poderes inteiros, mas só são capazes de resolver uma estimativa de fase modulo $2\pi$. Alguns requerem muitos qubits auxiliares, e outros requerem apenas um.

Da mesma forma, a estimativa aleatória da fase de caminhada prossegue da mesma forma que para outros algoritmos fornecidos com o cânone:

```qsharp
operation ApplyExampleOracle(
    eigenphase : Double,
    time : Double,
    register : Qubit[])
: Unit is Adj + Ctl {
    Rz(2.0 * eigenphase * time, register[0]);
}

operation EstimateBayesianPhase(eigenphase : Double) : Double {
    let oracle = ContinuousOracle(ApplyExampleOracle(eigenphase, _, _));
    using (eigenstate = Qubit()) {
        X(eigenstate);
        // The additional inputs here specify the mean and variance of the prior, the number of
        // iterations to perform, how many iterations to perform as a maximum, and how many
        // steps to roll back on an approximation failure.
        let est = RandomWalkPhaseEstimation(0.0, 1.0, 61, 100000, 1, oracle, [eigenstate]);
        Reset(eigenstate);
        return est;
    }
}
```
