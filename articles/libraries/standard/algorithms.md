---
title: 'P # bibliotecas padrão-algoritmos | Microsoft Docs'
description: 'P # bibliotecas padrão'
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.algorithms
ms.openlocfilehash: 61efddb9e7199543370ffd66d08f78ec013f4f79
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185703"
---
# <a name="quantum-algorithms"></a>Algoritmos Quantum #

## <a name="amplitude-amplification"></a>Amplificação de amplitude ##

A *amplificação de amplitude* é uma das ferramentas fundamentais da computação Quantum. É a ideia fundamental que conta com a pesquisa de Grover, estimativa de amplitude e muitos algoritmos de aprendizado de máquina Quantum.  Há muitas variantes e, em Q #, fornecemos uma versão geral baseada na amplificação de amplitude alheios com reflexos parciais para permitir a área mais ampla do aplicativo.

A ideia central por trás da amplificação de amplitude é aumentar a probabilidade de ocorrer um resultado desejado executando uma sequência de reflexos.  Esses reflexos giram o estado inicial mais próximo em relação a um estado de destino desejado, geralmente chamado de estado marcado.  Especificamente, se a probabilidade de medir o estado inicial para estar em um estado marcado for $ \sin ^ 2 (\theta) $ depois de aplicar a amplificação de amplitude $m $ vezes a probabilidade de êxito se tornará $ \sin ^ 2 ((2m + 1) \theta) $.  Isso significa que se $ \theta = \ PI/[2 (2n + 1)] $ para algum valor de $n $, a amplificação de amplitude é capaz de impulsionar a probabilidade de sucesso para $100\\% $ após $n $ iterações de amplificação de amplitude.  Como $ \theta = \sin ^{-1}(\sqrt{\Pr (Success)}) $ isso significa que o número de iterações necessárias para obter um sucesso de forma determinista é quadráticamente menor do que o número esperado necessário para localizar um estado marcado de forma não determinística usando Random exemplos.

Cada iteração da amplificação de amplitude exige que dois operadores de reflexão sejam especificados. Especificamente, se $Q $ é a amplificação de amplitude iterar e $P _0 $ é um operador de projetor no subespaço inicial e $P _1 $ é o projetor para o subespaço marcado, em seguida, $Q =-(\boldone-2P_0) (\boldone-2P_1) $.  Lembre-se de que um projetor é um operador Hermitian que tem eigenvalues $ + $1 e $0 $ e, como resultado, $ (\boldone-2P_0) $ é unitário porque tem eigenvalues que são raízes de Unity (neste caso, $ \pm $1). Como exemplo, considere o caso da pesquisa do Grover com o estado inicial $H ^ {\otimes n} \ket{0}$ e o estado marcado $ \ket{m} $, $P _0 = H ^ {\otimes n} \ket{0}\bra{0}H ^ {\otimes n} $ e $P _1 = \ket{m}\bra{m} $.  Na maioria dos aplicativos da amplificação de amplitude $P _0 $ será um projetor para um estado inicial, o que significa que $P _0 = \boldone-2 \ ket {\ psi} \ Bra {\ psi} $ para algum vetor $ \ket{\psi} $; no entanto, para alheios amplitude amplication $P _0 $ normalmente o projeto em muitos Estados da Quantum (ou seja, a multiplicidade do $ + $1 eigenvalue de $P _0 $ é maior que $1 $).

A lógica por trás da amplificação de amplitude segue diretamente da decomposição de Eigen de $Q $.  Especificamente, a eigenvectors de $Q $ que o estado inicial tem suporte diferente de zero pode ser mostrada como combinações lineares de $ + $1 eigenvectors de $P _0 $ e $P _1 $.  Especificamente, o estado inicial da amplificação de amplitude (supondo que seja um $ + $1 eigenvector de $P _0 $) pode ser escrito como $ $ \ket{\psi} = \frac{-i}{\sqrt{2}} \left (e ^ {i\theta} \ ket {\ psi_ +} + e ^ {-i\theta} \ ket {\ psi_-} \ right), $ $, em que $ \ket{\psi_\pm } $ são eigenvectors de $Q $ com eigenvalues $e ^ {\pm 2i \ teta} $ e só têm suporte na eigenvectors de $ + $1 de $P _0 $ e $P _1 $.  O fato de que eigenvalues são $e ^ {\pm i \theta} $ indica que o operador $Q $ executa uma rotação em um subespaço bidimensional especificado pelos dois projetores e o estado inicial em que o ângulo de rotação é $2 \ teta $.  É por isso que depois de $m $ iterações de $Q $ a probabilidade de êxito é $ \sin ^ 2 ([2m + 1] \theta) $.

Outra propriedade útil que chega disso é que o eigenvalue $ \theta $ está diretamente relacionado à probabilidade de que o estado inicial seja marcado (no caso em que $P _0 $ é um projetor apenas para o estado inicial).  Como o eigenphases de $Q $ é US $2 \ teta = 2 \ Sin ^{-1}(\sqrt{\Pr (Success)}) $, então, se aplicarmos a estimativa de fase à $Q $, poderemos aprender a probabilidade de sucesso para um procedimento de Quantum unitário.  Isso é útil porque requer menos aplicativos do procedimento Quantum para aprender a probabilidade de êxito do que seria necessário.

Q # apresenta amplificação de amplitude como uma especialização de amplificação de amplitude alheios.  A amplificação de amplitude de alheios ganha esse moniker porque o projetor na eigenspace inicial não precisa ser um projetor no estado inicial.  Nesse sentido, o protocolo é alheios para o estado inicial.  O principal aplicativo da amplificação alheios amplitude está em determinadas *combinações lineares de métodos de simulação de Hamiltonian unitários* , em que o estado inicial é desconhecido, mas torna-se confusas com um registro ancilla no protocolo de simulação.  Se esse registro ancilla for ser medido como um valor fixo, digamos $0 $, esses métodos de simulação aplicarão a transformação unitário desejada ao qubits restante (chamado de registro do sistema).  No entanto, todos os outros resultados de medição resultam em falha.  A amplificação de amplitude alheios permite que a probabilidade de sucesso dessa medida seja aumentada para $100\\% $ usando o raciocínio acima.  Além disso, a amplificação de amplitude comum corresponde ao caso em que o registro do sistema está vazio.  É por isso que Q # usa a amplificação de amplitude alheios como sua sub-rotina fundamental de amplificação de amplitude.

A rotina geral (`AmpAmpObliviousByReflectionPhases`) tem dois registros que chamamos de `ancillaRegister` e `systemRegister`. Ele também aceita dois Oracle para os reflexos necessários. O `ReflectionOracle` atua apenas no `ancillaRegister` enquanto o `ObliviousOracle` atua em conjunto em ambos os registros. A entrada para `ancillaRegister` deve ser inicializada para um-1 eigenstate do primeiro operador de reflexão $ \boldone-2P_1 $.

Normalmente, o Oracle prepara o estado na base computacional $ \ket{0...0} $. Em nossa implementação, a `ancillaRegister` consiste em um qubit (`flagQubit`) que controla a `stateOracle` e o restante do ancillas desejado. O `stateOracle` é aplicado quando o `flagQubit` é $ \ket{1}$.

Uma delas também pode fornecer os Oracle `StateOracle` e `ObliviousOracle` em vez de reflexões por meio de uma chamada para `AmpAmpObliviousByOraclePhases`.

Como mencionado, a amplificação de amplitude tradicional é apenas um caso especial dessas rotinas em que `ObliviousOracle` é o operador de identidade e não há nenhum qubits de sistema (ou seja, `systemRegister` está vazio). Se você quiser obter fases para reflexões parciais (por exemplo, para Grover Search), a função `AmpAmpPhasesStandard` estará disponível. Consulte `DatabaseSearch.qs` para obter uma implementação de exemplo do algoritmo do Grover.

Relacionamos as fases de rotação qubit às fases do operador de reflexão, conforme descrito no artigo por [G.H. baixo, I. L. Chuang](https://arxiv.org/abs/1707.05391). As fases de ponto fixo que são usadas são detalhadas em [Yoder, Low e Chuang,](https://arxiv.org/abs/1409.3305) juntamente com as fases em [baixo, Yoder e Chuang](https://arxiv.org/abs/1603.03996).

Para o segundo plano, você pode começar da [amplificação de amplitude padrão](https://arxiv.org/abs/quant-ph/0005055) e, em seguida, passar para uma introdução à [amplificação de amplitude alheios](https://arxiv.org/abs/1312.1414) e, finalmente, generalizações apresentadas em [baixa e Chuang](https://arxiv.org/abs/1610.06546). Uma boa apresentação de visão geral de toda a área (como está relacionada à simulação de Hamiltonian) foi fornecida por [Dominic Berry](http://www.dominicberry.org/presentations/Durban.pdf).

## <a name="quantum-fourier-transform"></a>Transformação de Fourier Quantum ##

A transformação de Fourier é uma ferramenta fundamental de análise clássica e é tão importante para cálculos de Quantum.
Além disso, a eficiência da *transformação de Fourier Quantum* (QFT) supera muito o que é possível em uma máquina clássica, tornando-a uma das primeiras ferramentas de escolha ao criar um algoritmo Quantum.

Como uma generalização aproximada do QFT, fornecemos a operação <xref:microsoft.quantum.canon.approximateqft> que permite mais otimizações por meio da remoção de rotações que não são estritamente necessárias para a precisão do algoritmo desejado.
O QFT aproximado requer a <xref:microsoft.quantum.primitive.rfrac> operação de $Z $-Rotation, bem como a operação de <xref:microsoft.quantum.intrinsic.h>.
Presume-se que a entrada e a saída sejam codificadas na codificação big endian (o menor bit/qubit está à esquerda, o mesmo que [ket Notation](xref:microsoft.quantum.concepts.dirac)).
O parâmetro de aproximação $a $ determina o nível de remoção do $Z $-rotações, ou seja, $a na [0.. n] $.
Nesse caso, todos os $Z $-rotações $2 \ pi/2 ^ k $ em que $k > um $ são removidos do circuito QFT.
É conhecido que por $k \ge \log_2 (n) + \log_2 (1/\epsilon) + $3. é possível associar $\\| \operatorname{QFT}-\operatorname{AQFT} \\| < \epsilon $.
Aqui, $\\| \cdot\\| $ é a norma do operador que, nesse caso, é a raiz quadrada do maior [eigenvalue](xref:microsoft.quantum.concepts.matrix-advanced) de $ (\Operatorname{QFT}-\operatorname{AQFT}) (\Operatorname{QFT}-\operatorname{AQFT}) ^ \dagger $.

## <a name="arithmetic"></a>Operações ##

Assim como a aritmética desempenha uma função central na computação clássica, ela também é indispensáveisda na computação Quantum.  Algoritmos como o algoritmo de fatoração do Atal, métodos de simulação do Quantum, bem como muitos algoritmos oracular dependem de operações aritméticas coerentes.  A maioria das abordagens para a compilação aritmética nos circuitos do adicionador Quantum.  O adicionador mais simples usa uma entrada clássica $b $ e adiciona o valor a um estado Quantum contendo um inteiro $ \ket{a} $.  Matematicamente, o adicionador (que denotamos $ \operatorname{Add} (b) $ para entrada clássica $b $) tem a propriedade que

$ $ \operatorname{Add} (b) \ket{a} = \ket{a + b}.
$ $ Esse circuito básico do adicionador é mais um incrementador do que um adicionador.
Ele pode ser convertido em um adicionador que tem duas entradas Quantum por meio de $ $ \operatorname{Add}\ket{a}\ket{b} = \ket{a}\ket{a + b}, $ $ usando aplicativos controlados pelo $n $ de adicionadores da forma \begin{align} \operatorname{Add} \ket{a} \ket{b} & = \Lambda\_{a\_0} \left (\operatorname{Add} (1) \right) \Lambda\_{a\_1} \left (\operatorname{Add} (2) \right) \Lambda\_{a\_2} \left (\operatorname{Add} (4) \right) \cdots \Lambda\_{a\_{n-1}} \left (\ OperatorName {Add} ({{n-1}}) \right) \ket{a}\ket{b} \\\\ & = \ket{a} \ket{b + a}, \end{align} para $n inteiros de $ bit $a $ e $b $ e módulo de adição $2 ^ n $.  Lembre-se de que a Notation $ \Lambda\_x (A) $ se refere, para qualquer operação $A $, à versão controlada da operação com qubit $x $ como Control.

Da mesma forma, a multiplicação clássica controlada (uma forma modular essencial para o algoritmo de fatoração do Atal) pode ser executada usando uma série semelhante de adições controladas: \begin{align} \operatorname{Mult} (a) \ket{x}\ket{b} & = \Lambda\_{x\_0} \left (\operatorname{Add} (2 ^ 0 a) \right) \Lambda\_{a\_1} \left (\operatorname{Add} (2 ^ 1a) \right) \Lambda\_{a\_2} \left (\operatorname{Add} (2 ^ 2 a) \right) \cdots \Lambda\_{x\_{ n-1}} \left (\operatorname{Add} ({2 ^ {n-1}} a) \right) \ket{x}\ket{b} \\\\ & = \ket{x}\ket{b + AX}.
\end{Align}, há uma sutileza com multiplicação em computadores Quantum que você pode notar na definição de $ \operatorname{Mult} $ acima.  Ao contrário da adição, a versão Quantum desse circuito armazena o produto das entradas em um registro auxiliar em vez de no registro de entrada.  Neste exemplo, o registro é inicializado com o valor $b $, mas normalmente ele começará a manter o valor zero.  Isso é necessário no porque, em geral, não há um inverso multiplicativa para geral $a $ e $x $.  Como todas as operações de Quantum, salvar medida, são reversívels, precisamos manter informações suficientes para inverter a multiplicação.  Por esse motivo, o resultado é armazenado em uma matriz separada.  Esse truque de salvar a saída de uma operação irreversível, como a multiplicação, em um registro separado, é conhecido como "truque Bennett" depois de Charlie Bennett e é uma ferramenta fundamental em computação reversível e Quantum.

Muitos circuitos Quantum foram propostos para adição e cada um explora uma compensação diferente em termos do número de qubits (espaço) e do número de operações de portão (tempo) necessário.  Examinamos dois adicionadores com alta economia de espaço abaixo, conhecidos como o Draper adicionador e o adicionador Beauregard.

### <a name="draper-adder"></a>Adicionador Draper ###

O conjunto de Draper é um dos adicionadores mais elegantes da Quantum, pois ele invoca diretamente as propriedades Quantum para executar a adição.  A percepção por trás do adicionador Draper é que a transformação de Fourier pode ser usada para converter turnos de fase em uma mudança de bit.  Em seguida, ele segue isso aplicando uma transformação de Fourier, aplicando as mudanças de fase apropriadas e, em seguida, desfazendo a transformação de Fourier, você pode implementar um adicionador.  Ao contrário de muitos outros adicionadores que foram propostos, o adicionador Draper usa explicitamente os efeitos de Quantum introduzidos por meio da transformação de Fourier do Quantum.  Ele não tem um equivalente clássico natural.  As etapas específicas do adicionador Draper são fornecidas abaixo.

Suponha que você tenha duas $n registros de qubit de $ bit que armazenam os inteiros $a $ e $b $ para todos os $a $ $ $ \operatorname{QFT}\ket{a} = \frac{1}{\sqrt{2 ^ n}} \sum\_{j = 0} ^ {2 ^ n-1} e ^ {i2\pi (AJ)/2 ^ n} \ket{j}.
$ $ Se definirmos $ $ \ket{\phi\_k (a)} = \frac{1}{\sqrt{2}} \left (\ket{0} + e ^ {i2\pi a/2 ^ k} \ket{1} \right), $ $ depois de alguma Algebra, você poderá ver que $ $ \operatorname{QFT}\ket{a} = \ket{\phi\_1 (a)} \otimes \cdots \ OTimes \ket{\phi\_n (a)}.
$ $ O caminho para executar um adicionador então fica claro depois de observar que a soma das entradas pode ser gravada como $ $ \ket{a + b} = \operatorname{QFT} ^{-1}\ket{\phi\_1 (a + b)} \otimes \cdots \otimes \ket{\phi\_n (a + b)}.
$ $ Os inteiros $b $ e $a $ podem ser adicionados executando a rotação de fase controlada em cada qubits na decomposição usando os bits de $b $ como controles.

Essa expansão pode ser ainda mais simplificada observando que, para qualquer inteiro $j $ e número real $x $, $e ^ {i2\pi (x + j)} = e ^ {i2\pi x} $.  Isso ocorre porque, se você girar $360 ^ {\circ} $ graus (US $2 \ pi $ radianos) em um círculo, você acabará precisamente onde começou.  A única parte importante do $x $ para $e ^ {i2\pi x} $ é, portanto, a parte fracionária do $x $.  Especificamente, se tivermos uma expansão binária do formulário $x = y +0. x\_0x\_2 \ ldots x\_n $ então $e ^ {i2\pi x} = e ^ {i2\pi (0. x\_0x\_2 \ ldots x\_{n-1})} $ e, portanto, $ $ \ket{\ Phi\_k (a + b)} = \frac{1}{\sqrt{2}} \left (\ket{0} + e ^ {i2\pi [a/2 ^ k +0. b\_k\ldots b\_1]} \ket{1} \right). $ $ isso significa que, se executarmos a adição incrementando cada uma das fatores tensor na expansão da transformação de Fourier de $ \ket{a} $ o número de rotações diminui à medida que $k $ diminui.  Isso reduz substancialmente o número de Gates Quantum necessários no adicionador.  Denotamos a transformação de Fourier, adição de fase e as etapas de transformação de Fourier inversa que compõem o Draper adicionado como $ \operatorname{QFT} ^{-1} \left (\phi\\\!\operatorname{ADD}\right) \operatorname{QFT} $. Um circuito Quantum que usa essa simplificação para implementar todo o processo pode ser visto abaixo.

![Adicionador Draper mostrado como diagrama de circuito](~/media/draper.png)

Cada portão $e ^ {i2 \ PI/k} $ controlado no circuito refere-se a um portão de fase controlada.  Esses Gates têm a propriedade que está no par de qubits em que atuam, $ \ket{00}\mapsto \ket{00}$, $ \ket{11}\mapsto e ^ {i2 \ PI/k} \ ket{11}$.  Esse circuito nos permite realizar acréscimos usando nenhum qubits adicional além daqueles necessários para armazenar as entradas e as saídas.

### <a name="beauregard-adder"></a>Adicionador Beauregard ###

O conjunto de Beauregard é um adicionador modular Quantum que usa o adicionador de Draper para executar o módulo de adição $N $ para um inteiro positivo de valor arbitrário $N $.  O significado dos somas modulares Quantum, como o Beauregard adicionado, se origina em uma grande extensão de seu uso na etapa de exponenciação modular dentro do algoritmo de Atal para fatoração.  Um adicionador modular Quantum tem a seguinte ação para a entrada Quantum $ \ket{b} $ e a entrada clássica $a $, em que $a $ e $b $ são prometidos como inteiros mod $N $, o que significa que eles estão no intervalo $ [0, \ldots, N-1] $.

$ $ \ket{b}\rightarrow \ket{b + a \Text{mod} N} = \begin{cases} \ket{b + a}, & b + a < N\\\\ \ket{b + a-N}, & (b + a) \ge N \end{cases}.
$$

O adicionador Beauregard usa o Draper soma ou mais especificamente $ \phi\\\!\operatorname{ADD} $, para adicionar $a $ e $b $ na fase.  Em seguida, ele usa a mesma operação para identificar se $a + b < N $ subtraindo $N $ e testando se $a + b-N < 0 $.  O circuito armazena essas informações em um qubit auxiliar e, em seguida, adiciona $N $ de volta ao registro se $a + b < N $.  Em seguida, ele é concluído por meio da descomputação deste bit auxiliar (essa etapa é necessária para garantir que o ancilla possa ser desalocado depois de chamar o adicionador).  O circuito para o adicionador Beauregard é fornecido abaixo.

![Adicionador Beauregard mostrado como diagrama de circuito](~/media/beau.png)

Aqui, o Gate $ \Phi\\\!\operatorname{ADD} $ usa a mesma forma que $ \Phi\\\!\operatorname{ADD} $, exceto que nesse contexto a entrada é clássica em vez de Quantum.  Isso permite que as fases controladas em $ \Phi\\\!\operatorname{ADD} $ sejam substituídas por Phase Gates que podem então ser compiladas juntas em menos operações para reduzir o número de qubits e o número de Gates necessário para o conjunto de somas.

Para obter mais detalhes, consulte [M. Roetteler, th. Beth](http://doi.org/10.1007/s00200-008-0072-2 ) e [D. Coppersmith](https://arxiv.org/abs/quant-ph/0201067).

### <a name="quantum-phase-estimation"></a>Estimativa da fase Quantum ###

Um aplicativo especialmente importante da transformação de Fourier do Quantum é aprender a eigenvalues de operadores unitários, um problema conhecido como *estimativa de fase*.
Considere um unitário $U $ e um estado $ \ket{\phi} $, de forma que $ \ket{\phi} $ seja um eigenstate de $U $ com eigenvalue desconhecido $ \phi $, \begin{Equation} U\ket {\ Phi} = \phi\ket{\phi}.
\end{Equation} se só tivermos acesso ao $U $ como um Oracle, podemos aprender a fase $ \phi $ utilizando esse $Z as rotações aplicadas ao destino de uma operação controlada se propagam de volta para o controle.

Suponha que $V $ é um aplicativo controlado de $U $, de modo que \begin{align} V (\ket{0} \otimes \ket{\phi}) & = \ket{0} \otimes \ket{\phi} \\\\ \textrm{e} V (\ket{1} \otimes \ket{\phi}) & = e ^ {i \phi} \ket{1}  \otimes \ket{\phi}.
\end{Align}, por linearidade, \begin{align} V (\ket{+} \otimes \ket{\phi}) & = \frac{(\ket{0} \otimes \ket{\phi}) + e ^ {i \phi} (\ket{1} \otimes \ket{\phi})} {\sqrt{2}}.
\end{Align}, podemos coletar termos para descobrir que \begin{align} V (\ket{+} \otimes \ket{\phi}) & = \frac{\ket{0} + e ^ {i \phi} \ket{1}} {\sqrt{2}} \otimes \ket{\phi} \\\\ & = (R_1 (\phi) \ket{+}) \otimes \ket{\phi} , \end{align} em que $R _1 $ é o unitário aplicado pela operação de <xref:microsoft.quantum.intrinsic.r1>.
Em outras palavras, o efeito da aplicação de $V $ é precisamente o mesmo que aplicar $R _1 $ com um ângulo desconhecido, mesmo que tenhamos acesso apenas ao $V $ como um Oracle.
Portanto, para o restante desta discussão, discutiremos a estimativa de fase em termos de $R _1 (\phi) $, que implementamos usando *Kickback fase*de chamada.

Como o controle e o registro de destino permanecem Untangled após esse processo, podemos reutilizar $ \ket{\phi} $ como o destino de um aplicativo controlado de $U ^ $2 para preparar um segundo controle qubit no estado $R _1 (2 \phi) \ket{+} $.
Continuando dessa forma, podemos obter um registro do formulário \begin{align} \ket{\psi} & = \sum_{j = 0} ^ n R_1 (2 ^ j \phi) \ket{+} \\\\ & \propto \bigotimes_{j = 0} ^ {n} \left (\ket{0} + \exp (i 2 ^ {j} \phi) \ket{1}\right) @no__ t_4_ \\ & \propto \sum_{k = 0} ^ {2 ^ n-1} \exp (i \phi k) \ket{k} \end{align} em que $n $ é o número de bits de precisão que exigimos e onde usamos ${} \propto {}$ para indicar que suprimimos o fator de normalização de $ 1/\sqrt{2 ^ n} $.

Se presumirmos que $ \phi = 2 \pi p/2 ^ k $ para um inteiro $p $, reconheceremos isso como $ \ket{\psi} = \operatorname{QFT} \ket{p_0 p_1 \dots p_n} $, em que $p _J $ é o $j ^ {\textrm{th}} $ bit of $2 \pi \phi $.
Aplicando o adjoin da transformação de Fourier do Quantum, portanto, obtemos a representação binária da fase codificada como um estado Quantum.

Em Q #, isso é implementado pela operação de <xref:microsoft.quantum.characterization.quantumphaseestimation>, que usa um aplicativo de implementação de <xref:microsoft.quantum.oracles.discreteoracle> de $U ^ m $ como uma função de inteiros positivos $m $.
