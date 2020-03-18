---
title: 'Algoritmos quânticos em Q #'
description: Aprenda sobre algoritmos fundamentais de computação quântica, incluindo amplificação de amplitude, fourier transform, draper e beauregard adders, e estimativa de fase.
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.algorithms
ms.openlocfilehash: 8b8a9019e8bc419f42b0c6f7558354d19a157917
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79402855"
---
# <a name="quantum-algorithms"></a>Algoritmos Quânticos #

## <a name="amplitude-amplification"></a>Amplificação de Amplitude ##

*A Amplificação amplitude* é uma das ferramentas fundamentais da Computação Quântica. É a ideia fundamental que está subjacente à pesquisa, estimativa de amplitude de Grover e muitos algoritmos de aprendizagem automática quântica.  Existem muitas variantes, e em Q# fornecemos uma versão geral baseada na Amplificação de Amplitude Alheia com Reflexões Parciais para permitir a maior área de aplicação.

A ideia central por trás da amplificação da amplitude é amplificar a probabilidade de um resultado desejado ocorrer através da realização de uma sequência de reflexões.  Estas reflexões giram o estado inicial mais próximo de um estado-alvo desejado, muitas vezes chamado de estado marcado.  Especificamente, se a probabilidade de medir o estado inicial para estar em estado marcado é $\sin^2(\theta)$ então depois de aplicar amplificação de amplitude $m$ vezes a probabilidade de sucesso se torna $\sin^2 ((2m+1)\theta)$.  Isto significa que se $\theta = \pi/[2(2n+1)] $ por algum valor de $n$ então a amplificação amplitude é capaz de aumentar a probabilidade de sucesso para $100\\%$ após $n de iterações de amplificação amplitude.  Uma vez que $\teta = \sin^{-1}(\sqrt{\Pr(sucesso)}}}$isto significa que o número de iterações necessárias para obter um sucesso determinicamente é quadraticamente inferior ao número esperado necessário para encontrar um estado marcado não determinicamente usando amostras aleatórias.

Cada iteração da amplificação amplitude requer que sejam especificados dois operadores de reflexão. Especificamente, se $Q$ é o iterato de amplificação amplitude e $P_0$ é um operador de projetor no subespaço inicial e $P_1$ é o projetor sobre o subespaço marcado e ntão $Q=-(\boldone-2P_0)(\boldone -2P_1)$.  Recorde-se que um projetor é um operador hermitiano que tem valores eigenvalues $+1$ e $0$ e, como resultado, $(\boldone -2P_0)$ é unitário porque tem valores eigen que são raízes de unidade (neste caso $\pm $1$). Como exemplo, considere o caso da pesquisa de Grover com o estado inicial $H^{\otimes n} \ket{0}$ e estado marcado $\ket{m}$, $P_0 = H^{\otimes n}\ket{0}\bra{0}H^{\otimes n}$ e $P_1= \ket{m}\bra{m}$.  Na maioria das aplicações de amplificação de amplitude $P_0$ será um projetor para um estado inicial, o que significa que $P_0 = \boldone -2\ket{\psi}\bra{\psi}$ para algum vetor $\ket{\psi}$; no entanto, para a amplicação de amplitude alheia $P_0$ irá normalmente projetar em muitos estados quânticos (isto é, a multiplicidade do valor eigenvalue de $+1$ de $P_0$ é superior a $1$).

A lógica por trás da amplificação amplitude segue diretamente da decomposição eigen de $Q$.  Especificamente, os eigenvectores de $Q$ que o estado inicial tem suporte não zero podem ser mostrados como combinações lineares dos eigenvectores de $+1$ de $P_0$ e $P_1$.  Especificamente, o estado inicial de amplificação de amplitude (assumindo que é um eigenvector de $P_0$) pode ser escrito como $$ \ket{\psi}=\{-i}{{-i}{{{-i}{{{-i}{{sqrt{2}}\left (e^{i\theta}\ket{\psi_+} + e^{-i\\theta}\ket{\psi_-}\right), $$ket{\psi_\pm}$ são eigenvectores de $Q$ com valores eigen$e{^pm 2i\theta}$ e só têm suporte nos $+1$ eigenvectors de $P_0$ e $P_1$.  O facto de os valores eigen are$e^{\pm i \theta}$ implica que o operador $Q$ realiza uma rotação num subespaço bidimensional especificado pelos dois projetores e o estado inicial em que o ângulo de rotação é $2\theta$.  É por isso que após $m as iterações de $Q$ a probabilidade de sucesso é $\sin^2([2m+1]\theta)$.

Outra propriedade útil que sai disto é que o eigenvalue $\theta$ está diretamente relacionado com a probabilidade de o estado inicial ser marcado (no caso em que $P_0$ é um projetor apenas para o estado inicial).  Uma vez que as fases eigenphases de $Q$ são $2\teta = 2\sin{-1}(\sqrt{\Pr(sucesso)}}$ então segue-se que se aplicarmos estimativa de fase a $Q$ então podemos aprender a probabilidade de sucesso para um procedimento quântico unitário.  Isto é útil porque requer quadraticamente menos aplicações do procedimento quântico para aprender a probabilidade de sucesso do que seria necessário de outra forma.

Q# introduz a amplificação da amplitude como uma especialização da amplificação de amplitude alheia.  A amplificação de amplitude alheia ganha este apelido porque o projetor no espaço eigenspace inicial não precisa ser um projetor sobre o estado inicial.  Neste sentido, o protocolo é alheio ao estado inicial.  A aplicação chave da amplificação de amplitude alheia está em certas *combinações lineares de* métodos de simulação unitária hamiltoniana, em que o estado inicial é desconhecido, mas fica enredado com um registo de acessórios no protocolo de simulação.  Se este registo acesso fosse medido como um valor fixo, digamos$0$, tais métodos de simulação aplicam a transformação unitária desejada aos restantes qubits (chamado registo do sistema).  Todos os outros resultados de medição conduzem, no entanto, ao fracasso.  A amplificação de amplitude alheia permite que a probabilidade de sucesso desta medição seja aumentada para $100\\%$ usando o raciocínio acima.  Além disso, a amplificação de amplitude comum corresponde ao caso em que o registo do sistema está vazio.  É por isso que Q# usa a amplificação de amplitude alheia como a sua subrotina de amplificação de amplitude fundamental.

A rotina geral (`AmpAmpObliviousByReflectionPhases`) tem dois registos a que chamamos `ancillaRegister` e `systemRegister`. Também aceita dois oráculos para as reflexões necessárias. O `ReflectionOracle` atua apenas no `ancillaRegister` enquanto o `ObliviousOracle` atua conjuntamente em ambos os registos. A entrada para `ancillaRegister` deve ser inicializada para um -1 eigenstate do primeiro operador de reflexão $\boldone -2P_1$.

Tipicamente, o oráculo prepara o estado na base computacional $\ket{0...0}$. Na nossa implementação, o `ancillaRegister` consiste de um qubit (`flagQubit`) que controla o `stateOracle` e o resto das auxiliares desejadas. O `stateOracle` é aplicado quando o `flagQubit` é $\ket{1}$.

Também se pode fornecer oráculos `StateOracle` e `ObliviousOracle` em vez de reflexões através de um apelo à `AmpAmpObliviousByOraclePhases`.

Como referido, a amplificação tradicional da Amplitude é apenas um caso especial destas rotinas em que `ObliviousOracle` é o operador de identidade e não existem qubits do sistema (isto é, `systemRegister` está vazio). Se desejar obter fases para reflexões parciais (por exemplo, para pesquisa de Grover), a função `AmpAmpPhasesStandard` está disponível. Por favor, consulte `DatabaseSearch.qs` para uma amostra de implementação do algoritmo de Grover.

Relacionamos as fases de rotação de um qubit às fases do operador de reflexão, tal como descrito no artigo pela [G.H. Low, I. L. Chuang](https://arxiv.org/abs/1707.05391). As fases fixas de pontos que são usadas são detalhadas em [Yoder, Low e Chuang](https://arxiv.org/abs/1409.3305) juntamente com as fases em [Low, Yoder e Chuang.](https://arxiv.org/abs/1603.03996)

Para segundo plano, pode começar a partir da [Amplificação Amplitude Padrão,](https://arxiv.org/abs/quant-ph/0005055) em seguida, passar para uma introdução à Amplificação amplitude [alheia](https://arxiv.org/abs/1312.1414) e, finalmente, generalizações apresentadas em [Low e Chuang](https://arxiv.org/abs/1610.06546). Uma bela apresentação geral de toda esta área (no que diz respeito à Simulação Hamiltonian) foi dada por [Dominic Berry.](http://www.dominicberry.org/presentations/Durban.pdf)

## <a name="quantum-fourier-transform"></a>Transformação quântica de fourier ##

A transformação de Fourier é uma ferramenta fundamental da análise clássica e é igualmente importante para as computações quânticas.
Além disso, a eficiência da *transformação quântica fourier* (QFT) supera em muito o que é possível numa máquina clássica tornando-a uma das primeiras ferramentas de escolha ao conceber um algoritmo quântico.

Como uma generalização aproximada do QFT, fornecemos a operação <xref:microsoft.quantum.canon.approximateqft> que permite mais otimizações através da poda de rotações que não são estritamente necessárias para a precisão algorítmica desejada.
O QFT aproximado requer a operação disadica $Z rotação de $<xref:microsoft.quantum.intrinsic.rfrac> bem como a operação <xref:microsoft.quantum.intrinsic.h>.
Presume-se que a entrada e a saída estão codificadas na codificação de grandes endianos--- ou seja, o qubit com índice `0` é codificado na parte mais esquerda (mais alta) da representação binária do inteiro.
Isto alinha-se com a [notação](xref:microsoft.quantum.concepts.dirac)de ket , como um registo de três qubits no estado $\ket{100}$ corresponde a $q_0$ estando no estado $\ket{1}$ enquanto $q_1$ e $q_2$ estão ambos no estado $\ket{0}$.
O parâmetro de aproximação $a$ determina o nível de poda das rotações $Z$, ou seja, $a \in [0.n]$.
Neste caso, todos os $Z$-rotações $2\pi/2^k$ onde $k > a$ são removidos do circuito QFT.
Sabe-se que por $k \ge \log_2(n) + \log_2(1 / \epsilon) + 3$. pode-se vincular $\\[ ] \nome do operador{QFT} - \nome de operador{AQFT} \\\epsilon$.
Aqui $\\\cdot\\[$] é a norma do operador que neste caso é a raiz quadrada do maior [eigenvalue](xref:microsoft.quantum.concepts.matrix-advanced) de $(\operatorname{QFT} - \nome de operador{AQFT})(\nome de operador{QFT} - \nome de operador{AQFT}^\apunhala$.

## <a name="arithmetic"></a>Operações aritméticas ##

Tal como a aritmética desempenha um papel central na computação clássica, também é indispensável na computação quântica.  Algoritmos como o algoritmo de factoring de Shor, métodos de simulação quântica, bem como muitos algoritmos oraculares dependem de operações aritméticas coerentes.  A maioria das abordagens para a aritmética se baseia maquetes em circuitos quânticos adder.  O adder mais simples pega numa entrada clássica $b$ e adiciona o valor a um estado quântico segurando um integer $\ket{a}$.  Matematicamente, o adder (que denotamos $\operatorname{Add}(b)$ para entrada clássica $b$) tem a propriedade que

$$ \operatorname{Add}(b)\ket{a}=\ket{a + b}.
$$ Este circuito básico de adder é mais um incrementador do que um adder.
Pode ser convertido num adder que tem duas inputs quânticas através de $$ \operatorname{Add}\ket{a}\ket{{{a}\ket{a+b}, $$ usando $n$ aplicações controladas de adders do formulário \start{align} \operatorname {Add} \ket{a} \ket{b} & = \Lambda\_{a\_0} \left (\operatorname{Add}(1) \Lambda\_{a\_1} \left (\operatorname{Add}(2) \right) \Lambda\_{a\_2} \left (\operatorname{Add}(4) \cdots \Lambda\_{a\_{n-1}} \left nome de operador{Add}({{n-1}}) \right) \ket{a}\ket{b} \\\\ & = \ket{a} \ket{b + a}, \end{align} para $n inteiros de bit de $bit $a$ e $b$ e adição de modulo $2^n$.  Recorde-se que a notação $\Lambda\_x(A)$ refere-se, para qualquer operação $A$, à versão controlada dessa operação com o qubit $x$ como controlo.

Da mesma forma, a multiplicação clássica controlada (uma forma modular da qual é essencial para o algoritmo de factoring de Shor) pode ser realizada utilizando uma série semelhante de adições controladas: \start{align} \operatorname{Mult}(a)\ket{x}\ket{b} & = \Lambda\_{x\_0}\left(\operatorname{Add}(2^0 a)\direita) \Lambda\_{a\_1}\left(\operatorname {Add}(2^1a)\direita) \Lambda\_{a\_2}\left (\operatorname{Add}(2^2 a)\à direita) \cdots \Lambda\_{x\_n-1}} \left (\operatorname{Add}({2^{n-1}a) \right)\ket{x}\ket{b} \\\\ & = \ket{x}\ket{b+ax}.
\end{align} Existe uma subtileza com multiplicação nos computadores quânticos que pode notar a partir da definição de $\operatorname{Mult}$ acima.  Ao contrário da adição, a versão quântica deste circuito armazena o produto das inputs num registo acessório e não no registo de entrada.  Neste exemplo, o registo é inicializado com o valor $b$, mas normalmente começará a deter o valor zero.  Isto é necessário porque, em geral, não há um inverso multiplicador para $a gerais e $x$.  Uma vez que todas as operações quânticas, exceto a medição, são reversíveis, precisamos de manter informação suficiente para inverter a multiplicação.  Por esta razão, o resultado é armazenado numa matriz separada.  Este truque de salvar a saída de uma operação irreversível, como a multiplicação, num registo separado é conhecido como o "truque Bennett" depois de Charlie Bennett e é uma ferramenta fundamental na computação reversível e quântica.

Muitos circuitos quânticos foram propostos para adição e cada um explora uma compensação diferente em termos do número de qubits (espaço) e do número de operações do portão (tempo) necessários.  Revemos dois adders altamente eficientes em termos de espaço abaixo conhecidos como o adder Draper e o adder Beauregard.

### <a name="draper-adder"></a>Draper Adder ###

O adder Draper é indiscutivelmente um dos mais elegantes adders quânticos, uma vez que invoca diretamente propriedades quânticas para realizar a adição.  A perceção por trás do adder Draper é que a transformação de Fourier pode ser usada para traduzir mudanças de fase em uma pequena mudança.  Segue-se que aplicando uma transformação fourier, aplicando turnos de fase apropriados, e, em seguida, desfazer a transformação fourier você pode implementar um adder.  Ao contrário de muitos outros adders que foram propostos, o adder Draper usa explicitamente os efeitos quânticos introduzidos através da transformação quântica fourier.  Não tem uma contrapartida clássica natural.  Os passos específicos do adder Draper são dados abaixo.

Assuma que tem dois registos de qubit de $n$bits armazenando os inteiros $a$ e $b$ então para todos os $a$ $$ \operatorname{QFT}\ket{a}= \frac{1}{\sqrt{2^n}}}}\sum\_{j=0}^{2^n-1} e^{i2\pi(aj)/2^n} \ket{j}.
$$ Se definirmos $$ \ket {\phi\_k(a)} = \frac{1}{\sqrt{2}}\left (\ket{0} + e^{i2\pi a /2^k}\ket{1} \right), $$ e depois alguma álgebra pode ver que $$ \operatorname{QFT}\ket{a}=\ket{\phi\_1(a)}\otimes \cdots \otimes \ket{\phi\_(a)}.
$$ O caminho para a realização de um adder torna-se claro depois de observar que a soma das inputs pode ser escrita como $$ \ket{a+b}=\operatorname{QFT}^{-1}\ket{\phi\_1(a+b)}\otimes \cdots \otimes \ket{\phi\_n (a+b)}.
$$ Os inteiros $b$ e $a$ podem então ser adicionados através da realização de rotação de fase controlada em cada um dos qubits na decomposição usando os pedaços de $b$ como controlos.

Esta expansão pode ser simplificada notando que para qualquer $j de sempre e número real $x$, $e^{i2\pi(x+j)}=e^{i2\pi x}$.  Isto porque se rodar $360^{\circ}$ graus ($2\pi$$ radians) em círculo, então você acaba precisamente onde você começou.  A única parte importante de $x$ para $e^{i2\pi x}$ é, portanto, a parte fracionária de $x$.  Especificamente, se tivermos uma expansão binária da forma $x=y+0,x\_0x\_2\ldots x\_n$ e depois $e^{i2\pi x}=e^{i2\pi (0,x\_0x\_2\ldots x\_{n-1}}}}}}$e, portanto, $\ket{{i2\pi=e^{i2\pi (0,x  0x  2\ldots x  {n-1}}}}}}$e, portanto, $$\ket\_{{i2\pi=e^{i2\pi (0,x  0x  2\ldots x  {n-1})}}}$e, portanto, $\ket{{i2\pi=e^{i2\pi (0,x  0x  2\ldots x  {n-1}}}}}}}}}}}}}}}}}\frac{1}{\sqrt{2}}\left(\ket{0} + e^{i2\pi [a/2^k+0.b\_k\ldots b\_1]}\ket{1} \right).$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$ o número de rotações diminui à medida que $k$ diminui.  Isto reduz substancialmente o número de portões quânticos necessários no adder.  Denotamos a transformação fourier, a adição de fase e os passos de transformação inversa fourier que compõem o adder Draper como $\operatorname{QFT}^{-1} à esquerda (\phi\\\!\operatorname{ADD}\right) \nome de operador{QFT}$. Um circuito quântico que usa esta simplificação para implementar todo o processo pode ser visto abaixo.

![Adder draper mostrado como diagrama de circuito](~/media/draper.svg)

Cada portão controlado $e^{i2\pi/k}$ no circuito refere-se a um portão de fase controlada.  Tais portões têm a propriedade que no par de qubits em que atuam, $\ket{00}\mapsto \ket{00}$ mas $\ket{11}\mapsto e^{i2\pi/k}\ket{11}$.  Este circuito permite-nos realizar a adição sem qubits adicionais para além dos necessários para armazenar as inputs e as saídas.

### <a name="beauregard-adder"></a>Beauregard Adder ###

O adder Beauregard é um adder modular quântico que usa o adder Draper para executar adição de modulo $N$ para um valor arbitrário positivo inteiro $N$.  A importância dos adders modulares quânticos, como o adder Beauregard, decorre em grande parte da sua utilização no passo de exponenciação modular dentro do algoritmo de Shor para factoring.  Um adder modular quântico tem a seguinte ação para entrada quântica $\ket{b}$ e entrada clássica $a$ onde $a$ e $b$ são prometidos para serem inteiros mod $N$, o que significa que eles estão no intervalo $[0,\ldots, N-1]$.

$$ \ket{b}\rightarrow \ket{b+a \text { mod }N}=\begin{cases} \ket{b+a},& b+a < N\\\\ \ket{b+a-N},& (b+a)\ge N \end{cases}.
$$

O adder Beauregard usa o adder Draper, ou mais especificamente $\phi\\\!nome de operador {ADD}$, para adicionar $a$ e $b$ em fase.  Em seguida, utiliza a mesma operação para identificar se $a+b <N$ subtraindo $N$ e testando se $a+b-N<0$.  O circuito armazena esta informação num qubit acessório e adiciona $N$ de volta ao registo se $a+b<N$.  Conclui então, descomputando esta broca acessória (este passo é necessário para garantir que a cilla pode ser desalocado após chamar o adder).  O circuito para o adder Beauregard é dado abaixo.

![Beauregard adder mostrado como diagrama de circuito](~/media/beau.svg)

Aqui o portão $\Phi\\\!nome de operador{ADD}$ assume o mesmo formulário que $\phi\\\!nome de operador {ADD}$ exceto que neste contexto a entrada é clássica e não quântica.  Isto permite que as fases controladas em $\Phi\\\!o nome de operador {ADD}$ seja substituído por portões de fase que podem ser compilados em menos operações para reduzir tanto o número de qubits como o número de portões necessários para o adder.

Para mais detalhes, consulte [M. Roetteler, Th. Beth](http://doi.org/10.1007/s00200-008-0072-2 ) e [D. Coppersmith.](https://arxiv.org/abs/quant-ph/0201067)

### <a name="quantum-phase-estimation"></a>Estimativa da Fase Quântica ###

Uma aplicação particularmente importante da transformação quântica fourier é aprender os valores eigen dos operadores unitários, um problema conhecido como estimativa de *fase.*
Considere um $U unitário$ e um estado $\ket{\phi}$ tal que $\ket{\phi}$ é um estado eigene de $U$ com eigenvalue $\phi$, \start{equação} U\ket{\phi} = \phi\ket{\phi}.
\end{equation} Se tivermos apenas acesso a $U$ como um oráculo, então podemos aprender a fase $\phi$ utilizando que as rotações de $Z$ aplicadas ao alvo de uma operação controlada propagam-se de volta ao controlo.

Suponha que $V$ é uma aplicação controlada de $U$, de tal forma que \start{align} V (\ket{0} \otimes \ket{\phi}) & = \ket{0} \otimes \ket {\phi} \\\\ \textrm{ e } V (\ket{1} \otimes \ket {\phi}) & e{{i \phi} \ket{1} \otimes \ket {{}}
\end{align} Então, por linearidade, \start{align} V (\ket{+} \otimes \ket{\phi}) & = \frac{ (\ket{0} \otimes \ket{\phi}) + e^{i \phi} (\ket{1} \otimes \ket {\phi}) }{{sqrt{2}}.
\end{align} Podemos recolher termos para descobrir que \start{align} V (\ket{+} \otimes \ket{\phi}) & = \frac{\ket{0} + e^{i \phi} \ket{1}}{\sqrt{2}} \otimes \ket{\phi} \\\\ & = (R_1(\phi) \ket{+}) \otimes \ket{\phi}, \end{{} where $R_1$ é o unitário aplicado pelo funcionamento <xref:microsoft.quantum.intrinsic.r1>.
Dito de outra forma, o efeito de aplicar $V$ é precisamente o mesmo que aplicar $R_1$ com um ângulo desconhecido, mesmo que só tenhamos acesso a $V$ como um oráculo.
Assim, para o resto desta discussão discutiremos a estimativa de fase em termos de $R_1(\phi)$, que implementamos utilizando o chamado recuo de *fase*.

Uma vez que o registo de controlo e alvo permanece desemaranhado após este processo, podemos reutilizar $\ket{\phi}$ como alvo de uma aplicação controlada de $U^2$ para preparar um segundo qubit de controlo no estado $R_1(2 \phi) \ket{+}$.
Continuando desta forma, podemos obter um registo do formulário \begin{align} \ket{\psi} & = \sum_{j = 0}^n R_1(2^j \phi) \ket{{}} \\\\ & \propto \bigotimes_{j=0}^{n} \left (\ket{0} + \exp(i^{j} \phi) \ket{1}\right \\ \\\propto \sum_{k = 0}^{2^n - 1} \exp(i \phi k) \ket{k} \end{align} onde $n$ é o número de pedaços de precisão que exigimos, e onde usamos ${} €propto {}$ para indicar que suprimimos o fator de normalização de $1 / \sqrt {2^n}$.

Se assumirmos que $\phi = 2 \pi p / 2^k$ para um inteiro $p$, então reconhecemos isto como $\ket{\psi} = \operatorname{QFT} \ket{p_1 p_0 \dots p_n}$, onde $p_j$ é o $j^{\textrm{th}}$$ bit de $2 \pi \phi$.
Aplicando a adjoint da transformação quântica fourier, obtemos assim a representação binária da fase codificada como um estado quântico.

Em Q#, esta é implementada pela operação <xref:microsoft.quantum.characterization.quantumphaseestimation>, que leva uma aplicação <xref:microsoft.quantum.oracles.discreteoracle> implementação de $U^m$ em função de inteiros positivos $m$.
