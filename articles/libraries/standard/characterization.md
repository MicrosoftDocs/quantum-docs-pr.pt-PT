---
title: 'Q # bibliotecas padrão-caracterização | Microsoft Docs'
description: 'P # bibliotecas padrão-caracterização'
author: QuantumWriter
uid: microsoft.quantum.libraries.characterization
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: d77085aa8aa83c18858056bab1858d990efdb36e
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185567"
---
# <a name="quantum-characterization-and-statistics"></a>Caracterização e estatísticas do Quantum #

É fundamental poder caracterizar os efeitos das operações para desenvolver algoritmos de Quantum úteis.
Isso é desafiador porque cada medição de um sistema Quantum gera no máximo um pouco de informação.
Para aprender um eigenvalue, independente de um estado Quantum, os resultados de várias medições devem ser Unidos para que o usuário possa obter as muitas informações necessárias para representar esses conceitos.
Os Estados da Quantum são especialmente inconvenientes porque o [teorema sem clonagem](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) afirma que não há como aprender um estado de Quantum arbitrário a partir de uma única cópia do estado, pois isso permitiria que você faça cópias do estado.
Essa ofuscação do estado Quantum do usuário é refletida no fato de que Q # não expõe ou nem define o que um estado *é* para os programas Quantum.
Portanto, abordamos a caracterização Quantum tratando as operações e os Estados como preto-caixa; Essa abordagem compartilha muito em comum com a prática experimental de caracterização, verificação e validação do Quantum (QCVV).

A caracterização é distinta de muitas das outras bibliotecas discutidas anteriormente.
O objetivo aqui é menos aprender informações clássicas sobre o sistema, em vez de executar uma transformação unitário em um vetor de estado.
Portanto, essas bibliotecas devem misturar o processamento de informações clássica e Quantum.


## <a name="iterative-phase-estimation"></a>Estimativa de fase iterativa ##

A exibição da programação Quantum em termos de caracterização Quantum sugere uma alternativa útil à estimativa da fase Quantum.
Ou seja, em vez de preparar um registro de $n $-qubit para conter uma representação binária da fase como na estimativa da fase Quantum, podemos exibir a estimativa de fase como o processo pelo qual um agente *clássico* aprende as propriedades de um sistema Quantum por meio de medidas.
Continuaremos como no caso do Quantum usando a fase Kickback para transformar os aplicativos de uma operação de caixa preta em rotações por um ângulo desconhecido, mas medirá o qubit de ancilla que giramos em cada etapa imediatamente após a rotação.
Isso tem a vantagem de exigirmos apenas um único qubit adicional para executar a fase Kickback descrita no caso Quantum, como aprendemos a fase dos resultados da medida em cada etapa de maneira iterativa.  
Cada um dos métodos propostos abaixo usa uma estratégia diferente para a criação de experimentos e métodos de processamento de dados diferentes para aprender a fase.  Cada um deles tem vantagem única, desde a necessidade de limites de erro rigorosos até a capacidade de incorporar informações anteriores, tolerar erros ou executar em computadores Limitted de memória.

Ao discutir a estimativa de fase iterativa, consideraremos um $U unitário $ fornecido como uma operação de caixa preta.
Conforme descrito na seção sobre Oracle em estruturas de [dados](xref:microsoft.quantum.libraries.data-structures), os modelos Q # Canon são operações pelo tipo de <xref:microsoft.quantum.oracles.discreteoracle> definido pelo usuário, definido pelo `((Int, Qubit[]) => Unit : Adjoint, Controlled)`tipo de tupla.
Concretamente, se `U : DiscreteOracle`, `U(m)` implementa $U ^ m $ para `m : Int`.

Com essa definição em vigor, cada etapa da estimativa de fase iterativa continua preparando uma auxiliar qubit no estado $ \ket{+} $, juntamente com o estado inicial $ \ket{\phi} $ que supomos que é um [eigenvector](xref:microsoft.quantum.concepts.matrix-advanced) de $U (m) $, ou seja, $U (m) \ket{\phi} = e ^ {im\phi} \ket{\phi} $.  
Um aplicativo controlado de `U(m)` é usado, o que prepara o estado $ \left (R\_1 (m \phi) \ket{+} \right) \ket{\phi} $.
Como no caso do Quantum, o efeito de um aplicativo controlado do `U(m)` da Oracle é precisamente o mesmo que o efeito de aplicar $R _1 $ para a fase desconhecida em $ \ket{+} $, de modo que possamos descrever os efeitos de $U $ dessa maneira mais simples.
Opcionalmente, o algoritmo gira o controle qubit aplicando $R _1 (-m\theta) $ para obter um estado $ \ket{\psi} = \left (R\_1 (m [\phi-\theta]) \ket{+} \right) \ket{\phi} $ $.
O auxiliar qubit usado como um controle para `U(m)` é então medido na base de $X $ para obter um único `Result`clássico.

Neste ponto, a reconstrução da fase do `Result` valores obtidos por meio da estimativa de fase iterativa é um problema de inferência de estatística clássica.
Encontrar o valor de $m $ que maximiza as informações obtidas, considerando um método de inferência fixo, é simplesmente um problema nas estatísticas.
Enfatizamos isso descrevendo brevemente a estimativa de fase iterativa em um nível teórico no bayesiana de estimativa de parâmetro de subestimação antes de continuar a descrever os algoritmos estatísticos fornecidos no Q # Canon para resolver essa inferência clássica persisti.

### <a name="iterative-phase-estimation-without-eigenstates"></a>Estimativa de fase iterativa sem Eigenstates ###

Se um estado de entrada for fornecido que não é um eigenstate, o que significa que, se $U (m) \ket{\phi\_j} = e ^ {im\phi\_j} $, o processo de estimativa de fase não determina de forma determinística o estado da Quantum em direção a um único eigenstate de energia.  A eigenstate, na verdade, convergi que é a eigenstate que tem mais probabilidade de produzir os `Result`observados.

Especificamente, uma única etapa do PE executa a seguinte transformação não-unitário em um estado \begin{align} \sum_j \sqrt{\Pr (\phi\_j)} \ket{\phi\_j} \mapsto \sum\_j\frac {\ sqrt {\ PR (\phi\_j)} \sqrt{\Pr (\text{Result} | \ Phi\_j)} \ket{\phi\_j}} {\sqrt{\Pr (\phi\_j) \sum\_j \Pr (\text{Result} | \phi\_j)}}.
\end{align} como esse processo é iterado em vários valores `Result`, eigenstates que não têm valores máximos de $ \prod_k\Pr (\text{Result}\_k | \phi\_j) $ serão suprimidos exponencialmente.
Como resultado, o processo de inferência terá a tendência de convergir para Estados com um único eigenvalue se os experimentos forem escolhidos corretamente.

Bayes ' teorema ' sugerirá ainda mais que o estado resultante da estimativa de fase será gravado no formato \begin{align} \frac{\sqrt{\Pr (\phi\_j)} \sqrt{\Pr (\text{Result} | \phi\_j)} \ket{\phi\_j}} {\sqrt{\Pr (\phi\_j) \sum\_j \Pr (\text{Result} | \phi\_j)}} = \sum_j \sqrt{\Pr (\phi\_j | \text{Result})} \ket{\phi\_j}.
\end{align} aqui $ \Pr (\phi\_j | \text{Result}) $ pode ser interpretado como a probabilidade de que um ascribeia para cada hipótese sobre os eigenstates fornecidos:

1. conhecimento do estado do Quantum antes da medição,
2. conhecimento do eigenstates de $U $ e,
3. conhecimento do eigenvalues de $U $.

Aprender essas três coisas muitas vezes é exponencialmente difícil em um computador clássico.
O utilitário de estimativa de fase surge, sem qualquer extensão, desde o fato de que ele pode executar tal tarefa de aprendizado Quantum sem conhecer nenhum deles.
A estimativa de fase para esse motivo aparece dentro de um número de algoritmos Quantum que fornecem aumentos exponencials.

### <a name="bayesian-phase-estimation"></a>Estimativa de fase Bayesiana ###

> [!TIP]
> Para obter mais detalhes sobre a estimativa de fase Bayesiana na prática, consulte o exemplo de [**PhaseEstimation**](https://github.com/Microsoft/Quantum/tree/master/Samples/src/PhaseEstimation) .

A ideia da estimativa de fase de bayesiana é simples.
Você coleta estatísticas de medição do protocolo de estimativa de fase e, em seguida, processa os resultados usando a inferência Bayesiana e fornece uma estimativa do parâmetro.
Esse processamento fornece uma estimativa do eigenvalue, bem como a incerteza nessa estimativa.
Ele também permite que você execute experimentos adaptáveis e utilize informações anteriores.
A desvantagem do princípio dos métodos é que ele é computacionalmente exigente.

Para entender como esse processo de inferência de Bayesiana funciona, considere o caso de processamento de um único resultado de `Zero`.
Observe que $X = \ket{+} \bra{+}-\ket{-}\bra{-}$, de modo que $ \ket{+} $ é o único eigenstate positivo de $X $ correspondente a `Zero`.
A probabilidade de observar `Zero` para uma [medida`PauliX`](xref:microsoft.quantum.concepts.pauli) no primeiro qubit dado um estado de entrada $ \ket{\psi}\ket{\phi} $ é, portanto, \begin{Equation} \Pr (\texttt{zero} | \psi) = \left | \braket{+ | \psi} \right | ^ 2.
\end{Equation} no caso de estimativa de fase iterativa, temos o $ \ket{\psi} = R_1 (m [\phi-\theta]) \ket{+} $, de modo que \begin{align} \Pr (\texttt{Zero} | \phi; m, \theta) & = \left | \braket{+ | R_1 (m [\phi-\theta]) | +} \right | ^ 2 \\\\ & = \left | \frac12 \left (\bra{0} + \bra{1} \right) \left (\ket{0} + e ^ {i m [\phi-\theta]} \ket{1} \right) \right | ^ 2 \\\\ & = \left | \frac{1 + e ^ {i m [\phi-\theta]}}{2} \right | ^ 2 \\\\ & = \cos ^ 2 (m [\phi-\theta]/2) \tag{★} \label{EQ: Phase-est-probabilidade}.
\end{Align}, ou seja, a estimativa de fase iterativa consiste em aprender a frequência de oscilação de uma função sinusoidal, dada a capacidade de virar uma moeda com uma tendência dada por essa sinusoid.
Seguindo a terminologia clássica tradicional, chamamos de $ \eqref{EQ: Phase-est-probabilidade} $ a *função de probabilidade* para estimativa de fase iterativa.

Após observar uma `Result` da função de probabilidade de estimativa de fase iterativa, podemos usar a regra Bayes ' para prescrever o que deve acreditar que a fase esteja seguindo essa observação.
Concreto, \begin{Equation} \Pr (\phi | d) = \frac{\Pr (d | \phi) \Pr (\phi)} {\int \Pr (d | \phi) \Pr (\phi) {\mathrm d} \phi} \Pr (\phi), \end{Equation} em que $d na \\{\texttt{Zero}, \texttt{One}\\} $ é um `Result`e, em que $ \Pr (\phi) $ Descreve nosso crenças anterior sobre $ \phi $.
Isso faz com que a natureza iterativa da estimativa de fase iterativa seja explícita, já que a distribuição posteriores $ \Pr (\phi | d) $ descreve nosso crenças imediatamente antes da nossa observação do próximo `Result`.

A qualquer momento durante esse procedimento, podemos relatar a fase $ \hat{\phi} $ inferida pelo controlador clássico como \begin{Equation} \hat{\phi} \mathrel{: =} \expect [\phi | \Text{data}] = \int \phi \Pr (\phi | \Text{Data}) {\mathrm d} \phi, \end{Equation} em que $ \ Text {Data} $ significa todo o registro de todos os `Result` valores obtidos.

A inferência exata de bayesiana é uma prática inmanejável.
Para ver essa imagine, desejamos aprender uma variável de $n de $ bits $x $.
A distribuição anterior $ \Pr (x) $ tem suporte acima de US $2 ^ n $ valores hipotéticos de $x $.
Isso significa que, se precisar de uma estimativa altamente precisa de $x $, a estimativa de fase Bayesiana poderá precisar de memória proibitiva e tempo de processamento.
Embora, para alguns aplicativos, como a simulação do Quantum, a precisão Limitted necessária não impede que outros métodos de outros aplicativos, como o algoritmo do Atal, não possam usar a inferência exata de Bayesiana em sua etapa de estimativa de fase.  Por esse motivo, também fornecemos implementações para métodos Bayesiana aproximados, como [estimativa aleatória de fase de passeio (RWPE)](xref:microsoft.quantum.research.randomwalkphaseestimation.randomwalkphaseestimation) e também abordagens não Bayesiana, como [estimativa de fase robusta](xref:microsoft.quantum.characterization.robustphaseestimation).

### <a name="robust-phase-estimation"></a>Estimativa de fase robusta ###

Uma reconstrução máxima de *posteriori* bayesiana de uma fase estimada dos resultados da medição é exponencialmente difícil no pior caso. Assim, os algoritmos de estimativa de fase mais práticos sacrificam alguma qualidade na reconstrução, no Exchange para uma quantidade de pós-processamento clássico que, em vez disso, escala polinomialmente com o número de medições feitas.

Um exemplo com uma etapa de pós-processamento clássica eficiente é o algoritmo de [estimativa de fase robusta](https://arxiv.org/abs/1502.02677), com sua assinatura e suas entradas mencionadas acima. Ele pressupõe que as caixas pretas de entrada $U $ são empacotadas como `DiscreteOracle` tipo e, portanto, consulta apenas as potências de inteiros de $U $ controlado $. Se o estado de entrada no registro de `Qubit[]` for um eigenstate $U \ket{\psi} = e ^ {i\phi} \ ket {\ psi} $, o algoritmo de estimativa de fase robusta retornará uma estimativa $ \hat{\phi}\in [-\pi, \pi) $ de $ \phi $ como um `Double`.

O recurso mais importante da estimativa de fase robusta, que é compartilhada com a maioria das variantes úteis, é que a qualidade de reconstrução de $ \hat{\phi} $ está em certo sentido Heisenberg-Limited. Isso significa que, se o desvio de $ \hat{\phi} $ do valor verdadeiro for $ \sigma $, $ \sigma $ escala inversamente – proporcionalmente ao número total de consultas $Q $ feitas para o $U controlado $, ou seja, $ \sigma = \mathcal{O} (1/Q) $. Agora, a definição de desvio varia entre diferentes algoritmos de estimativa. Em alguns casos, pode significar que, com pelo menos $ \mathcal{O} (1) $ probabilidade, o erro de estimativa $ | \hat{\phi}-\phi |\_\circ\le \sigma $ em alguma medida circular $ \circ $. Para estimativa de fase robusta, o desvio é precisamente a variância $ \sigma ^ 2 = \mathbb{E}\_\hat{\phi} [(\mod\_{2 \ PI} (\hat{\phi}-\phi + \pi)-\pi) ^ 2] $ se não quebrarmos as fases periódicas em um único intervalo finito $ (-\pi, \pi] $. Mais precisamente, o desvio padrão em estimativa de fase robusta satisfaz as desigualdades $ $ \begin{align} 2,0 \pi/Q \le \sigma \le 2 \ pi/2 ^ {n} \le 10.7 \ PI/Q, \end{Align} $ $, onde o limite inferior é atingido no limite de assintoticamente grande $Q $ e no canto superior o limite é garantido mesmo para tamanhos de amostra pequenos.  Observe que $n $ selecionado pela entrada de `bitsPrecision`, que define implicitamente $Q $.

Outros detalhes relevantes incluem, digamos, a sobrecarga de espaço pequeno de apenas $1 $ ancilla qubit, ou que o procedimento não é adaptável, o que significa que a sequência necessária de experimentos de Quantum é independente dos resultados de medida intermediários. Neste e em breves exemplos em que a escolha do algoritmo de estimativa de fase é importante, deve-se consultar a documentação como @"microsoft.quantum.canon.robustphaseestimation" e as publicações referenciadas aqui para obter mais informações e sobre sua implementação.

> [!TIP]
> Há muitos exemplos em que a estimativa de fase robusta é usada. Para estimativa de fase na extração da energia de estado terrestre de vários sistemas físicos, consulte o exemplo de [ **simulação H2** ](https://github.com/Microsoft/Quantum/tree/master/Samples/src/H2SimulationCmdLine), o [exemplo **SimpleIsing** ](https://github.com/Microsoft/Quantum/tree/master/Samples/src/SimpleIsing)e o exemplo de [ **modelo Hubbard** ](https://github.com/Microsoft/Quantum/tree/master/Samples/src/HubbardSimulation).


### <a name="continuous-oracles"></a>Oracle contínuos ###

Também é possível generalizar a partir do modelo Oracle usado acima para permitir Oracle, modelados pelo tipo de Canon <xref:microsoft.quantum.oracles.continuousoracle>.
Considere que, em vez de um único operador unitário $U $, temos uma família de operadores unitários $U (t) $ para $t na \mathbb{R} $ de forma que $U (t) U (s) $ = $U (t + s) $.
Essa é uma declaração mais fraca do que no caso discreto, já que podemos construir uma <xref:microsoft.quantum.oracles.discreteoracle> restringindo $t = m\,\delta t $ para alguns $ \delta t $ fixos.
Por [teorema da pedra](https://en.wikipedia.org/wiki/Stone%27s_theorem_on_one-parameter_unitary_groups), $U (t) = \exp (i t) $ para algum operador $H $, em que $ \exp $ é o exponencial de matriz, conforme descrito em [matrizes avançadas](xref:microsoft.quantum.concepts.matrix-advanced).
Um eigenstate $ \ket{\phi} $ de $H $ de forma que $H \ket{\phi} = \phi \ket{\phi} $ também é um eigenstate de $U (t) $ para todos os $t $, \begin{Equation} U (t) \ket{\phi} = e ^ {i \phi t} \ket{\phi}.
\end{equation}

A mesma análise discutida para a [estimativa de fase Bayesiana](#bayesian-phase-estimation) pode ser aplicada, e a função de probabilidade é exatamente a mesma para esse modelo Oracle geral: $ $ \Pr (\texttt{zero} | \phi; t, \theta) = \cos ^ 2 \ Left (\frac{t [\phi-\theta]} @no__ t_1_ \right).
$ $ Mais, se $U $ for uma simulação de um gerador dinâmico, como é o caso da [simulação de Hamiltonian](xref:microsoft.quantum.libraries.applications#hamiltonian-simulation), interpretamos $ \phi $ como uma energia.
Portanto, o uso da estimativa de fase com consultas contínuas nos permite aprender o espectro de energia simulado [de moléculas](https://arxiv.org/abs/quant-ph/0604193), [materiais](https://arxiv.org/abs/1510.03859) ou [campo teorias](https://arxiv.org/abs/1111.3633v2) sem precisar comprometer nossa escolha de experimentos exigindo $t $ para ser um inteiro.

### <a name="random-walk-phase-estimation"></a>Estimativa de fase de passo aleatório ###

O Q # fornece uma aproximação útil de estimativa de fase de Bayesiana projetada para uso próximo de dispositivos Quantum que operam por condicionado uma movimentação aleatória no registro de dados obtido da estimativa de fase iterativa.
Esse método é adaptativo e totalmente determinístico, permitindo o dimensionamento quase ideal de erros na fase estimada $ \hat{\phi} $ com sobrecargas de memória muito baixas.

O protocolo usa um método de inferência Bayesiana aproximado que assume que a distribuição anterior é gaussiana.
Essa suposição gaussiana nos permite usar uma fórmula analítica para o experimento que minimiza a variância de posteriores.
Em seguida, o algoritmo, com base no resultado desse experimento, muda a estimativa de $ \phi $ para a esquerda ou direita por uma quantidade predeterminada e reduz a variância por um valor predeterminado.
Essa média e variância fornecem todas as informações necessárias para especificar um gaussiano anterior em $ \phi $ para o próximo experimento.
Falhas de medição inesperadas ou o resultado real que está nas caudas do início anterior, pode causar a falha desse método.
Ele se recupera de uma falha executando experimentos para testar se a média atual e o desvio padrão são apropriados para o sistema.
Se não forem, o algoritmo fará uma etapa inversa da movimentação e o processo continuará.
A capacidade de avançar para trás também permite que o algoritmo Aprenda mesmo se o desvio padrão anterior inicial for inapropriately pequeno.

## <a name="calling-phase-estimation-algorithms"></a>Chamando algoritmos de estimativa de fase ##

Cada operação de estimativa de fase fornecida com o Q # Canon usa um conjunto diferente de entradas parametrizando a qualidade que solicitamos a estimativa final de $ \hat{\phi} $.
No entanto, essas várias entradas compartilham várias entradas em comum, de modo que o aplicativo parcial nos parâmetros de qualidade resulta em uma assinatura comum.
Por exemplo, a operação de <xref:microsoft.quantum.characterization.robustphaseestimation> discutida na próxima seção tem a seguinte assinatura:

```qsharp
operation RobustPhaseEstimation(bitsPrecision : Int, oracle : DiscreteOracle, eigenstate : Qubit[])  : Double
```

A entrada `bitsPrecision` é exclusiva para `RobustPhaseEstimation`, enquanto `oracle` e `eigenstate` estão em comum.
Assim, como visto no **H2Sample**, uma operação pode aceitar um algoritmo de estimativa de fase iterativa com uma entrada do formulário `(DiscreteOracle, Qubit[]) => Unit` para permitir que um usuário especifique algoritmos de estimativa de fase arbitrária:

```qsharp
operation H2EstimateEnergy(
    idxBondLength : Int, 
    trotterStepSize : Double,
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double)) 
: Double
```

Esses algoritmos de estimativa de inúmeras fases são otimizados para diferentes propriedades e parâmetros de entrada, que devem ser compreendidos para fazer a melhor escolha para o aplicativo de destino. Por exemplo, alguns algoritmos de estimativa de fase são adaptáveis, o que significa que as etapas futuras são controladas de maneira clássica pelos resultados das medidas anteriores. Alguns exigem a capacidade de exponentiater seu Oracle unitário de caixa preta com potências reais arbitrárias e outros exigem apenas potências de inteiros, mas só podem resolver um módulo de estimativa de fase $2 \ PI $. Alguns exigem muitos auxiliar qubits e outros exigem apenas um.

Da mesma forma, o uso da estimativa de fase de busca aleatória prossegue praticamente da mesma forma que para outros algoritmos fornecidos com a Canon:

```qsharp
operation ExampleOracle(eigenphase : Double, time : Double, register : Qubit[]) : Unit
is Adj + Ctl {
    Rz(2.0 * eigenphase * time, register[0]);
}

operation BayesianPhaseEstimationCanonSample(eigenphase : Double) : Double {

    let oracle = ContinuousOracle(ExampleOracle(eigenphase, _, _));
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
