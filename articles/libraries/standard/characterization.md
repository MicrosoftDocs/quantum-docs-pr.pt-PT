---
title: Q# bibliotecas padrão - caracterização / Microsoft Docs
description: Q# bibliotecas padrão - caracterização
author: QuantumWriter
uid: microsoft.quantum.libraries.characterization
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 51124dc78feedf6d5c85fe224898e66a1c5ed459
ms.sourcegitcommit: ca5015fed409eaf0395a89c2e4bc6a890c360aa2
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76870355"
---
# <a name="quantum-characterization-and-statistics"></a>Caracterização quântica e Estatísticas #

É fundamental ser capaz de caracterizar os efeitos das operações de forma a desenvolver algoritmos quânticos úteis.
Isto é um desafio porque cada medição de um sistema quântico produz, no máximo, um pouco de informação.
Para aprender um eigenvalue, muito menos um estado quântico, os resultados de muitas medições devem ser costurados em conjunto para que o utilizador possa recolher os muitos pedaços de informação necessários para representar estes conceitos.
Os Estados quânticos são especialmente preocupantes porque o [teorema](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) de não clonagem afirma que não há forma de aprender um estado quântico arbitrário a partir de uma única cópia do Estado, porque fazê-lo permitiria fazer cópias do Estado.
Esta obfuscção do estado quântico do utilizador reflete-se no facto de q# não expor ou mesmo definir o que um estado *é* para programas quânticos.
Abordamos assim a caracterização quântica, tratando as operações e os Estados como caixa preta; esta abordagem partilha muito em comum com a prática experimental de caracterização quântica, verificação e validação (QCVV).

A caracterização é distinta de muitas das outras bibliotecas discutidas anteriormente.
O objetivo aqui é menos aprender informação clássica sobre o sistema, em vez de realizar uma transformação unitária num vetor de estado.
Estas bibliotecas devem, portanto, misturar o processamento de informação clássica e quântica.


## <a name="iterative-phase-estimation"></a>Estimativa da fase iterativa ##

Ver a programação quântica em termos de caracterização quântica sugere uma alternativa útil à estimativa da fase quântica.
Ou seja, em vez de preparar mossa $n registo de qubit para conter uma representação binária da fase como na estimativa da fase quântica, podemos ver a estimativa de fase como o processo pelo qual um agente *clássico* aprende propriedades de um sistema quântico através de medições.
Procedemos como no caso quântico usando o recuo de fase para transformar as aplicações de uma operação de caixa preta em rotações por um ângulo desconhecido, mas vamos medir o qubit de oscilação que giramos em cada passo imediatamente após a rotação.
Isto tem a vantagem de que só precisamos de um único qubit adicional para realizar o recuo de fase descrito no caso quântico, pois aprendemos então a fase a partir dos resultados de medição em cada passo de forma iterativa.  
Cada um dos métodos abaixo propostos utiliza uma estratégia diferente para conceber experiências e diferentes métodos de processamento de dados para aprender a fase.  Cada um deles tem uma vantagem única que vai desde ter rigorosos limites de erro, até as capacidades de incorporar informações prévias, tolerar erros ou executar em computadores clássicos limitados de memória.

Ao discutir a estimativa da fase iterativa, consideraremos um $U$ unitário dado como uma operação de caixa preta.
Tal como descrito na secção sobre oráculos em estruturas de [dados,](xref:microsoft.quantum.libraries.data-structures)os modelos canon Q# tais operações pelo <xref:microsoft.quantum.oracles.discreteoracle> tipo definido pelo utilizador, definidos pelo tipo tuple `((Int, Qubit[]) => Unit : Adjoint, Controlled)`.
Concretamente, se `U : DiscreteOracle`, então `U(m)` implementa $U^m$ para `m : Int`.

Com esta definição em vigor, cada passo da estimativa da fase iterativa prossegue preparando um qubit auxiliar no estado $\ket{+}$ juntamente com o estado inicial $\ket {\phi}} que assumimos ser um [eigenvector](xref:microsoft.quantum.concepts.matrix-advanced) de $U(m)$, ou seja, $U(m)\ket{\phi}= e^im\phi}\ket{}}}.}.}.}.}.}.}.}.  
Uma aplicação controlada de `U(m)` é então usada que prepara o estado $\left (R\_1(m \phi) \ket{+}\right)ket{\phi}$.
Tal como no caso quântico, o efeito de uma aplicação controlada do oráculo `U(m)` é precisamente o mesmo que o efeito de aplicar $R_1$ para a fase desconhecida em $\ket{+}$, de tal forma que podemos descrever os efeitos de $U$ desta forma mais simples.
Opcionalmente, o algoritmo roda o qubit de controlo aplicando $R_1 (-m\theta)$ para obter um estado $\ket{\psi}=à esquerda(R\_1(m [\phi-\theta]) \ket{+}\direita)\ket{\phi}$.
O qubit auxiliar utilizado como controlo para `U(m)` é então medido na base $X$para obter uma única `Result`clássica.

Neste ponto, a reconstrução da fase a partir dos valores `Result` obtidos através da estimativa da fase iterativa é um problema clássico de inferência estatística.
Encontrar o valor de $m$ que maximize a informação obtida, dado um método de inferência fixa, é simplesmente um problema nas estatísticas.
Salientamos isto descrevendo brevemente a estimativa da fase iterativa a nível teórico no formalismo de estimativa do parâmetro bayesiano antes de proceder para descrever os algoritmos estatísticos fornecidos no cânone Q# para resolver este problema de inferência clássica.

### <a name="iterative-phase-estimation-without-eigenstates"></a>Estimativa de fase iterativa sem eigenstates ###

Se for fornecido um estado de entrada que não seja um eigenstate, o que significa que se $U(m)\ket{\phi\_j} = e^{im\phi\_j}$ então o processo de estimativa de fase não-determinicamente guia o estado quântico para um único eigenstate energético.  O eigenstate a que, em última análise, converge é o eigenstate que é mais provável produzir o `Result`observado.

Especificamente, um único passo de E executa a seguinte transformação não unitária num estado \begin{align} \sum_j \sqrt{\Pr(\phi\_j)} \ket{\phi\_j} \mapsto \sum\_j\frac{\sqrt{\Pr(\phi\_j)}\sqrt{\Pr(\text{Result}\phi\_j)}\ket{\phi\_j}}{\sqrt{\Pr(\phi\_j)\sum\_j \Pr(\text{Result}\phi\_j)}}
\end{align} Como este processo é iterado sobre vários valores de `Result`, os eigenstates que não têm valores máximos de $\prod_k\Pr(\text{Result}\_k\phi\_j)$ serão exponencialmente suprimidos.
Como resultado, o processo de inferência tenderá a convergir para estados com um único eigenvalue se as experiências forem escolhidas corretamente.

O teorema de Bayes sugere ainda que o estado que resulta da estimativa de fase seja escrito na forma \begin{align} \frac{\sqrt{\Pr(\phi\_j)}\sqrt{\Pr(\text{Result}\phi\_j)}\ket{\\_phi j}}{\sqrt{\Pr(\phi\_j)\sum\_j \Pr(\text{Result}\phi\_j)}\\sum_j\\\sqrt{\Pr(\phi\_j\text{Result}}} \ket{\phi\_j}.
\end{align} Here $\Pr(\phi\_j\text{Result})$pode ser interpretado como a probabilidade que se atribuiria a cada hipótese sobre os eigenstates dado:

1. conhecimento do estado quântico antes da medição,
2. conhecimento dos eigenstates de $U$ e,
3. conhecimento dos valores eigen de $U$.

Aprender estas três coisas é muitas vezes exponencialmente difícil num computador clássico.
A utilidade da estimativa de fase surge, em grande parte, pelo facto de poder realizar uma tarefa de aprendizagem quântica sem conhecer nenhuma delas.
A estimativa de fase por esta razão aparece dentro de uma série de algoritmos quânticos que fornecem acelerações exponenciais.

### <a name="bayesian-phase-estimation"></a>Estimativa da fase bayesiana ###

> [!TIP]
> Para obter mais detalhes sobre a estimativa da fase bayesiana na prática, consulte a amostra de Estimativa de [**Fase.** ](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation)

A ideia da estimativa da fase bayesiana é simples.
Recolhe-se estatísticas de medição do protocolo de estimativa de fase e, em seguida, processa os resultados usando inferência bayesiana e fornece uma estimativa do parâmetro.
Este processamento dá-lhe uma estimativa do valor eigenvalue, bem como da incerteza nessa estimativa.
Também permite realizar experiências adapttivas e utilizar informações prévias.
O principal inconveniente dos métodos é que é computacionalmente exigente.

Para entender como funciona este processo de inferência bayesiana, considere o caso de processamento de um único resultado `Zero`.
Note que $X = \ket{+}\bra{+} - \ket{-}\bra{-}$, de tal forma que $\ket{+}$ é o único eigenstate positivo de $X$ correspondente a `Zero`.
A probabilidade de observar `Zero` para uma [medição`PauliX`](xref:microsoft.quantum.concepts.pauli) no primeiro qubit dado um estado de entrada {\cet{\psi}\ket{\phi}$ é assim \start{equation} \Pr(\texttt{{ { \ psi) = \left; \braket{+ \ \psi} \right^2.
\end{equation} No caso da estimativa da fase iterativa, temos aquele $\ket{\psi} = R_1(m [\phi-theta]) \ket{+}$, de tal forma que \start{align} \Pr(\texttt{Zero} \ \phi; m,\theta) & = \left] \braket{+ [ R_1 (m[\phi-\theta]) +} \direita^^^2 \\\\ & = \left; \frac12 \left, \bra{0} + \bra{1} \right, \ket{0} + e^{i m [\phi-\theta]} \ket{1} \right; \right^2 \\\\ & = \left; \frac{1 + e^{i m [\phi-\theta]}}{2} \right\^\\2 \\ & = \cos^2(m [\phi-theta] / 2) \tag{★} \label{eq:phase-est-probabilidade}.
\end{align} Ou seja, a estimativa da fase iterativa consiste em aprender a frequência de oscilação de uma função sinusoidal, dada a capacidade de lançar uma moeda com um enviesamento dado por esse sinusoid.
Seguindo a terminologia clássica tradicional, chamamos $\eqref{eq:phase-est-probabilidade}$ a *função de probabilidade* para estimativa de fase iterativa.

Tendo observado uma `Result` da função de probabilidade de estimativa de fase iterativa, podemos então usar a regra de Bayes para prescrever o que devemos acreditar que a fase deve seguir essa observação.
Concretamente, \start{equation} \Pr(\phi  d) = \frac{\Pr(d  \phi) \Pr(\phi){\int \Pr(d  \phi) \Pr(\phi){\mathrm d}\phi} \Pr(\phi), \end{equation} onde $d \in \\{\textt{Zero}, \texttt{One}\\}$ é um `Result`, e onde $\Pr(\phi)$ descreve as nossas crenças anteriores sobre $\phi$.
Isto torna então explícita a natureza iterativa da estimativa da fase iterativa, uma vez que a distribuição posterior $\Pr(\phi / d)$ descreve as nossas crenças imediatamente precedidos da nossa observação da próxima `Result`.

Em qualquer momento durante este procedimento, podemos reportar a fase $\hat{\phi}$ inferida pelo controlador clássico como \start{equation} \hat{\phi \mathrel{:=} \expect[\phi ] \text{data}] = \int \phi \Pr(\phi [ \text{data}) {\mathrm d}\phi, \end{equação} onde o texto {{data}`Result`}

A inferência exata de Bayesian é na prática intratável.
Para ver esta imagine, queremos aprender uma variável de $n$bit $x$.
A distribuição prévia $\Pr(x)$ tem suporte acima de $2^n$ valores hipotéticos de $x$.
Isto significa que se precisarmos de uma estimativa muito precisa de $x$ então a estimativa da fase bayesiana pode precisar de memória proibitiva e tempo de processamento.
Embora para algumas aplicações, como a simulação quântica, a precisão limitada necessária não impeça tais métodos de outras aplicações, como o algoritmo de Shor, não podem usar a inferência bayesiana exata dentro do seu passo de estimativa de fase.  Por esta razão, também fornecemos implementações para métodos bayesianos aproximados, tais como a estimativa de [fases de caminhada aleatória (RWPE)](xref:microsoft.quantum.research.randomwalkphaseestimation.randomwalkphaseestimation) e também abordagens não bayesianas, tais como [a estimativa de fase robusta.](xref:microsoft.quantum.characterization.robustphaseestimation)

### <a name="robust-phase-estimation"></a>Estimativa de fase robusta ###

Um máximo uma reconstrução *posteriori* Bayesian de uma estimativa de fase dos resultados da medição é exponencialmente difícil no pior dos casos. Assim, a maioria dos algoritmos práticos de estimativa de fase sacrificam alguma qualidade na reconstrução, em troca de uma quantidade de pós-processamento clássico que, em vez disso, escala polinomialmente com o número de medições feitas.

Um desses exemplos com um passo pós-processamento clássico eficiente é o algoritmo robusto de estimativa de [fase,](https://arxiv.org/abs/1502.02677)com a sua assinatura e inputs acima mencionados. Assume que as caixas pretas unitárias de entrada $U$ são embaladas como `DiscreteOracle` tipo, e, portanto, apenas consultas de $U$controladas. Se o estado de entrada no registo `Qubit[]` for um eigenstate $U\ket{\psi}=e^{i\phi\ket{\psi}$, o algoritmo de estimativa de fase robusta devolve uma estimativa $\hat{\phi}\in[-\pi,\pi)$ de $\phi$ como um `Double`.

A característica mais importante da estimativa de fase robusta, que é partilhada com a maioria das outras variantes úteis, é que a qualidade de reconstrução de $\hat{\phi}$ é, de certa forma, limitada a Heisenberg. Isto significa que se o desvio de $\hat{\phi}$ do valor real for $\sigma$, então $\sigma$ escalas inversamente-proporcionais ao número total de consultas $Q$ feitas a $U$, ou seja, $\sigma=\mathcal{O}(1/Q)$. Agora, a definição de desvio varia entre diferentes algoritmos de estimativa. Em alguns casos, pode significar que com pelo menos $\mathcal{O}(1)$ probabilidade, o erro de estimativa $\hat{\phi}-\phi\_\circ\le \sigma$ em alguma medida circular $\circ$. Para uma estimativa robusta da fase, o desvio é precisamente a variação $\sigma^2 = \mathbb{E}\_\hat{\phi}[[\mod\_{2\pi}(\hat{\phi}\phi +\pi)-pi)^2]$ se desembrulharmos as fases periódicas num único intervalo finito $(\pi,pi]$. Mais precisamente, o desvio padrão na estimativa de fase robusta satisfaz as desigualdades $$ \begin{align} 2.0 \pi / Q \le \sigma \le 2\pi / 2^{n} \le 10.7\pi / Q, \end{align} $$ onde o limite inferior é atingido no limite de assimptoticamente grande $Q$, e o limite superior é garantido mesmo para pequenas amostras.  Note que $n$ selecionados pela entrada `bitsPrecision`, que define implicitamente $Q$.

Outros detalhes relevantes incluem, por exemplo, o pequeno espaço sobrecarga de apenas $1$ qubit de acesso, ou que o procedimento não é adaptável, o que significa que a sequência necessária de experiências quânticas é independente dos resultados de medição intermédio. Neste e próximo exemplos em que a escolha do algoritmo de estimativa de fase é importante, deve-se referir-se à documentação, como @"microsoft.quantum.characterization.robustphaseestimation" e às publicações referenciadas para obter mais informações e para a sua implementação.

> [!TIP]
> Há muitas amostras onde é utilizada uma estimativa de fase robusta. Para a estimativa de fase na extração da energia do estado terrestre de vários sistemas físicos, consulte a amostra de [ **simulação H2,** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line)a amostra [ **simpleising** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/simple)e a amostra do [ **modelo Hubbard.** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard)


### <a name="continuous-oracles"></a>Oráculos contínuos ###

Também podemos generalizar a partir do modelo oráculo usado acima para permitir oráculos de tempo contínuo, modelados pelo tipo canon <xref:microsoft.quantum.oracles.continuousoracle>.
Considere que em vez de um único operador unitário $U$, temos uma família de operadores unitários $U(t)$ para $t \in \mathbb{R}$ tal que $U(t) U(s)$ = $U(t+ s)$.
Esta é uma afirmação mais fraca do que no caso discreto, uma vez que podemos construir uma <xref:microsoft.quantum.oracles.discreteoracle> restringindo $t = m\,\delta t$ por alguns $\delta t$fixos.
Pelo [teorema de Stone](https://en.wikipedia.org/wiki/Stone%27s_theorem_on_one-parameter_unitary_groups), $U(t) = \exp(i H t)$ para algum operador $H$, onde $\exp$ é a matriz exponencial como descrito em [matriz avançada.](xref:microsoft.quantum.concepts.matrix-advanced)
Um eigenstate $\ket {\phi}$ de $H$ tal que $H \ket{\phi} = \phi {\phi}} é então também um eigenstate de $U(t)$ para todos os $t$, \start{equation} U(t) \ket{\phi} = e{^i \phi t} \{\phi}.
\end{equation}

A mesma análise discutida para a estimativa da [fase bayesiana](#bayesian-phase-estimation) pode ser aplicada, e a função de probabilidade é precisamente a mesma para este modelo oráculo mais geral: $$ \Pr(\texttt{Zero} \ phi; t,\theta)=\cos^2\left (\frac{t[\phi -\theta]}{2}\direita).
$$ Além disso, se $U$ é uma simulação de um gerador dinâmico, como é o caso da [simulação hamiltoniana,](xref:microsoft.quantum.libraries.applications#hamiltonian-simulation)interpretamos $\phi$ como uma energia.
Assim, usar a estimativa de fase com consultas contínuas permite-nos aprender o espectro de energia simulado [de moléculas,](https://arxiv.org/abs/quant-ph/0604193) [materiais](https://arxiv.org/abs/1510.03859) ou [teorias](https://arxiv.org/abs/1111.3633v2) de campo sem ter que comprometer a nossa escolha de experiências, exigindo que $t$ seja um inteiro.

### <a name="random-walk-phase-estimation"></a>Estimativa de fase de caminhada aleatória ###

Q# fornece uma aproximação útil da estimativa de fase bayesiana projetada para uso perto de dispositivos quânticos que operam condicionando uma caminhada aleatória no registo de dados obtido a partir da estimativa de fase iterativa.
Este método é simultaneamente adaptativo e inteiramente determinista, permitindo uma escala quase ótima de erros na fase estimada $\hat{\phi}$ com despesas de memória muito baixas.

O protocolo usa um método de inferência bayesiana aproximada que pressupõe que a distribuição prévia é gaussian.
Esta suposição gaussiana permite-nos usar uma fórmula analítica para a experiência que minimiza a variação posterior.
O algoritmo, então, com base no resultado dessa experiência, muda a estimativa de $\phi$ à esquerda ou à direita por uma quantia pré-determinada e diminui a variação por uma quantia pré-determinada.
Esta média e variação dão toda a informação necessária para especificar um gaussiano anterior em $\phi$ para a próxima experiência.
Falhas de medição inesperadas, ou o resultado real estar na cauda do anterior inicial, podem fazer com que este método falhe.
Recupera-se da falha através da realização de experiências para testar se a média atual e o desvio padrão são adequados para o sistema.
Se não forem, então o algoritmo faz um passo inverso da caminhada e o processo continua.
A capacidade de andar para trás também permite que o algoritmo aprenda mesmo que o desvio padrão inicial seja inapropriadamente pequeno.

## <a name="calling-phase-estimation-algorithms"></a>Algoritmos de estimativa de fase ##

Cada operação de estimativa de fase fornecida com o cânon Q# leva um conjunto diferente de inputs parametrizando a qualidade que exigimos da estimativa final $\hat{\phi}$.
Estas várias inputs, no entanto, todas partilham várias inputs em comum, de tal forma que a aplicação parcial sobre os parâmetros de qualidade resulta numa assinatura comum.
Por exemplo, a operação <xref:microsoft.quantum.characterization.robustphaseestimation> discutida na secção seguinte tem a seguinte assinatura:

```qsharp
operation RobustPhaseEstimation(bitsPrecision : Int, oracle : DiscreteOracle, eigenstate : Qubit[])  : Double
```

A entrada `bitsPrecision` é única para `RobustPhaseEstimation`, enquanto `oracle` e `eigenstate` são comuns.
Assim, como visto no **H2Sample,** uma operação pode aceitar um algoritmo de estimativa de fase iterativa com uma entrada do formulário `(DiscreteOracle, Qubit[]) => Unit` permitir que um utilizador especifique algoritmos de estimativa de fase arbitrária:

```qsharp
operation H2EstimateEnergy(
    idxBondLength : Int,
    trotterStepSize : Double,
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double))
: Double
```

Estes algoritmos de estimativa de fase miríade são otimizados para diferentes propriedades e parâmetros de entrada, que devem ser entendidos para fazer a melhor escolha para a aplicação alvo. Por exemplo, alguns algoritmos de estimativa de fase são adaptáveis, o que significa que os passos futuros são controlados clássicamente pelos resultados de medição de passos anteriores. Alguns requerem a capacidade de exponenciar o seu oráculo unitário caixa preta por poderes reais arbitrários, e outros apenas requerem poderes inteiros, mas só são capazes de resolver uma estimativa de fase modulo $2\pi$. Alguns requerem muitos qubits auxiliares, e outros requerem apenas um.

Da mesma forma, a utilização da estimativa de fase de caminhada aleatória prossegue da mesma forma que para outros algoritmos fornecidos com o cânone:

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
