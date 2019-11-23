---
title: Pauli medições | Microsoft Docs
description: Medições de Pauli
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 7bea821be7e26e72f2860278486d35be676ca63d
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183714"
---
# <a name="pauli-measurements"></a>Medições de Pauli

Nas discussões anteriores, concentramos-se em medidas de base computacional.  Na verdade, há outras medidas comuns que ocorrem na computação Quantum que, de uma perspectiva de notação, são convenientes para expressar em termos de medidas de base computacional.  O conjunto mais comum dessas medidas são as *medidas Paulis*.  Nesses casos, é comum discutir a medição de um operador Pauli, em geral, um operador como $X, Y, Z $ ou $Z \otimes Z, X\otimes X, X\otimes Y $ e assim por diante.  Discutir a medição em termos de operadores Pauli é especialmente comum no subcampo de correção de erro Quantum. Em Q #, seguimos uma convenção semelhante; Agora, explicamos essa exibição alternativa de medidas.

Antes de se aprofundar nos detalhes de como pensar em uma medida Pauli, é útil pensar em que a medição de um único qubit dentro de um computador Quantum faz o estado Quantum.  Imagine que tenhamos um estado de Quantum $n $-qubit; Depois, a medição de um qubit regra imediatamente a metade das possibilidades de $2 ^ n $ em que o estado pode estar.  Em outras palavras, a medida projeta o estado da Quantum em um dos dois espaços.  Podemos generalizar a maneira como pensamos na medição para refletir isso.

Para identificar esses subespaços de forma concisa, precisamos de uma linguagem para descreve-los.  Uma maneira de fazer isso é descrever os dois subespaços especificando-os por meio de uma matriz que tem apenas dois eigenvalues exclusivos, tirados pela Convenção para ser $ \pm $1.  O exemplo mais simples disso é:

$ $ Z = \begin{bmatrix} 1 & 0 \\\\ 0 &-1 \end{bmatrix}.
$$

A matriz Pauli $ $Z claramente tem dois eigenvectors $ \ket{0}$ e $ \ket{1}$ com eigenvalues $ \pm $1.  Portanto, se medirmos o qubit e obtivermos $ \ket{0}$, estamos no eigenspace de $ + $1 (o conjunto de todos os vetores formados de somas de eigenvectors com apenas eigenvalues positivo ou somente negativo) do operador e, se medirmos $ \ket{1}$, estamos no eigenspace $-$1 de $Z $.  Esse processo é mencionado na linguagem de medidas Pauli como "medindo Pauli $Z $" e é totalmente equivalente a executar uma medição de base computacional.

É claro que qualquer matriz de $2 \ vezes $2 que seja uma transformação unitário de $Z $ também satisfaça a esses critérios.  Isso significa que também poderíamos considerar a matriz $A = U ^ \dagger Z U $, para qualquer matriz unitário $U $, a fim de fornecer uma matriz que defina os dois resultados de uma medição em seu $ \pm $1 eigenvectors.  A notação de medidas Pauli faz referência a isso identificando as medidas $X, Y, Z $ como medidas equivalentes que podem ser feitas para obter informações de um qubit.  Essas medidas são fornecidas abaixo para sua conveniência.

$ $ \begin{array}{| c | c |} medição de \text{Pauli} & U\\\\ Z & \boldone\\\\ X & H\\\\ Y & HS ^ \dagger\\\\ \end{array} $ $

Ou seja, usar essa linguagem, "Measure $Y $" é equivalente a aplicar $HS ^ \dagger $ e, em seguida, medir na base computacional, em que $S $ é a chamada de portão de fase fornecida por

$ $ \begin{bmatrix}1 & 0\\\\ 0 & i\end {bmatrix}.
$$

Também é equivalente a aplicar $HS ^ \dagger $ ao vetor de estado Quantum e, em seguida, medir $Z $.  Em seguida, o estado correto seria encontrado transformando-o de volta para a base computacional, que resulta na aplicação de $SH $ ao vetor de estado Quantum.

## <a name="q-outcome-classical-information-obtained-from-quantum-state"></a>Q # informações clássicas de resultado obtidas do estado Quantum
Em Q #, dizemos que o resultado, ou seja, as informações clássicas extraídas da interação com o estado, é $j $, que está no conjunto $\{0, 1\}$ se o resultado estiver na eigenspace de $ (-1) ^ j $, do operador Pauli medido.

As medições de operadores qubit Pauli são definidas da mesma forma, como visto em:

$ $ Z\otimes Z = \begin{bmatrix}1 & 0 & 0 & 0\\\\ 0 &-1 & 0 & 0\\\\ 0 & 0 &-1 & 0\\\\ 0 & 0 & 0 & 1 \ fim {bmatrix}.
$$

Assim, os produtos tensor de dois operadores Pauli $ $Z $ formam uma matriz composta de dois espaços consistindo em US $ + $1 e $-$1 eigenvalues.  Assim como no caso de qubit único, ambos constituem um meio-espaço que significa que metade do espaço de vetor acessível pertence ao eigenspace $ + $1 e à metade restante para o $-$1 eigenspace.  Em geral, é fácil ver a definição do produto tensor de que qualquer produto tensor de operadores Pauli $ $Z $ e a identidade também obedece a isso.  Por exemplo,

$ $ Z\otimes\boldone = \begin{bmatrix} 1 & 0 & 0 & 0\\\\ 0 & 1 & 0 & 0\\\\ 0 & 0 &-1 & 0\\\\ 0 & 0 & 0 &-1 \ fim {bmatrix}.
$$

Como antes, qualquer transformação unitário dessas matrizes também descreve dois semestres rotulados por $ \pm $1 eigenvalues.  Por exemplo, $X \otimes X = H\otimes H (Z\otimes Z) H\otimes H $ da identidade que $Z = HXH $.  Semelhante ao caso qubit, todas as medidas de Pauli de duas qubit podem ser escritas como $U ^ \dagger (Z\otimes \id) U $ para $4 \ vezes $4 matrizes unitários $U $.  Enumeramos as transformações na tabela a seguir, em que apresentamos para conveniência o portão de troca que troca qubits $0 $ e $1 $: $ \operatorname{SWAP} = \operatorname{CNOT}\_{01}\operatorname{CNOT}\_{10}\operatorname{CNOT}\_{01}$:

$ $ \begin{array}{| c | c |} \text{Pauli medida} & U\\\\ \hline Z\otimes \boldone & \boldone\otimes \boldone\\\\ X\otimes \boldone & H\otimes \boldone\\\\ Y\otimes \boldone & HS ^ \dagger\otimes \boldone\\\\ \boldone \otimes Z & \operatorname{SWAP}\\\\ \boldone \otimes X & (H\otimes \boldone) \operatorname{SWAP}\\\\ \boldone \otimes Y & (HS ^ \dagger\otimes \boldone) \ OperatorName {SWAP}\\\\ Z\otimes Z & \operatorname{CNOT}\_{10}\\\\ X\otimes Z & \operatorname{CNOT}\_{10}(H\otimes \boldone)\\\\ Y\otimes Z & \operatorname{CNOT}\_{10}(HS ^ \dagger\otimes \boldone)\\\\ Z\otimes X & \operatorname{CNOT}\_{10}(\boldone\otimes H)\\\\ X\otimes X & \operatorname{CNOT}\_{10}(H \ OTimes H)\\\\ Y\otimes X & \operatorname{CNOT}\_{10}(HS ^ \dagger\otimes H)\\\\ Z\otimes Y & \operatorname{CNOT}\_{10}(\boldone \otimes HS ^ \dagger)\\\\ X\otimes Y & \operatorname{CNOT}\_{10}(H\otimes HS ^ \dagger)\\\\ Y\otimes Y & \operatorname{CNOT}\_{10}(HS ^ \dagger\otimes HS ^ \dagger)\\\\ \end{array} $ $

Aqui, a porta $ \operatorname{CNOT}\_{10}$ é exibida pelo seguinte motivo.  Cada medida de Pauli que não inclui a matriz $ \boldone $ é equivalente a um unitário para $Z \otimes Z $ pelo raciocínio acima.  O eigenvalues de $Z \otimes Z $ só depende da paridade da qubits que compõe cada vetor de base computacional e as operações controladas que aparecem nessa lista servem para calcular essa paridade e armazená-las no primeiro bit.  Depois que o primeiro bit for medido, poderemos recuperar a identidade do meio de espaço resultante, que é equivalente a medir o operador Pauli.

Uma observação adicional, embora possa ser tentador pressupor que medir $Z \otimes Z $ é o mesmo que medir $Z \otimes \id $ e $ \id \otimes Z $, essa suposição seria falsa.  O motivo é que medir $Z \otimes Z $ projeta o estado da Quantum no eigenstate de $ + $1 ou $-$1 desses operadores.  Medindo $Z \otimes \id $ e $ \id \otimes Z $ projeta o vetor de estado Quantum primeiro em um semestre de $Z \otimes \id $ e, em seguida, em um semestre de $ \id \otimes Z $.  Como há quatro vetores de base computacional, a execução de ambas as medidas reduz o estado para um quarto de espaço e, portanto, reduz-a para um único vetor de computação.


## <a name="correlations-between-qubits"></a>Correlações entre qubits
Outra maneira de observar a medição de produtos tensor de Paulis, como $X \otimes X $ ou $Z \otimes Z $, é que essas medidas permitem que você examine as informações armazenadas nas correlações entre as duas qubits.  Medir $X \otimes \id $ permite que você examine as informações armazenadas localmente no primeiro qubit.  Embora os dois tipos de medidas sejam igualmente valiosos na computação Quantum, o primeiro ilumina o poder da computação Quantum. Ele revela que, na computação Quantum, muitas vezes as informações que você deseja aprender não são armazenadas em nenhum único qubit, mas armazenadas não localmente em todas as qubits de uma vez e apenas examinando-as por meio de uma medida conjunta com $Z \otimes Z $ faz com que essas informações se tornem manifesto.

Operadores Pauli arbitrários, como $X \otimes Y \otimes Z \otimes \boldone $, também podem ser medidos.  Todos esses produtos tensor de Pauli Operators têm apenas duas eigenvalues $ \pm $1 e ambas as eigenspaces constituem metade de espaços de todo o espaço de vetor.  Portanto, eles coincidem com os requisitos declarados acima.

Em Q #, essas medidas retornam $j $ se a medida produz um resultado no eigenspace de sinal $ (-1) ^ j $.  Ter isso como um recurso interno em Q # é útil porque a medição desses operadores requer cadeias longas de Gates e transformações de base controladas para descrever a diagonal $U $ Gate necessário para expressar a operação como um produto tensor de $Z $ e $ \id $.  Ao simplesmente ser capaz de especificar que você deseja realizar uma dessas medidas predefinidas, você não precisa se preocupar em como transformar sua base de forma que uma medida de base computacional forneça as informações necessárias.  O Q # trata todas as transformações de base necessárias para você automaticamente. Consulte [a referência da biblioteca do Q # para medições de Pauli](/qsharp/api/canon/microsoft.quantum.canon.measurepaulis)

## <a name="the-no-cloning-theorem"></a>O teorema no-Cloning
As informações da Quantum são poderosas.  Ele nos permite fazer coisas incríveis, como números de fator exponencialmente mais rápidos do que os melhores algoritmos clássicos conhecidos, ou simular com eficiência sistemas de informações de alta correlação que exigem, de modo clássico, o custo exponencial para simular com precisão.  No entanto, há limitações no poder da computação Quantum.  Uma dessas limitações é fornecida pelo *teorema no-Cloning*.

O teorema no-Cloning é adequadamente nomeado.
Ele não permite a clonagem de Estados de Quantum genérico por um computador Quantum.
A prova do teorema é bastante simples.
Embora uma prova completa do teorema sem clonagem seja um pouco técnica para nossa discussão aqui, a prova do teorema no caso em que o computador Quantum em questão não tem ancilla qubits adicional está dentro de nosso escopo (ancilla qubits são qubits usados para espaço transitório durante uma computação e são facilmente usados e gerenciados em Q #, consulte <xref:microsoft.quantum.techniques.qubits>).
Para esse computador Quantum, a operação de clonagem deve ser uma matriz unitário. Não permitimos a medição, já que corromperia o estado Quantum que estamos tentando clonar. A matriz unitário que desejamos deve ter a propriedade $ $ U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}, $ $ para qualquer estado $ \ket{\psi} $.
Em seguida, a propriedade linear da multiplicação de matriz implica que, para qualquer segundo estado Quantum $ \ket{\phi} $,

\begin{align} & U\left [\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \right) \right] \ket{0}= \frac{1}{\sqrt{2}} U\ket {\ Phi} \ ket{0}+ \frac{1}{\sqrt{2}} U\ket {\ psi} \ ket{0}\\\\ & \qquad\qquad = \frac{1}{\sqrt{2}} \left (\ket{\phi}\ket{\phi} + \ket{\psi}\ket{\psi}\right)\\\\ & \qquad\qquad\ne \left (\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \ Right) \right) \otimes\left (\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \right) \right).
\end{align}

Isso fornece a intuição fundamental por trás do teorema sem clonagem: qualquer dispositivo que copia um estado de Quantum desconhecido deve induzir erros em pelo menos alguns dos Estados que ele copia.  Embora a principal suposição de que o Cloner atue linearmente no estado de entrada possa ser violada pela adição de ancilla e medida do ancilla qubits, essas interações também vazam informações sobre o sistema por meio das estatísticas de medição e evitam clonagem exata nesses casos também.  Para obter uma prova mais completa dos teorema sem clonagem, consulte [para obter mais informações](xref:microsoft.quantum.more-information).

O teorema no-Cloning é importante para uma compreensão qualitativa da computação Quantum porque, se você puder clonar os Estados da Quantum de forma incara, terá uma capacidade quase mágico de aprender com os Estados da Quantum.  Na verdade, você poderia violar o princípio de incerteza de vaunted da Heisenberg.  Como alternativa, você pode usar um Cloner ideal para pegar um único exemplo de uma distribuição de Quantum complexa e aprender tudo o que poderia ser possível saber sobre essa distribuição de apenas uma amostra.  Isso seria como você invertendo uma moeda e observando a cabeça e, depois, ao informar a um amigo sobre o resultado que eles respondem "Ah, a distribuição dessa moeda deve ser Bernoulli com $p = 0.512643 \ ldots $!"  Essa instrução seria não sensical porque um pouco de informação (o resultado dos cabeçotes) simplesmente não pode fornecer muitas informações necessárias para codificar a distribuição sem informações substanciais anteriores.  Da mesma forma, sem informações anteriores, não podemos clonar perfeitamente um estado Quantum da mesma forma que não podemos preparar uma Ensemble dessas moedas sem saber $p $.

As informações não são gratuitas na computação Quantum.  Cada qubit medido fornece uma única informação, e o teorema no-Cloning mostra que não há nenhum backdoor que possa ser explorado para contornar a compensação fundamental entre as informações obtidas sobre o sistema e o distúrbios invocado sobre ele.

