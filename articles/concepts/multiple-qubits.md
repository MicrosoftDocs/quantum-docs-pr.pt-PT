---
title: Vários qubits | Microsoft Docs
description: Vários qubits
author: QuantumWriter
uid: microsoft.quantum.concepts.multiple-qubits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 3e0404cfd67f693ff6b7a8297566e59208fc7ec0
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183782"
---
# <a name="multiple-qubits"></a>Vários qubits

Embora os Gates de qubit tenham alguns recursos intuitivos, como a capacidade de estar em mais de um estado em um determinado momento, se tudo o que tínhamos em um computador Quantum fosse um único qubit Gates, teríamos um dispositivo com energia computacional que seria diminuído por até mesmo uma calculadora deixa um supercomputador clássico.
O verdadeiro poder da computação Quantum só se torna evidente, pois aumentamos o número de qubits.
Essa energia surge, em parte, porque a dimensão do espaço vetorial dos vetores de estado do Quantum aumenta exponencialmente com o número de qubits.
Isso significa que, embora um único qubit possa ser modelado trivialmente, a simulação de uma computação Quantum 50-qubit impediria que os limites dos supercomputadors existentes fossem reforçados.
Aumentar o tamanho da computação por apenas um qubit adicional *dobra* a memória necessária para armazenar o estado e, aproximadamente, *dobra* o tempo computacional.
Essa dupla dobra de potência computacional é o motivo pelo qual um computador Quantum com um número relativamente pequeno de qubits pode superar de longe os supercomputadors mais potentes de hoje, amanhã e além de algumas tarefas computacionais.

Por que temos um crescimento exponencial para os vetores de estado Quantum?  Nosso objetivo nesta seção é revisar as regras usadas para criar Estados qubit de Estados de qubit único, bem como discutir as operações de portão que precisamos incluir em nosso conjunto de portais para formar um computador Quantum universal de muitos qubit.
Essas ferramentas são absolutamente necessárias para entender os conjuntos de porta que são comumente usados em código Q # e também para se aprofundar sobre por que os efeitos da Quantum, como Entanglement ou interferência, renderizam a computação Quantum mais potente do que a computação clássica.

## <a name="representing-two-qubits"></a>Representando dois qubits
A principal diferença entre os Estados de um e dois qubit é que os Estados de dois qubit são bidimensionais em vez de bidimensionais.
Isso ocorre porque a base computacional para Estados de duas qubit é formada pelos produtos tensor de Estados One-qubit.  Por exemplo, temos \begin{align} 00 \equiv \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} & = \begin{bmatrix}1 \\\\ 0\\\\ 0\\@no__ t_9_ 0 \end{bmatrix}, \qquad 01 \equiv \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \begin{bmatrix}0 \\\\ 1\\\\ 0\\\\ 0 \end{bmatrix},\\\\ 10 \equiv \begin{bmatrix}0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} & = \begin{bmatrix}0 \\\\ 0\\\\ 1\\\\ 0 \end{bmatrix}, \qquad 11 \equiv \begin{bmatrix}0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \begin{bmatrix}0 \\\\ 0\\\\ 0 @no__ t_40_ \\ 1 \end{bmatrix}.
\end{align}

É fácil ver que, geralmente, o estado da Quantum de $n $ qubits é representado por um vetor de unidade da dimensão $2 ^ n $ usando essa construção.  O vetor

$ $ \begin{bmatrix} \alpha_{00} \\\\ \alpha_{01} \\\\ \alpha_{10} \\\\ \alpha_{11} \end{bmatrix} $ $

representa um estado Quantum em dois qubits se $ | \alpha_{00}| ^ 2 + | \alpha_{01}| ^ 2 + | \alpha_{10}| ^ 2 + | \alpha_{11}| ^ 2 = 1 $. Assim como ocorre com qubits único, o vetor de estado do quantum de vários qubits contém todas as informações necessárias para descrever o comportamento do sistema.

Se recebermos dois qubits separados, um no estado $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ e um segundo qubit no estado $ \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $, o estado correspondente de dois qubit será

$ $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} \otimes \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} = \begin{bmatrix} \alpha \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} \\\\ \ Beta \begin{bmatrix}\gamma \\\\ \delta \end{bmatrix} \end{bmatrix} = \begin{bmatrix} \alpha\gamma \\\\ \alpha\delta \\\\ \beta\gamma \\\\ \beta\delta \end{bmatrix}, $ $

em que a operação $ \otimes $ é chamada de produto tensor (ou produto Kronecker) de vetores. Observe que, embora possamos sempre pegar o produto tensor de dois Estados de qubit único para formar um estado de dois qubit, nem todos os Estados de Quantum de dois qubit podem ser escritos como o produto tensor de dois Estados de qubit único.
Por exemplo, não há Estados $ \psi = \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ e $ \phi = \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $ de forma que seu produto tensor seja o estado 

$ $ \psi\otimes \phi = \begin{bmatrix} 1/\ sqrt{2} \\\\ 0 \\\\ 0 \\\\ 1/\ sqrt{2} \end{bmatrix}. $ $ 

Esse estado de duas qubit, que não pode ser escrito como o produto tensor de Estados de qubit único, é chamado de "estado confusas"; os dois qubits são considerados [*confusas*](https://en.wikipedia.org/wiki/Quantum_entanglement).  De forma flexível, como o estado do Quantum não pode ser considerado como um produto tensor de Estados de qubit único, as informações que o estado mantém não são confinadas para qualquer um dos qubits individualmente.  Em vez disso, as informações são armazenadas não localmente nas correlações entre os dois Estados.  Essa não localidade de informações é um dos principais recursos que distinguem a computação Quantum em relação à computação clássica e é essencial para vários protocolos Quantum, incluindo a [portadora Quantum](https://github.com/Microsoft/Quantum/tree/master/Samples/src/Teleportation) e a [correção de erro Quantum](xref:microsoft.quantum.libraries.error-correction).

## <a name="measuring-two-qubit-states"></a>Medindo Estados de duas qubit ##
Medir Estados de duas qubit é muito semelhante a medições de qubit único. Medindo o estado

$ $ \begin{bmatrix} \alpha_{00} \\\\ \alpha_{01} \\\\ \alpha_{10} \\\\ \alpha_{11} \end{bmatrix} $ $

produz $0 $ com probabilidade $ | \alpha_{00}| ^ $2, $1 $ com probabilidade $ | \alpha_{01}| ^ $2, $10 $ com probabilidade $ | \alpha_{10}| ^ $2 e $11 $ com probabilidade $ | \alpha_{11}| ^ $2. As variáveis $ \alpha_{00}, \alpha_{01}, \alpha_{10}, $ e $ \alpha_{11}$ foram deliberadamente nomeadas para tornar essa conexão clara. Após a medição, se o resultado for $0 $, o estado do quantum do sistema de duas qubit foi recolhido e agora é

$ $0 \equiv \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix}.
$$

Também é possível medir apenas um qubit de um estado de Quantum de dois qubit. Nos casos em que você mede apenas um dos qubits, o impacto da medição é ligeiramente diferente, pois o estado inteiro não é recolhido para um estado de base computacional, em vez disso, ele é recolhido para apenas um subsistema.  Em outras palavras, em tais casos medir apenas um qubit recolhe apenas um dos subsistemas, mas não todos eles.  

Para ver isso, considere medir a primeira qubit do seguinte Estado, que é formada pela aplicação da transformação Hadamard $H $ em dois qubits inicialmente definido como o estado "0": $ $ H ^ {\otimes 2} \left (\begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{ bmatrix} 1 \\\\ 0 \end{bmatrix} \right) = \frac{1}{2}\begin{bmatrix}1 & 1 & 1 & 1 \\\\ 1 &-1 & 1 &-1 \\\\ 1 & 1 &-1 &-1 @no__ t_10_ \\ 1 &-1 &-1 & 1 \end{bmatrix}\begin{bmatrix}1\\\\ 0\\\\ 0\\\\ 0 \ fim {bmatrix} = \frac{1}{2}\begin{bmatrix}1\\\\ 1\\\\ 1\\\\ 1 \ end {bmatrix} \mapsto \begin{cases}\Text{Outcome} = 0 & \frac{1}{\sqrt{2}} \begin{bmatrix}1\\\\ 1\\\\ 0\\\\ 0 \end{bmatrix}\\\\ \Text{Outcome} = 1 & \frac{1}{\sqrt{2}} \begin{bmatrix}0\\\\ 0\\\\ 1\\\\ 1 \end{bmatrix}\\\\ \end{ casos}.
$ $ Os dois resultados têm 50% de probabilidade de ocorrer.  O resultado sendo 50% de probabilidade para ambos pode ser Intuit do fato de que o vetor de estado inicial do Quantum é invariável em troca de $0 $ por $1 $ no primeiro qubit.

A regra matemática para medir o primeiro ou o segundo qubit é simples.  Se permitirmos que $e _K $ seja o vetor de base computacional $k ^ {\rm th} $ e permita que $S $ seja o conjunto de todos os $e _K $ de modo que o qubit em questão receba o valor $1 $ para esse valor de $k $.  Por exemplo, se estivermos interessados em medir o primeiro qubit, $S $ consistiria em $e _2 \ equiv $10 e $e _3 \ equiv $11.  Da mesma forma, se estivermos interessados na segunda qubit $S $ consistiria em $e _1 \ equiv $1 e $e _3 \equiv $11.  Em seguida, a probabilidade de medir o qubit escolhido para ser $1 $ é para o vetor de estado $ \psi $

$ $ P (\Text{Outcome} = 1) = \sum_{e_k \Text{no conjunto} S} \psi ^ \dagger e_k e_k ^ \dagger \psi.
$$

Como cada medida qubit só pode produzir $0 $ ou $1 $, a probabilidade de medir $0 $ é simplesmente $1-P (\Text{Outcome} = 1) $.  É por isso que só fornecemos explicitamente uma fórmula para a probabilidade de medir $1 $.

A ação que tal medida tem no estado pode ser expressa matematicamente como

$ $ \psi \mapsto \frac{\sum_{e_k \Text{no conjunto} S} e_k e_k ^ \dagger \psi}{\sqrt{P (\Text{Outcome} = 1)}}.
$$

O leitor cuidadoso pode se preocupar com o que acontece quando a probabilidade da medida é zero.  Embora o estado resultante seja tecnicamente indefinido nesse caso, nunca precisamos nos preocupar com essas eventualidades porque a probabilidade é zero!


Se levarmos $ \psi $ para ser o vetor de estado uniforme fornecido acima e estiver interessado em medir a primeira qubit, 

$ $ P (\Text{Measurement do primeiro qubit} = 1) = (\psi ^ \dagger e_2) (e_2 ^ \dagger \psi) + (\psi ^ \dagger e_3) (e_3 ^ \dagger \psi) = | e_2 ^ \dagger \psi | ^ 2 + | e_3 ^ \dagger \psi | ^ 2.
$$

Observe que essa é apenas a soma das duas probabilidades que seriam esperadas para medir os resultados $10 $ e $11 $ foram todos os qubits a serem medidos.
Para nosso exemplo, isso é avaliado como

$ $ \frac{1}{4}\left | \begin{bmatrix}0 & 0 & 1 & 0 \ end {bmatrix} \ Begin {bmatrix} 1\\\\ 1\\\\ 1\\\\ 1 \ end {bmatrix} \right | ^ 2 + \frac{1}{4}\left | \ Begin {bmatrix} 0 & 0 & 0 & 1 \ fim {bmatrix} \ Begin {bmatrix} 1\\\\ 1\\\\ 1\\\\ 1 \ end {bmatrix} \right | ^ 2 = \frac{1}{2}.
$$

que corresponde perfeitamente ao que nossa intuição nos informa que deve ser a probabilidade.  Da mesma forma, o estado pode ser escrito como

$ $ \frac{\frac{e_2}{2}+ \frac{e_3}{2}} {\sqrt{\frac{1}{2}}} = \frac{1}{\sqrt{2}} \begin{bmatrix} 0\\\\ 0\\\\ 1\\\\ 1 \ fim {bmatrix} $ $

novamente de acordo com nossa intuição.

## <a name="two-qubit-operations"></a>Operações de duas qubit
Como no caso de qubit único, qualquer transformação unitário é uma operação válida em qubits. Em geral, uma transformação unitário em $n $ qubits é uma matriz $U $ do tamanho de $2 ^ n \times 2 ^ n $ (para que ela atue em vetores de tamanho $2 ^ n $), de modo que $U ^{-1} = U ^ \dagger $. Por exemplo, a porta CNOT (controlada não) é uma porta de dois qubit comumente usada e é representada pela seguinte matriz de unitário:

$ $ \operatorname{CNOT} = \begin{bmatrix} 1 \ 0 \ 0 \ 0 \\\\ 0 \ 1 \ 0 \ 0 \\\\ 0 \ 0 \ 0 \ 1 \\\\ 0 \ 0 \ 1 \ 0 \end{bmatrix} $ $

Também podemos formar Gates de duas qubit aplicando Gates de qubit único em ambos os qubits. Por exemplo, se aplicarmos as Gates 

$ $ \begin{bmatrix} a \ b\\\\ c \ d \end{bmatrix} $ $

e em

$ $ \begin{bmatrix} e \ f\\\\ g \ h \end{bmatrix} $ $

para o primeiro e o segundo qubits, respectivamente, isso é equivalente a aplicar o unitário de dois qubit fornecido por seu produto tensor: $ $ \begin{bmatrix} a \ b\\\\ c \ d \end{bmatrix} \otimes \begin{bmatrix} e \ f\\\\ g \ h \end{bmatrix} = \ Comece {bmatrix} AE \ AF \ is \ BF \\\\ AG \ Ah \ BG \ BH \\\\ CE \ CF \ de \ DF \\\\ CG \ ch \ DG \ DH \end{bmatrix}. $ $, portanto, podemos formar dois grupos de qubit assumindo o produto tensor de algumas Gates de qubit individuais conhecidos. Alguns exemplos de Gates de duas qubit incluem $H \otimes H $, $X \otimes \boldone $ e $X \otimes Z $.

Observe que, embora qualquer um dos dois Gates qubit defina uma porta de dois qubit ao pegar seu produto tensor, o converso não será verdadeiro. Nem todas as Gates de duas qubit podem ser escritas como o produto tensor de Gates de qubit único.  Essa porta é chamada de portão *Entangling* . Um exemplo de um portão Entangling é o portão CNOT.

A intuição por trás de uma porta controlada não pode ser generalizada para Gates arbitrárias.  Um portão controlado em geral é um portão que atua como identidade (ou seja, ele não tem nenhuma ação), a menos que um qubit específico seja $1 $.  Denotamos um unitário controlado, controlado nesse caso no qubit rotulado $x $, com um $ \Lambda\_x (U) $.  Por exemplo, $ \Lambda_0 (U) e\_{1}\otimes {\psi} = e\_{1}\otimes U {\psi} $ e $ \Lambda\_0 (U) e\_{0}\otimes {\psi} = e\_{0}\otimes{\psi} $ , em que $e\_$0 e $e\_$1 são os vetores de base computacional para um único qubit correspondente aos valores $0 $ e $1 $.  Por exemplo, considere a seguinte porta $ $Z controlada, então podemos expressar isso como $ $ \Lambda\_0 (Z) = \begin{bmatrix}1 & 0 & 0 & 0\\\\0 & 1 & 0 & 0\\\\0 & 0 & 1 & 0\\\\0 & 0 & 0 &-1 \end{bmatrix} = (\boldone\otimes H) \operatorname{CNOT} (\boldone\otimes H).
$$

A criação de unidades controladas de maneira eficiente é um grande desafio.  A maneira mais simples de implementar isso requer formar um banco de dados de versões controladas de Gates fundamentais e substituir cada portão fundamental na operação unitário original por sua contraparte controlada.  Geralmente, isso é muito inútil e a Insight inteligente muitas vezes pode ser usada apenas para substituir alguns Gates por versões controladas para obter o mesmo impacto.  Por esse motivo, fornecemos em nossa estrutura a capacidade de executar o método simples de controlar ou permitir que o usuário defina uma versão controlada do unitário se uma versão de ajuste manual for conhecida.

Os Gates também podem ser controlados usando informações clássicas.  Um não portão, por exemplo, controlado de forma clássica, é apenas um não portão comum, mas só será aplicado se um bit clássico for $1 $ em oposição a um bit quântico.  Nesse sentido, um portão controlado de forma clássica pode ser considerado como uma instrução If no código Quantum, no qual a Gate é aplicada somente em uma ramificação do código.


Como no caso de qubit único, um conjunto de portão de dois qubit é universal se qualquer matriz de US $4 \ vezes $4 pode ser aproximada por um produto de Gates desse conjunto para precisão arbitrária.
Um exemplo de um conjunto de portão universal é o portão Hadamard, o portão T e o portão CNOT. Ao pegar produtos desses Gates, podemos aproximar qualquer matriz de dois qubits.

## <a name="many-qubit-systems"></a>Muitos sistemas qubit
Seguimos exatamente os mesmos padrões explorados no caso de duas qubit para criar vários Estados de Quantum de qubit de sistemas menores.  Esses Estados são criados com a formação de produtos tensor de Estados menores.  Por exemplo, considere a codificação da cadeia de caracteres de bits $1011001 $ em um computador Quantum.  Podemos codificá-lo como

$ $1011001 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{ bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}.
$$

As Gates da Quantum funcionam exatamente da mesma maneira.  Por exemplo, se quisermos aplicar o $X $ Gate ao primeiro qubit e, em seguida, executar um CNOT entre o segundo e o terceiro qubits, poderemos expressar essa transformação como

\begin{align} & (X \otimes \operatorname{CNOT}_{12}\otimes \boldone\otimes \boldone \otimes \boldone \otimes \boldone) \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\ OTimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\ OTimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\\\\ & \qquad\qquad\equiv 0011001.
\end{align}

Em muitos sistemas qubit, muitas vezes há necessidade de alocar e desalocar qubits que sirvam como memória temporária para o computador Quantum.  Tal qubit é chamada de ancilla.  Por padrão, supomos que o estado qubit seja inicializado para $e _0 $ na alocação.  Supomos que ele é retornado novamente para $e _0 $ antes da desalocação.  Essa suposição é importante porque, se um ancilla qubit se tornar confusas com outro registro de qubit quando ele se tornar desalocado, o processo de desalocação danificará o ancilla.  Por esse motivo, sempre presumimos que esses qubits sejam revertidos para seu estado inicial antes de serem liberados.

Finalmente, embora novos Gates precisem ser adicionados ao nosso conjunto de porta para obter a computação Quantum universal para dois computadores Quantum qubit, nenhum novo Gates precisa ser introduzido no caso de várias qubit.  O Gates $H $, $T $ e CNOT formam uma porta universal definida em muitos qubits porque qualquer transformação unitário geral pode ser quebrada em uma série de duas rotações de qubit.  Em seguida, podemos aproveitar a teoria desenvolvida para o caso de duas qubit e usá-la novamente aqui quando tivermos muitos qubits.

Embora a notação linear algébricas que temos usado até agora pode, certamente, ser usada para descrever os Estados de qubit, ela se torna cada vez mais complicada à medida que aumentamos o tamanho dos Estados.  O vetor de coluna resultante para uma cadeia de caracteres de comprimento de 7 bits, por exemplo, é $128 $ dimensional, o que o torna expressando usando a notação descrita anteriormente muito complicada.  Por esse motivo, apresentamos uma notação comum na computação Quantum que nos permite descrever de forma concisa esses vetores altamente dimensionais.
