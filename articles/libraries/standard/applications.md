---
title: 'P # bibliotecas padrão – aplicativos | Microsoft Docs'
description: Bibliotecas padrão Q#
author: QuantumWriter
uid: microsoft.quantum.libraries.applications
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: ef22460a5bca63ebaf32c0ba21984e103ec8ebdd
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864394"
---
# <a name="applications"></a>Aplicações #

## <a name="hamiltonian-simulation"></a>Simulação Hamiltoniana ##

A simulação de sistemas Quantum é um dos aplicativos mais empolgantes da computação Quantum.
Em um computador clássico, a dificuldade de simular a mecânica quantum, em geral, é dimensionada com a dimensão $N $ de sua representação de vetor de estado.
Como essa representação aumenta exponencialmente com o número de $n $ qubits $N = 2 ^ n $, uma característica conhecida também conhecida como o tempo [de indimensão](xref:microsoft.quantum.concepts.multiple-qubits), a simulação da Quantum no hardware clássico é inmanejável.

No entanto, a situação pode ser muito diferente no hardware Quantum. A variação mais comum da simulação do Quantum é chamada de problema de simulação de Hamiltonian de tempo independente. Lá, é fornecida uma descrição do sistema Hamiltonian $H $, que é uma matriz Hermitian, e algum estado inicial de Quantum $ \ket{\psi (0)} $ que é codificado de acordo com a $n $ qubits em um computador Quantum. Como os Estados da Quantum em sistemas fechados evoluem na equação Schrödinger $ $ \begin{align} i\frac {d \ket{\psi (t)}} {d t} & = H \ket{\psi (t)}, \end{align} $ $ o objetivo é implementar o operador de evolução temporal $U (t) = e ^ {-iHt} $ em um período fixo $t $ , em que $ \ket{\psi (t)} = U (t) \ket{\psi (0)} $ resolve a equação Schrödinger.
De forma semelhante, o problema de simulação de Hamiltonian dependente de tempo resolve a mesma equação, mas com $H (t) $ agora é uma função de tempo.

A simulação de Hamiltonian é um componente importante de muitos outros problemas de simulação de Quantum, e soluções para o problema de simulação de Hamiltonian são algoritmos que descrevem uma sequência de Gates de Quantum primitivo para sintetizar um aproximar unitário $ \tilde{U} $ com erro $\\| \tilde{U}-U (t)\\| \le \epsilon $ na [norma Spectral](xref:microsoft.quantum.concepts.matrix-advanced). A complexidade desses algoritmos depende muito de como uma descrição dos Hamiltonian de interesse é disponibilizada por um computador Quantum. Por exemplo, na pior das hipóteses, se $H $ agindo em $n $ qubits fosse fornecida como uma lista de $2 ^ n \times 2 ^ n $ Numbers, uma para cada elemento de matriz, simplesmente ler os dados já exigiria tempo exponencial. Na melhor das hipóteses, é possível assumir o acesso a um unitário de caixa preta que $O \ket{t}\ket{\psi (0)} = \ket{t}U (t) \ket{\psi (0)} $ resolve o problema de forma trivial. Nenhum desses modelos de entrada é particularmente interessante – o primeiro, pois não é melhor do que as abordagens clássicas, e a última opção é que a caixa preta oculta a complexidade do portão primitivo de sua implementação, que poderia ser exponencial no número de qubits.

### <a name="descriptions-of-hamiltonians"></a>Descrições de Hamiltonians ###

Portanto, as suposições adicionais do formato da entrada são necessárias. Um equilíbrio fino deve ser riscado entre os modelos de entrada que são suficientemente descritivos para abranger Hamiltonians interessantes, como aqueles para sistemas físicos realísticos ou problemas computacionais interessantes e modelos de entrada que são suficientemente restritivos ser implementado de forma eficiente em um computador Quantum. Uma variedade de modelos de entrada não triviais pode ser encontrada na literatura e varia de Quantum para clássico. 

Como exemplos de modelos de entrada Quantum, [a simulação de Hamiltonian baseada em amostras](http://www.nature.com/articles/s41534-017-0013-7) assume o acesso de caixa preta a operações Quantum que produzem cópias de uma matriz de densidade $ \rho $, que são levadas a Hamiltonian $H $. No [modelo de acesso unitário](https://arxiv.org/abs/1202.5822) , um pressupõe que o Hamiltonian, em vez disso, é decomposto em uma soma de unidades $ $ \begin{align} H & = \sum ^ {d-1}\_{j = 0} a\_j \hat{U}\_j, \end{Align} $ $, em que $a\_j > 0 $ são coeficientes e $ \hat{U}\_j $ são unidades. Em seguida, supõe-se que um tenha acesso de caixa preta ao Oracle $V unitário = \sum ^ {d-1}\_{j = 0} \ket{j}\bra{j}\otimes \hat{U}\_j $ que selecione o $ \hat{U}\_j $ desejado, e o Oracle $A \ket{0}= \sum ^ {d-1}\_{j = 0} \sqrt{a\_j/\ Sum ^ {d-1}\_{k = 0} \alpha\_j} \ket{j} $ que criam uma codificação de estado Quantum com esses coeficientes. No caso da [simulação de Hamiltonian esparsa](https://arxiv.org/abs/quant-ph/0301023), uma assume que o Hamiltonian é uma matriz esparsa com apenas $d = \mathcal{O} (\Text{polylog} (N)) $ non-zero elemento em cada linha. Além disso, um assume a existência de circuitos Quantum eficientes que geram o local desses elementos diferentes de zero, bem como os respectivos valores. A complexidade dos [algoritmos de simulação de Hamiltonian](xref:microsoft.quantum.more-information) é avaliada em termos de número de consultas a essas caixas pretas, e a complexidade do portão primitivo depende muito da dificuldade de implementar essas caixas pretas.

> [!NOTE]
> A notação de Big-o geralmente é usada para descrever o dimensionamento da complexidade dos algoritmos. Dadas duas funções reais $f, g $, a expressão $g (x) = \mathcal{O} (f (x)) $ significa que existe uma constante positiva absoluta $x\_0, c > 0 $ de modo que $g (x) \le c f (x) $ para todos os $x \ge x\_$0. 

Na maioria dos aplicativos práticos a serem implementados em um computador Quantum, essas caixas pretas devem ser implementadas de forma eficiente, ou seja, com as Gates $ \mathcal{O} (\Text{polylog} (N)) $ Primitive Quantum. De forma mais forte, simulable Hamiltonians deve ter uma descrição clássica suficientemente esparsa. Em uma dessas formulações, supõe-se que Hamiltonian é decomposto de uma soma de Hermitian partes $ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} H_j.
\end{align} $ $ mais, presume-se que cada parte, um Hamiltonian $H\_j $, seja fácil de simular. Isso significa que o unitário $e ^ {-iH\_j t} $ para qualquer hora $t $ pode ser implementado exatamente usando as Gates $ \mathcal{O} (1) $ Primitive Quantum. Por exemplo, isso é verdadeiro no caso especial em que cada $H\_j $ são operadores de Pauli locais, o que significa que eles são de produtos tensor de $ \mathcal{O} (1) $ não Identity Pauli Operators que atuam em qubits de fechamento espacial. Esse modelo é particularmente aplicável a sistemas físicos com interação vinculada e local, uma vez que o número de termos é $d = \mathcal{O} (\Text{polylog} (N)) $ e pode ser escrito claramente, ou seja, descrito de forma clássica, em tempo polinomial.

> [!TIP]
> Hamiltonians que decompõem uma soma de partes podem ser descritos usando a biblioteca de representação do gerador dinâmico. Para obter mais informações, consulte a seção representação do gerador dinâmico em [estruturas de dados](xref:microsoft.quantum.libraries.data-structures).

### <a name="simulation-algorithms"></a>Algoritmos de simulação ###

Um algoritmo de simulação do Quantum converte uma determinada descrição de um Hamiltonian em uma sequência de Gates de Quantum primitivos que, como um todo, uma evolução de tempo aproximada disse Hamiltonian.

No caso especial em que o Hamiltonian é decomposto em uma soma de partes Hermitian, a decomposição Trotter-Suzuki é um algoritmo especialmente simples e intuitivo para simular Hamiltonians que decompõem uma soma de componentes Hermitian. Por exemplo, um integrador de primeiro pedido desta família aproxima $ $ \begin{align} U (t) & = \left (e ^ {-iH\_0 t/r} e ^ {-iH\_1 t/r} \cdots e ^ {-iH\_{d-1} t/r} \right) ^ {r} + \mathcal{O} (d ^ 2 \ max_j\\| H\_j\\| ^ 2 t ^ 2/r), \end{align} $ $ usando um produto de $r d $ termos. 

> [!TIP]
> Os aplicativos do algoritmo de simulação Trotter-Suzuki são abordados nos exemplos.
> Para o modelo Ising usando apenas as operações intrínsecas fornecidas por cada computador de destino, consulte o [exemplo **SimpleIsing** ](https://github.com/microsoft/Quantum/blob/master/samples/simulation/ising/simple).
> Para o modelo Ising usando a estrutura de controle de biblioteca Trotter-Suzuki, consulte o [exemplo **IsingTrotter** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/trotter-evolution).
> Para molecular Hydrogen usando a estrutura de controle de biblioteca Trotter-Suzuki, consulte o exemplo de [ **simulação H2** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line).

Em muitos casos, gostaríamos de implementar o algoritmo de simulação, mas não estamos interessados nos detalhes de sua implementação. Por exemplo, o integrador de segunda ordem aproxima $ $ \begin{align} U (t) & = \left (e ^ {-iH\_0 t/2R} e ^ {-iH\_1 t/2R} \cdots e ^ {-iH\_{d-1} t/2R} e ^ {-iH\_{d-1} t/2R} \cdots e ^ {-iH\_1 t/2R} e ^ {-iH\_0 t/2R} \right) ^ {r} + \mathcal{O} (d ^ 3 \ max_j\\| H\_j\\| ^ 3 t ^ 3/r ^ 2), \end{align} $ $ usando um produto de $2rd $ termos. Ordens maiores envolverão ainda mais termos e variantes otimizadas podem exigir ordenações altamente não triviais em exponencials. Outros algoritmos avançados também podem envolver o uso de ancilla qubits em etapas intermediárias. Portanto, empacotamos algoritmos de simulação na Canon como o tipo definido pelo usuário

```qsharp
newtype SimulationAlgorithm = ((Double, EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl);
```

O primeiro parâmetro `Double` é a hora da simulação, o segundo parâmetro `EvolutionGenerator`, abordado na seção representação do gerador dinâmico de [estruturas de dados](xref:microsoft.quantum.libraries.data-structures), é uma descrição clássica de um Hamiltonian de tempo independente fornecido com instruções sobre como cada termo no Hamiltonian pode ser simulado por um circuito Quantum. Tipos desse formulário aproximam a operação de unitário $e ^ {-iHt} $ no terceiro parâmetro `Qubit[]`, que é o registro que armazena o estado Quantum do sistema simulado. Da mesma forma, para o caso dependente de tempo, definimos um tipo definido pelo usuário com um `EvolutionSchedule` tipo, que é uma descrição clássica de um Hamiltonian dependente de tempo.

```qsharp
newtype TimeDependentSimulationAlgorithm = ((Double, EvolutionSchedule, Qubit[]) => Unit : Adjoint, Controlled);
```

Por exemplo, a decomposição Trotter-Suzuki pode ser chamada usando as seguintes funções de Canon, com parâmetros `trotterStepSize` modificando a duração da simulação em cada exponencial e `trotterOrder` para a ordem do integrador desejado.

```qsharp
function TrotterSimulationAlgorithm(
    trotterStepSize: Double, 
    trotterOrder: Int) 
    : SimulationAlgorithm {
    ...
}
function TimeDependentTrotterSimulationAlgorithm(
    trotterStepSize: Double, 
    trotterOrder: Int) 
    : TimeDependentSimulationAlgorithm {
    ...
}
```

> [!TIP]
> Os aplicativos da biblioteca de simulação são abordados nos exemplos. Para estimativa de fase no modelo Ising usando `SimulationAlgorithm`, consulte o exemplo [ **IsingPhaseEstimation** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation).
> Para a preparação do estado adiabatic no modelo Ising usando `TimeDependentSimulationAlgorithm`, consulte o [exemplo **AdiabaticIsing** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/adiabatic).


### <a name="adiabatic-state-preparation--phase-estimation"></a>Estimativa de estado de adiabatic de & fase de preparação ###

Um aplicativo comum de simulação de Hamiltonian é a preparação do estado adiabatic. Aqui, um é fornecido com dois Hamiltonians $H\_{\Text{Start}} $ e $H\_{\Text{end}} $ e um estado Quantum $ \ket{\psi (0)} $ que é um estado de aterramento da Hamiltonian $H\_{\Text{Start}} $. Normalmente, $H\_{\Text{Start}} $ é escolhido de modo que $ \ket{\psi (0)} $ seja fácil de se preparar de um estado de base computacional $ \ket{0\cdots 0} $. Ao fazer a interpolação entre esses Hamiltonians no problema de simulação dependente de tempo de forma suficientemente lenta, é possível terminar, com alta probabilidade, em um estado de terra do Hamiltonian final $H\_{\Text{end}} $. Embora a preparação de uma boa aproximação para os Estados de aterramento Hamiltonian possa continuar dessa maneira chamando os algoritmos de simulação de Hamiltonian dependentes de tempo como uma sub-rotina, outras abordagens conceitualmente diferentes, como a Quantum de variação eigensolver são possíveis.

Outro aplicativo onipresente no quantum química é estimar a energia de estado do solo de Hamiltonians que representa as etapas intermediárias da reação química. Tal esquema poderia, por exemplo, contar com a preparação do estado adiabatic para criar o estado do solo e, em seguida, incorporar a simulação de Hamiltonian de tempo independente como uma sub-rotina na caracterização da estimativa de fase para extrair essa energia com um erro finito e probabilidade de sucesso. 

Abstrair algoritmos de simulação como os tipos definidos pelo usuário `SimulationAlgorithm` e `TimeDependentSimulationAlgorithm` nos permite incorporar convenientemente sua funcionalidade a algoritmos Quantum mais sofisticados. Isso nos motiva a fazer o mesmo para essas sub-rotinas usadas com frequência.

Portanto, definimos a função conveniente

```qsharp
function InterpolatedEvolution(
        interpolationTime: Double, 
        evolutionGeneratorStart: EvolutionGenerator,
        evolutionGeneratorEnd: EvolutionGenerator,
        timeDependentSimulationAlgorithm: TimeDependentSimulationAlgorithm)
        : (Qubit[] => Unit is Adj + Ctl) {
        ...
}
 
```

Isso retorna uma operação unitário que implementa todas as etapas da preparação do estado adiabatic. O primeiro parâmetro `interpolatedTime` define o tempo sobre o qual interpolar linearmente entre o Hamiltonian inicial descrito pelo segundo parâmetro `evolutionGeneratorStart` e o final Hamiltonian descrito pelo terceiro parâmetro `evolutionGeneratorEnd`. O quarto parâmetro `timeDependentSimulationAlgorithm` é onde um faz a escolha do algoritmo de simulação. Observe que, se `interpolatedTime` for longa o suficiente, um estado inicial de terra permanecerá um estado de aterramento instantâneo da Hamiltonian durante toda a duração da simulação dependente de tempo e, portanto, terminará no estado de terra do Hamiltonian final.

Também definimos uma operação útil que executa automaticamente todas as etapas de um experimento típico de química da Quantum. Por exemplo, temos o seguinte, que retorna uma estimativa de energia do estado produzido pela preparação do estado adiabatic:

```qsharp
operation AdiabaticStateEnergyEstimate( 
    nQubits : Int, 
    statePrepUnitary: (Qubit[] => Unit),
    adiabaticUnitary: (Qubit[] => Unit),
    qpeUnitary: (Qubit[] => Unit is Adj + Ctl),
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double)) 
    : Double {
...
}
```

`nQubits` é o número de qubits usado para codificar o estado inicial do Quantum. `statePrepUnitary` prepara o estado de início da base computacional $ \ket{0\cdots 0} $. `adiabaticUnitary` é a operação unitário que implementa a preparação do estado adiabatic, como produzida pela função `InterpolatedEvolution`. `qpeUnitary` é a operação unitário que é usada para executar a estimativa de fase no estado resultante do Quantum. `phaseEstAlgorithm` é nossa escolha de algoritmo de estimativa de fase.

> [!TIP]
> Os aplicativos da preparação do estado adiabatic são abordados nos exemplos. Para o modelo Ising usando uma implementação manual da preparação do estado adiabatic versus usando a função `AdiabaticEvolution`, consulte o [exemplo **AdiabaticIsing** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/adiabatic).
> Para estimativa de fase e preparação do estado adiabatic no modelo Ising, consulte o [exemplo **IsingPhaseEstimation** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation).

> [!TIP]
> A [simulação de molecular Hydrogen](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line) é uma amostra interessante e breve. O modelo e os resultados experimentais relatados em [' Malley et. al.](https://arxiv.org/abs/1512.06860) requer apenas matrizes Pauli e usa a forma $ \hat H = g\_{0}I\_0I\_1 + g\_1 {Z\_0} + g\_2 {Z\_1} + g\_3 {Z\_0} {Z\_1} + g\_4 {Y\_0} {Y\_1} + g\_5 {X\_0} {X\_1} $. Esse é um Hamiltonian efetivo que só exige apenas 2 qubits, em que as constantes $g $ são computadas a partir da distância $R $ entre os dois Atoms Hydrogen. Usando as funções do Canon, os Paul são convertidos em unidades e, em seguida, evoluíram por curtos períodos de tempo usando a decomposição Trotter-Suzuki. Uma boa aproximação para o estado de terra $H _2 $ pode ser criada sem usar a preparação do estado adiabatic e, portanto, a energia do estado terrestre pode ser encontrada diretamente usando a estimativa de fase da Canon.

## <a name="shors-algorithm"></a>Algoritmo de Shor ##
O algoritmo do Atal continua sendo um dos desenvolvimentos mais significativos na computação Quantum, pois ele mostrou que os computadores Quantum podem ser usados para resolver problemas importantes e, no momento, inmanejáveis.
O algoritmo do Atal fornece uma maneira rápida de fatorar números grandes usando um computador Quantum, um problema chamado de *fatoração*.
A segurança de muitos cryptosystems de hoje é baseada na suposição de que não existe um algoritmo rápido para fatoração.
Portanto, o algoritmo de Atal teve um impacto profundo em como pensamos na segurança em um mundo posterior.

O algoritmo do Atal pode ser considerado como um algoritmo híbrido.
O computador Quantum é usado para executar uma tarefa de computação física conhecida como descoberta de períodos.
Os resultados da localização do período são então processados de uma estimativa para estimar os fatores.
Examinamos essas duas etapas abaixo.

### <a name="period-finding"></a>Localização do período ###

Depois de ver como o trabalho de transformação de Fourier de Quantum e a estimativa de fase (consulte [algoritmos de Quantum](xref:microsoft.quantum.libraries.standard.algorithms)), podemos usar essas ferramentas para resolver um problema computacional de forma clássica, chamado *localização de períodos*.  Na próxima seção, veremos como aplicar a localização do período à fatoração.

Considerando dois inteiros $a $ e $N $, em que $a < N $, a meta do período que localiza, também chamada de Order Localization, é encontrar a _ordem_ $r $ of $a $ módulo $N $, em que $r $ é definido para ser o inteiro mínimo positivo, de forma que $a ^ r \equiv 1 \Text{mod} N $.  

Para localizar o pedido usando um computador Quantum, podemos usar o algoritmo estimativa de fase aplicado ao operador unitário a seguir $U _a $: $ $ U_a \ket{x} \equiv \ket{(AX) \Text{mod} N}. $ $ eigenvectors de $U _a $ são para Integer $s $ e $0 \ Leq s \leq r-$1, $ $ \ket{x_s} \equiv 1/\sqrt{r} \sum\_{k = 0} ^ {r-1} e ^ {\frac{-2\pi i SK} {r}} \ket{a ^ k\text {mod} N}, $ $ são _eigenstates_ de $U _A $.
O eigenvalues de $U _a $ $ U\_um \ket{x\_s} = e ^ {2 \ Pi i s/r} \ket{x\_s}. $$

A estimativa de fase gera, portanto, o eigenvalues $e ^ {2 \ Pi i s/r} $, do qual $r $ pode ser aprendido com eficiência usando as [frações contínuas](https://en.wikipedia.org/wiki/Continued_fraction) de $s/r $.

O diagrama de circuito para localização do período Quantum é:

![](./../../media/QPE.svg)

Aqui, $2n $ qubits são inicializados para $ \ket{0}$ e $n $ qubits são inicializados para $ \ket{1}$.
O leitor pode imaginar novamente por que o Quantum Register para manter o eigenstates é inicializado para $ \ket{1}$.
Como não sabemos a ordem $r $ antecipadamente, não podemos realmente preparar $ \ket{x_s} $ States diretamente.
Felizmente, acontece que $1/\ sqrt {r} \sum\_{s = 0} ^ {r-1} \ket{x\_s} = \ket{1}$.
Não precisamos realmente preparar $ \ket{x} $!
Podemos apenas preparar um registro Quantum de $n $ qubits no estado $ \ket{1}$. 

O circuito contém o QFT e vários Gates controlados.
O portão QFT foi descrito [anteriormente](xref:microsoft.quantum.libraries.standard.algorithms).
O $U controlado _a Gate mapeia $ \ket{x} $ para $ \ket{(AX) \Text{mod} N} $ se o controle qubit for $ \ket{1}$ e mapear $ \ket{x} $ para $ \ket{x} $ caso contrário.

Para atingir $ (a ^ NX) \Text{mod} N $, podemos simplesmente aplicar controlled-$U _ {a ^ N} $, em que calculamos $a ^ N \Text{mod} N $ de forma clássica para conectar-se ao circuito Quantum.  
Os circuitos para atingir esse tipo de aritmética de modulação foram descritos na [documentação aritmética do Quantum](./algorithms.md#arithmetic), especificamente exigimos um circuito de exponenciação modular para implementar as operações de $U controlado\_{a ^ i} $.

Enquanto o circuito acima corresponde à [estimativa da fase Quantum](xref:microsoft.quantum.characterization.quantumphaseestimation) e habilita explicitamente a localização da ordem, podemos reduzir o número de qubits necessário. Podemos seguir o método de Beauregard para a localização de pedidos, conforme descrito [na página 8 de arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8), ou use uma das rotinas de estimativa de fase disponível em Microsoft. Quantum. Canon. Por exemplo, a [estimativa de fase robusta](xref:microsoft.quantum.characterization.robustphaseestimation) também usa um qubit extra.
 
### <a name="factoring"></a>Cálculo ###
A meta de fatoração é determinar os dois fatores primos de Integer $N $, em que $N $ é um número de $n $-bit.  
A fatoração consiste nas etapas descritas abaixo. As etapas são divididas em três partes: uma rotina de pré-processamento clássica (1-4); uma rotina de computação Quantum para localizar a ordem de $a \Text{mod} N $ (5); e uma rotina de pré-processamento clássica para derivar os fatores primos da ordem (6-9).

A rotina de pré-processamento clássica consiste nas seguintes etapas:
1. Se $N $ for par, retorne o fator principal $2 $.
2. Se $N = p ^ q $ para $p \geq1 $, $q \geq2 $, retorne o fator principal $p $.  Esta etapa é executada de clássico.
3. Escolha um número aleatório $a $ de $1 < um < N-$1.
4. Se $ \Text{GCD} (a, N) > 1 $, retorne o fator principal $ \Text{GCD} (a, N) $. Esta etapa é calculada usando o algoritmo do Euclid.
Se nenhum fator principal tiver sido retornado, continuamos para a rotina Quantum:
5. Chame o algoritmo do período Quantum que localiza para calcular a ordem $r $ de $a \Text{mod} N $. Use $r $ na rotina de pré-processamento clássica para determinar os principais fatores:
6. Se $r $ for ímpar, volte para a etapa de pré-processamento (3).
7. Se $r $ for par e $a ^ {r/2} =-1 \ Text {mod} N $, volte para a etapa de pré-processamento (3).
8. Se $ \Text{GCD} (a ^ {r/2} + 1, N) $ for um fator não trivial de $N $, retorne $ \Text{GCD} (um ^ {r/2} + 1, N) $.
9. Se $ \Text{GCD} (a ^ {r/2}-1, N) $ for um fator não trivial de $N $, retorne $ \Text{GCD} (um ^ {r/2}-1, N) $.


O algoritmo de fatoração é probabilística: pode ser mostrado que, com probabilidade, pelo menos uma metade que $r $ será par e $a ^ {r/2} \neq-1 \Text{mod} N $, produzindo assim um fator primo.  (Consulte o [artigo original do Atal](https://doi.org/10.1109/SFCS.1994.365700) para obter detalhes ou um dos textos *básicos de computação Quantum* no para obter [mais informações](xref:microsoft.quantum.more-information)).
Se um fator principal não for retornado, basta repetir o algoritmo da etapa (1).  Após $n $ tentativas, a probabilidade de que cada tentativa tenha falha é no máximo $2 ^ {-n} $.
Assim, depois de repetir o algoritmo, um número pequeno de vezes o sucesso é praticamente garantido.
