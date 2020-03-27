---
title: Vários qubits
description: Saiba como realizar operações em dois ou mais qubits.
author: QuantumWriter
uid: microsoft.quantum.concepts.multiple-qubits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 239073b7e7edafc49bc65cb60c9f45cf0af83dbe
ms.sourcegitcommit: a0e50c5f07841b99204c068cf5b5ec8ed087ffea
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "80320879"
---
# <a name="multiple-qubits"></a>Múltiplos Qubits

Enquanto os portões de um qubit único possuem algumas características contraintuitivas, tais como a capacidade de estar em mais de um estado em um dado momento, se tudo o que tínhamos num computador quântico fossem portões de um único qubit então teríamos um dispositivo com poder computacional que seria atenuado por mesmo uma calculadora muito menos um supercomputador clássico.
O verdadeiro poder da computação quântica só se torna evidente à medida que aumentamos o número de qubits.
Esta potência surge, em parte, porque a dimensão do espaço vetorial dos vetores do estado quântico cresce exponencialmente com o número de qubits.
Isto significa que, embora um único qubit possa ser modelado trivialmente, simular uma computação quântica de 50 qubits iria indiscutivelmente empurrar os limites dos supercomputadores existentes.
Aumentar o tamanho do cálculo por apenas um qubit adicional *duplica* a memória necessária para armazenar o estado e *aproximadamente duplica* o tempo computacional.
Esta rápida duplicação do poder computacional é a razão pela qual um computador quântico com um número relativamente pequeno de qubits pode ultrapassar em muito os supercomputadores mais poderosos de hoje, amanhã e além para algumas tarefas computacionais.

Por que temos crescimento exponencial para os vetores do estado quântico?  O nosso objetivo nesta secção é rever as regras utilizadas para construir estados multiqubit a partir de estados de qubit único, bem como discutir as operações do portal que precisamos incluir no nosso portal definido para formar um computador quântico universal de muitos qubits.
Estas ferramentas são absolutamente necessárias para entender os conjuntos de portais que são comumente usados no código Q# e também para ganhar intuição sobre por que os efeitos quânticos como o emaranhado ou a interferência tornam a computação quântica mais poderosa do que a computação clássica.

## <a name="representing-two-qubits"></a>Representando dois Qubits
A principal diferença entre estados de um e dois qubits é que os estados de dois qubits são quatro estados dimensionais em vez de bidimensionais.
Isto porque a base computacional para estados de dois qubits é formada pelos produtos tensores de estados de um qubit.  Por exemplo, temos \begin{align} 00 \equiv \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \start{bmatrix}1 \\\\ 0 \end{bmatrix} &= \start{bmatrix}1 \\\\ 0\\\\ 0\\\\ 0 \end{b Matrix},\qquad 01 \equiv \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \start{bmatrix}0 \\\\ 1 \end{bmatrix} = \start{bmatrix}0 \\\\ 1\\\\ 0\\\\ 0 \end{bmatrix}\\\\ 10 \equiv \start{bmatrix}0 \\\\ 1 \end{bmatrix}\otimes \start{bmatrix}1 \\\\ 0 \end{bmatrix} &= \start{bmatrix}0 \\\\ 0\\\\ 1\\\\ 0 \end{bmatrix},\qquad 11 \equiv \begin{bmatrix}0 \\\\ 1 \end{bmatrix}\otimes \start {bmatrix}0 \\\\ 1 \end{bmatrix} = \start{bmatrix}0 \\\\ 0\\\\ 0\\\\ 1 \end{bmatrix}.
\fim{align}

É fácil ver que, de uma forma mais geral, o estado quântico de $n qubits de$ é representado por um vetor unitário de dimensão $2^n$ usando esta construção.  O vetor

$$ \start{bmatrix} \alpha_{00} \\\\  \alpha_{01} \\\\{10} alpha_ \\ \\alpha_{11} \end{bmatrix} $}

representa um estado quântico em dois qubits se $\alpha_{00}^2+\alpha_{01}^2+\\alpha_{10}^2+\alpha_{11}^2=1$). Tal como acontece com os qubits individuais, o vetor de estado quântico de múltiplos qubits contém toda a informação necessária para descrever o comportamento do sistema.

Se nos forda duas qubits separadas, um no estado $\start{bmatrix} \alpha \\\\ \beta {bmatrix}$ e um segundo qubit no estado $\start{bmatrix} \gamma \\\\ \delta {bmatrix}$, o estado correspondente de dois qubits é o estado correspondente de dois qubits é o estado correspondente de dois qubits é o estado correspondente de dois qubits é o estado correspondente de dois qubits é o estado correspondente de dois qubits é o estado correspondente de dois qubits é o estado correspondente de dois qubits é o estado correspondente de dois qubits é o estado correspondente de dois qubits é o estado correspondente de dois qubits é o estado correspondente de dois qubits é o estado correspondente de dois qubits é o estado correspondente de dois qubits é

$$ \start{bmatrix} \alpha \\\\ \beta \final{bmatrix} \otimes \start {bmatrix} \gamma \\\\ \delta \end {bmatrix} =\start{bmatrix} \alpha \start{bmatrix} \gamma \\\\ \delta \end{bmatrix} \\\\ \beta \start{bmatrix}\gamma \\\\ \delta \\end{bmatrix} = \start{bmatrix} \alpha\gamma \\\\ \alpha\delta \\\\ \beta\gamma \\\\ \beta\delta {end{bmatrix} , $$

onde a operação $\otimes$ é chamado de produto tensor (ou produto Kronecker) de vetores. Note-se que, embora possamos sempre tomar o produto tensor de dois estados monobitais para formar um estado de dois qubits, nem todos os estados quânticos de dois qubits podem ser escritos como o produto tensor de dois estados monoqubit.
Por exemplo, não existem estados $\psi=\begin{bmatrix} \alpha \\\\ \beta \end{bmatrix}$ and $\phi=\start{bmatrix} \gamma \\\\ \delta \\end{bmatrix}$ de tal forma que o seu produto tensor é o estado 

$$\psi\otimes \phi = \start{bmatrix} 1/\sqrt{2} \\\\ 0 \\\\ 0 \\\\ 1/\sqrt{2} \end{bmatrix}.$$ 

Este estado de dois qubits, que não pode ser escrito como o produto tensor de estados monoqubits, é chamado de "estado emaranhado"; dizem que os dois qubits estão [*emaranhados.* ](https://en.wikipedia.org/wiki/Quantum_entanglement)  Vagamente falando, porque o estado quântico não pode ser considerado como um produto tensor de estados qubit únicos, a informação que o Estado detém não se limita a nenhum dos qubits individualmente.  Pelo contrário, a informação é armazenada não localmente nas correlações entre os dois Estados.  Esta não-localidade da informação é uma das principais características distintivas da computação quântica sobre a computação clássica e é essencial para uma série de protocolos quânticos, incluindo [teleportação quântica](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/teleportation) e [correção de erros quânticos.](xref:microsoft.quantum.libraries.error-correction)

## <a name="measuring-two-qubit-states"></a>Medição de Dois Estados Qubit ##
Medir estados de dois qubits é muito semelhante às medições de qubit único. Medindo o estado

$$ \start{bmatrix} \alpha_{00} \\\\  \alpha_{01} \\\\{10} alpha_ \\ \\alpha_{11} \end{bmatrix} $}

rende $00$ com probabilidade $\alpha_{00}^^2$, $01$ com probabilidade $\alpha_{01}^^2$, $10$ com probabilidade $\alpha_{10}^^2$, e $11$ com probabilidade $\\alpha_{11}^^2$. As variáveis $\alpha_{00}, \alpha_{01}, \alpha_{10},$ e $\alpha_{11}$ foram deliberadamente nomeados para tornar esta ligação clara. Após a medição, se o resultado for $00$ então o estado quântico do sistema de dois qubits entrou em colapso e é agora

$00 \equiv \start{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix}.
$$

Também é possível medir apenas um qubit de um estado quântico de dois qubits. Nos casos em que se mede apenas um dos qubits, o impacto da medição é subtilmente diferente porque todo o Estado não é colapsado para um estado de base computacional, pelo contrário, é colapsado para apenas um subsistema.  Por outras palavras, nestes casos, a medição de apenas um qubit só colapsa um dos subsistemas, mas nem todos.  

Para ver isto considerar medir o primeiro qubit do seguinte estado, que é formado pela aplicação da transformação de Hadamard $H$ em dois qubits inicialmente definidos para o estado "0": $$ H^{\otimes 2} \start {bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \start {bmatrix}1 \\\\ 0 \end{bmatrix} \right) = \{1}{2}frac 1 \\\\ 1 e -1 e 1 e 1 e -1 \\\\ 1 e 1 e -1 e -1 \\\\ 1 e 1 e 1 final{bmatrix}\begin{bmatrix}1\\\\ 0\\\\ 0\\\\ 0\end{bmatrix} = \frac {2}{1}\begin {bmatrix}1\\\\ 1\\\\ 1\\\\ 1\end{bmatrix} \mapsto \start{cases}\text{outcome }=0 & \frac{1}{\sqrt{2}}\start{bmatrix}1\\\\ 1\\\\ 0\\\\ 0 \end{bmatrix} \\\\\text{outcome }=1 & \frac{1}{\sqrt{2}}\start{bmatrix}0\\\\ 0\\\\ 1\\\\ 1 \end{bmatrix}\\\\ \end{cases}.
$$ Ambos os resultados têm 50% de probabilidade de ocorrer.  O resultado é 50% de probabilidade para ambos pode ser intuido pelo facto de o vetor do estado quântico inicial ser invariante ao trocar $0$ por $1$ no primeiro qubit.

A regra matemática para medir o primeiro ou segundo qubit é simples.  Se deixarmos $e_k$ ser o vetor de base computacional $k^{\rm th}$ e deixar que $S$ seja o conjunto de todos os $e_k$ de tal forma que o qubit em questão leva o valor de $1$ por esse valor de $k$.  Por exemplo, se estivermos interessados em medir o primeiro qubit, então $S$ consistiria em $e_1\equiv 10$ e $e_3\equiv 11$.  Da mesma forma, se estivermos interessados no segundo qubit $S$ consistiria em $e_2\equiv 01$ e $e_3 \equiv 11$.  Em seguida, a probabilidade de medir o qubit escolhido para $1$ é para o vetor do estado $\psi$

$$ P(\text{outcome}=1)= \sum_{e_k \text{ no conjunto } S}\psi^\dagger e_k e_k^\dagger \psi.
$$

> [!NOTE]
> Neste documento estamos a usar o formato pouco endiano para rotular a base computacional. Em pouco formato endiano, as partes menos significativas vêm em primeiro lugar. Por exemplo, o número quatro em formato pequeno-endiano é representado pela cadeia de bits 001.

Uma vez que cada medição de qubit só pode render $0$ ou $1$1$, a probabilidade de medir $0$ é simplesmente $1-P (\text{outcome}=1)$.  É por isso que só explicitamente damos uma fórmula para a probabilidade de medir $1$1$.

A ação que tal medida tem sobre o estado pode ser expressa matematicamente como

$$ \psi \mapsto \frac{\sum_{e_k \text{{ in the set } S} e_k e_k^\dagger \psi}{\sqrt{P(\text{outcome}=1)}}}
$$

O leitor cauteloso pode preocupar-se com o que acontece quando a probabilidade da medição é zero.  Embora o estado resultante seja tecnicamente indefinido neste caso, nunca precisamos de nos preocupar com tais eventualidades porque a probabilidade é zero!


Se levarmos $\psi$ para ser o vetor de estado uniforme dado acima e estamos interessados em medir o primeiro qubit então 

$$ P(\text{measurement of first qubit}=1) = (\psi^\dagger e_1)(e_1^\dagger \psi)(\psi^\dagger e_3)(e_3^\dagger \psi)=e_1^\dagger \psi^2+/e_3^\adagger \psi^2^2^.
$$

Note que esta é apenas a soma das duas probabilidades que seriam esperadas para medir os resultados $10$ e $11$ foram todos os qubits a medir.
Para o nosso exemplo, isto avalia para

$$ \frac{1}{4}\left\\start{bmatrix}0&0&1&0\end{bmatrix}\start{bmatrix}1\\\\ 1\\\\ 1\\\\ 1\end{bmatrix} \right\2+\frac{1}{4}\\start{bmatrix}0&0&0&1\end{bmatrix}\start{bmatrix}1\\\\ 1\\\\ 1\\\\ 1\end{bmatrix} \right^2=\frac{1}{2}.
$$

que combina perfeitamente com o que a nossa intuição nos diz que a probabilidade deve ser.  Da mesma forma, o estado pode ser escrito como

$$ \frac{{e_1}{2}+\frac{e_3}{2}}{\sqrt{\frac{1}{2}}}=\frac{1}{\sqrt{2}}\start{bmatrix} 0\\\\ 0\\\\ 1\\\\ 1\end{bmatrix} $$

novamente de acordo com a nossa intuição.

## <a name="two-qubit-operations"></a>Operações de Dois Qubit
Tal como no caso do qubit único, qualquer transformação unitária é uma operação válida em qubits. Em geral, uma transformação unitária em qubits de $n$ é uma matriz $U$ de tamanho $2^n \vezes 2^n$ (de modo a agir em vetores de tamanho $2^n$), de tal forma que $U^{-1} = U^\dagger$.
Por exemplo, o portão CNOT (controlado-NÃO) é um portão de dois qubits comumente utilizado e é representado pela seguinte matriz unitária:

$$ \operatorname{CNOT} = \start{bmatrix} 1\ 0\ 0\ 0\ 0 \\\\ 0\ 0\ 0\ 0\ 0 \\\\ 0\ 0 \\\ 0\ 1 \\ 0\ 0\ 0\ 0\ 0\ 0\ 0\ 0\ 0\ 0\ 0 \ 0 \end{bmatrix} $$ $$

Também podemos formar portões de dois qubits aplicando portões de qubit único em ambos os qubits. Por exemplo, se aplicarmos os portões 

$$ \start{bmatrix} a\ b\\\\ c\ d \end{bmatrix} $$

e

$$\start{bmatrix} e\ f\\\\  g\ h \end{bmatrix} $$

ao primeiro e segundo qubits, respectivamente, isto equivale a aplicar o unitário de dois qubitda dado pelo seu produto tensor: $$\begin{bmatrix} a\ b\\\\ c\ d \end{bmatrix} \otimes \start {bmatrix} e\ f\\\\ g\ h \end{bmatrix}= \start{bmatrix} a E\ af\ be\ bf \\\\ ag\ ah\ bg\ \\bh \\ ce\ cf\ de\ df \\\\ cg\ ch\ dg\ dh \end{bmatrix}.$$$ Assim podemos formar portões de dois qubits tomando o produto tensor de alguns portões de um único qubit conhecidos. Alguns exemplos de portões de dois qubits incluem $H \otimes H$, $X \otimes \boldone$, e $X \otimes Z$.

Note que, embora quaisquer dois portões de qubit único definam um portão de dois qubits tomando o seu produto tensor, o inverso não é verdade. Nem todos os portões de dois qubits podem ser escritos como o produto tensor de portões de um único qubit.  Tal portão é chamado de portão *de engate.* Um exemplo de um portão de engate é o portão CNOT.

A intuição por trás de um portão não controlado pode ser generalizada a portões arbitrários.  Um portão controlado em geral é um portão que funciona como identidade (ou seja, não tem ação) a menos que um qubit específico seja $1$1$.  Denotamos um unitário controlado, controlado neste caso no qubit rotulado $x$, com um $\Lambda\_x(U)$.  Como exemplo $\Lambda_0(U) e\_{1}\otimes {\psi}=e\_{1}\otimes U{\psi}$ e $\Lambda\_0(U) e\_{0}\otimes {\psi}=e\_{0}\otimes{\psi}$, onde $e\_0$ e $e\_1$ são os vetores de base computacional para um único qubit correspondente aos valores $0$ e $1$1$.  Por exemplo, considere o seguinte portão controlado $Z$ então podemos expressá-lo como $$ \Lambda\_0(Z)= \start{bmatrix}1&0&0&0\\\\0&1&0&0\\\\0 &0&1&0\\\\0&0&0&-1 \end{bmatrix}=(\boldone\otimes H)\operatorname{CNOT}(\boldone\otimes H).
$$

Construir unitários controlados de forma eficiente é um grande desafio.  A forma mais simples de implementar isto requer a formação de uma base de dados de versões controladas de portões fundamentais e a substituição de todos os portãos fundamentais da operação unitária original pela sua congénere controlada.  Esta visão é muitas vezes bastante desperdiçada e inteligente muitas vezes pode ser usada para apenas substituir alguns portões por versões controladas para obter o mesmo impacto.  Por esta razão, fornecemos no nosso quadro a capacidade de executar o método ingénuo de controlo ou permitir que o utilizador defina uma versão controlada do unitário se for conhecida uma versão otimizada afinada à mão.

Os portões também podem ser controlados usando informações clássicas.  Um não-portão controlado clássicamente, por exemplo, é apenas um não-portão comum, mas só é aplicado se uma parte clássica for $1$ em oposição a uma parte quântica.  Neste sentido, um portão controlado clássicamente pode ser considerado como uma declaração se no código quântico em que o portão é aplicado apenas em um ramo do código.


Tal como no caso do qubit único, um conjunto de dois qubits gate é universal se qualquer matriz unitária de $4\times de 4$4$ pode ser aproximadamente aproximadapor um produto de portões deste conjunto para precisão arbitrária.
Um exemplo de um portão universal definido é o portão Hadamard, o portão T, e o portão CNOT. Tomando produtos destes portões, podemos aproximar qualquer matriz unitária em dois qubits.

## <a name="many-qubit-systems"></a>Sistemas Many-Qubit
Seguimos exatamente os mesmos padrões explorados no caso de dois qubits para construir muitos estados quânticos qubit a partir de sistemas menores.  Estes Estados são construídos através da formação de produtos tensores de estados mais pequenos.  Por exemplo, considere codificar a cadeia bit $1011001$ num computador quântico.  Podemos codificar isto como

$$ 1011001 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \start {bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \start{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \start{{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \start{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \start{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \start{bmatrix} 0 \\\\ 1 \end{bmatrix}.
$$

Os portões quânticos funcionam exatamente da mesma maneira.  Por exemplo, se quisermos aplicar o portão $X$ ao primeiro qubit e, em seguida, executar um CNOT entre o segundo e o terceiro qubits podemos expressar esta transformação como

\start{align} &(X \otimes \operatorname{CNOT}_{12}\otimes \boldone\otimes \boldone \otimes \boldone \otimes \boldone \otimes \boldone} \start{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \start{bmatrix} 1 \\\\ 0 \end{bmatrix }\otimes \start{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \start{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \start{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \start{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\\\\ &\qquad\qquad\equiv 0011001.
\fim{align}

Em muitos sistemas qubit, muitas vezes há a necessidade de alocar e desalocar qubits que servem de memória temporária para o computador quântico.  Tal qubit é chamado de uma cilla.  Por predefinição assumimos que o estado qubit é inicializado para $e_0$ após a atribuição.  Assumimos ainda que é devolvido novamente a $e_0$ antes da desatribuição.  Este pressuposto é importante porque se um qubit aceso se envolver com outro registo de qubit quando este for desalocado, então o processo de desafetação prejudicará a acessia.  Por esta razão, assumimos sempre que tais qubits são revertidos para o seu estado inicial antes de serem libertados.

Finalmente, embora fossem necessários novos portões para alcançar a computação quântica universal para dois computadores quânticos qubit, não é necessário introduzir novos portões no caso multiqubit.  Os portões $H$, $T$ e CNOT formam um portão universal definido em muitos qubits porque qualquer transformação unitária geral pode ser quebrada em uma série de duas rotações qubit.  Podemos então aproveitar a teoria desenvolvida para o caso de dois qubits e usá-la novamente aqui quando temos muitos qubits.

Embora a notação algébrica linear que temos vindo a utilizar até agora possa certamente ser usada para descrever estados multiqubit, torna-se cada vez mais complicada à medida que aumentamos a dimensão dos Estados.  O vetor de coluna resultante para uma corda de 7 bits, por exemplo, é $128$ dimensional, o que faz expressá-lo usando a notação descrita anteriormente muito pesada.  Por esta razão, apresentamos uma notação comum na computação quântica que nos permite descrever concisamente estes vetores de alta dimensão.
