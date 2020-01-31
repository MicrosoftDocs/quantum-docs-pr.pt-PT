---
title: Medições Pauli
description: Medições Pauli
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 0a3ee595022ec389ecadcab081ccd126cb3252ae
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819914"
---
# <a name="pauli-measurements"></a>Medições Pauli

Nas discussões anteriores, concentrámo-nos nas medições computacionais.
De facto, existem outras medições comuns que ocorrem na computação quântica que, do ponto de vista notacional, são convenientes para expressar em termos de medições computacionais.
Como você trabalha com Q#, o tipo mais comum de medições que você vai encontrar provavelmente serão *medições Pauli*, que generalizam medições de base computacional para incluir medições em outras bases, e de paridade entre diferentes qubits.
Nestes casos, é comum discutir a medição de um operador Pauli, em geral um operador como $X, Y,Z$ ou $Z\otimes Z, X\otimes X, X\otimes Y$, e assim por diante.

> [!TIP]
> Em Q#, os operadores de Pauli multiqubit são geralmente representados por matrizes de tipo `Pauli[]`.
> Por exemplo, para representar $X \otimes Z \otimes Y$, pode usar a matriz `[PauliX, PauliZ, PauliY]`.

Discutir a medição em termos de operadores Pauli é especialmente comum no subcampo da correção de erros quânticos.
Em Q#, seguimos uma convenção semelhante; agora explicamos esta visão alternativa das medições.

Antes de aprofundar os detalhes de como pensar numa medição de Pauli, é útil pensar sobre o que medir um único qubit dentro de um computador quântico faz ao estado quântico.
Imagine que temos um estado quântico $n$-qubit; em seguida, medir um qubit imediatamente exclui metade das possibilidades de $2^n$ em que o estado pode estar dentro.
Por outras palavras, a medição projeta o estado quântico para um de dois espaços intermédios.
Podemos generalizar a forma como pensamos sobre a medição para refletir esta intuição.

Para identificar concisamente estes subespaços, precisamos de uma linguagem para os descrever.
Uma maneira de descrever os dois subespaços é especificando-os através de uma matriz que tem apenas dois valores eigen únicos, tomados por convenção para ser $\pm $pm 1$.
Para um simples exemplo de descrever subespaços desta forma, considere $Z$:

$$ \start{align} Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.
\end{align} $$

Ao ler os elementos diagonais da matriz Pauli-$Z$, podemos ver que $Z$ tem dois eigenvectors, $\ket{0}$ e $\ket{1}$, com os correspondentes valores $\pm $1$.
Assim, se medirmos o qubit e obtemos `Zero` (correspondente ao Estado $\ket{0}$), sabemos que o estado do nosso qubit é um eigenstate de $+1$ do operador $Z$.
Da mesma forma, se obtemos `One`, sabemos que o estado do nosso qubit é um eigenstate de $1$1$ de $Z$.
Este processo é referido na linguagem das medições de Pauli como "medindo Pauli $Z$", e é inteiramente equivalente a realizar uma medição computacional.

Qualquer matriz de $2\times de 2$ que seja uma transformação unitária de $Z$ também satisfaz este critério.
Ou seja, poderíamos também usar uma matriz $A=U^\dagger Z U$, onde $U$ é qualquer outra matriz unitária, para dar uma matriz que define os dois resultados de uma medição nos seus eigenvectores de $\pm 1$ 1$.
A notação de Pauli mede esta equivalência unitária identificando $X,Y,Z$ medições como medidas equivalentes que se poderia fazer para obter informações a partir de um qubit.
Estas medições são dadas abaixo por conveniência.


|Medição Pauli  |Transformação unitária  |
|-------------------|------------------------|
| $Z$               | $\boldone$             |
| $X$               | $H$                    |
| $Y$               | $HS^{\dagger}$         |

Ou seja, usando esta linguagem, "medir $Y$" equivale a aplicar $HS^\dagger$ e depois medir na base computacional, onde [`S`](xref:microsoft.quantum.intrinsic.s) é uma operação quântica intrínseca por vezes chamada de "portão de fase", e pode ser simulada pela matriz unitária

$$ \start{align} S = \start{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix}.
\end{align} $$

Também é equivalente a aplicar $HS^\dagger$ ao vetor do estado quântico e, em seguida, medir $Z$, de modo que a seguinte operação é equivalente a `Measure([PauliY], [q]])`:

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        H(q);
        Adjoint S(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

O estado correto seria então encontrado transformando-se de volta à base computacional, o que equivale a aplicar $SH$ ao vetor do estado quântico; no corte acima, a transformação de volta à base computacional é tratada automaticamente pela utilização do bloco `within … apply`.

Em Q#, dizemos que o resultado--- isto é, a informação clássica extraída da interação com o Estado---é dada por um valor `Result` $j \in \\{\texttt{Zero}, \texttt{One}\\}$ indicando se o resultado está no eigenspace de $(-1)^j$ do operador Pauli medido.


## <a name="multiple-qubit-measurements"></a>Medições de qubit múltiplo

As medições dos operadores pauli multiqubit são definidas da mesma forma, como visto a partir de:

$$ Z\otimes Z = \start{bmatrix}1 &0&0&0\\\\ 0&-1&0&0;0\\\\ 0&0&0\\\\ 0&0&0&1\end{bmatrix}.
$$

Assim, os produtos tensores de dois operadores Pauli-$Z$$ formam uma matriz composta por dois espaços compostos por $+1$ e $1$ eigenvalues.
Tal como acontece com o caso de um único qubit, ambos constituem um espaço de meio espaço, o que significa que metade do espaço vetorial acessível pertence ao espaço de eigenspace de $+1$ e a restante metade para o eigenspace de $1$.
Em geral, é fácil ver pela definição do produto tensor que qualquer produto tensor dos operadores Pauli-$Z$e a identidade também obedece a isso.
Por exemplo,

$$ \begin{align} Z \otimes \boldone = \start{bmatrix} 1 & 0 & 0 & 0 & 0 \\\\ 0 & 1 & 0 e 0 \\\\ 0 & 0 & -1 & 0 \\\\ 0 & 0 & 0 & -1 \{bmatrix}.
\end{align} $$

Como antes, qualquer transformação unitária de tais matrizes também descreve dois espaços semi-espaços rotulados por $\pm 1$ eigenvalues.
Por exemplo, $X\otimes X = H\otimes H(Z\otimes Z)H\otimes H$ da identidade que $Z=HXH$.
Semelhante ao caso de um qubit, todas as medições de dois qubitpaulpauli podem ser escritas como $U^\dagger (Z\otimes \id) U$ por $4\vezes 4$ 4$ matrizes unitárias $U$. Enumeramos as transformações na tabela seguinte.

> [!NOTE]
> Na tabela abaixo, usamos $\operatorname{SWAP}$ para indicar a matriz $$ \start{align} \operatorname{SWAP} & = \left(\start{matrix} 1 & 0 & 0 & 0 e 0 \\\\ 0 & 0 & 0 & 0 \\\\ 0 & 0 & 0 e 0 \\\\ 0 & 0 & 0 & 1 \end{matrix}\right) \end{align} $} usube para simular a operação intrínseca [`SWAP`](xref:microsoft.quantum.intrinsic).

|Medição Pauli     |Transformação unitária  |
|----------------------|------------------------|
| $Z \otimes \boldone$ | $\boldone \otimes \boldone$ |
| $Z\otimes \boldone$ | $\boldone\otimes \boldone$ |
| $X\otimes \boldone$ | $H\otimes \boldone$ |
| $Y\otimes \boldone$ | $HS^\dagger\otimes \boldone$ |
| $\boldone \otimes Z$ | $\operatorname {SWAP}$ |
| $\boldone \otimes X$ | $(H\otimes \boldone)\operatorname{SWAP}$ |
| $\boldone \otimes Y$ | $(HS^\dagger\otimes \boldone)\operatorname {SWAP}$ |
| $Z\otimes Z$ | $\operatorname{CNOT}\_{10}$ |
| $X\otimes Z$ | $\operatorname{CNOT}\_{10}(H\otimes \boldone)$ |
| $Y\otimes Z$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes \boldone)$ |
| $Z\otimes X$ | $\operatorname{CNOT}\_{10}(\boldone\otimes H)$ |
| $X\otimes X$ | $\operatorname{CNOT}\_{10}(H\otimes H)$ |
| $Y\otimes X$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes H)$ |
| $Z\otimes Y$ | $\operatorname{CNOT}\_{10}(\boldone \otimes HS^\dagger)$ |
| $X\otimes Y$ | $\operatorname{CNOT}\_{10}(H\otimes HS^\dagger)$ |
| $Y\otimes Y$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes HS^\dagger)$ |

Aqui, a operação [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) aparece pelo seguinte motivo.
Cada medição de Pauli que não inclui a matriz $\boldone$ é equivalente a um unitário a $Z\otimes Z$ pelo raciocínio acima.
Os valores eigen de $Z\otimes Z$ apenas dependem da paridade dos qubits que compõem cada vetor de base computacional, e as operações controladas não servem para calcular esta paridade e armazená-la na primeira parte.
Depois, uma vez medido o primeiro pedaço, podemos recuperar a identidade do meio espaço resultante, o que equivale a medir o operador Pauli.

Uma nota adicional: embora possa ser tentador assumir que medir $Z\otimes Z$ é o mesmo que medir sequencialmente $Z\otimes \mathbb{1}$ e, em seguida, $\mathbb{1} \otimes Z$, este pressuposto seria falso.
A razão é que medir $Z\otimes Z$ projeta o estado quântico para o $+1$ ou $1$ eigenstate destes operadores.
Medir $Z\otimes \mathbb{1}$ e depois $\mathbb{1} \otimes Z$ projeta o vetor do estado quântico primeiro em um espaço de $Z\otimes \mathbb{1}$ e depois para um espaço de $\mathbb{1} \otimes Z$.
Como existem quatro vetores computacionais, a realização de ambas as medições reduz o estado a um quarto de espaço e, portanto, reduz-o a um único vetor de base computacional.

## <a name="correlations-between-qubits"></a>Correlações entre qubits
Outra forma de ver a medição de produtos tensores de matrizes Pauli, como $X\otimes X$ ou $Z\otimes Z$ é que estas medidas permitem olhar para a informação armazenada nas correlações entre os dois qubits.
Medir $X\otimes \id$ permite-lhe olhar para a informação que é armazenada localmente no primeiro qubit.
Embora ambos os tipos de medições sejam igualmente valiosos na computação quântica, o primeiro ilumina o poder da computação quântica.
Revela que na computação quântica, muitas vezes a informação que pretende aprender não é armazenada em nenhum qubit, mas sim armazenada não localmente em todos os qubits ao mesmo tempo, e, portanto, apenas olhando para ela através de uma medição articular (por exemplo, $Z\ovezes Z$) faz isso informação tornar-se manifesto.

Por exemplo, na correção de erros, muitas vezes queremos saber que erro ocorreu enquanto não aprendemos nada sobre o estado que estamos a tentar proteger.
A [amostra de código bit-flip](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) mostra um exemplo de como pode fazê-lo usando medidas como $Z \otimes Z \otimes \id$ e $\id \otimes Z \otimes Z$.
<!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded. -->

Operadores arbitrários pauli como $X\otimes Y \otimes Z \otimes \boldone$ também podem ser medidos.
Todos estes produtos tensores dos operadores pauli têm apenas dois eigenvalues $\pm $pm $pm 1$ e ambos os espaços eigen constituem espaços de meio espaço de todo o espaço vetorial.
Assim, coincidem com os requisitos acima referidos.

Em Q#, tais medições regressam $j$ se a medição produzir um resultado no espaço eigendo do sinal $(-1)^j$.
Ter medições pauli como uma característica incorporada em Q# é útil porque medir tais operadores requer longas cadeias de portões controlados-NOT e transformações de base para descrever a diagonalização $U portão de$ necessário para expressar a operação como um produto tensor de $Z$ e $\id$.
Ao poder especificar que pretende fazer uma destas medições pré-definidas, não precisa de se preocupar em como transformar a sua base de modo a que uma medição de base computacional forneça as informações necessárias.
Q# lida com todas as transformações de base necessárias para si automaticamente.
Para mais informações, consulte as [operações`Measure`](xref:microsoft.quantum.intrinsic.measure) e [`MeasurePaulis`.](xref:microsoft.quantum.measurement.measurepaulis)

## <a name="the-no-cloning-theorem"></a>O Teorema sem Clonagem

A informação quântica é poderosa.
Permite-nos fazer coisas incríveis, como números de fatores exponencialmente mais rápidos do que os algoritmos clássicos mais conhecidos, ou simular eficientemente sistemas de eletrões correlacionados que requerem custos exponenciais para simular com precisão.
No entanto, existem limitações ao poder da computação quântica.
Uma dessas limitações é dada pelo *Teorema de Não Clonagem.*

O Teorema de Não Clonagem é devidamente nomeado.
Proíbe a clonagem de estados quânticos genéricos por um computador quântico.
A prova do teorema é notavelmente simples.
Embora uma prova completa do teorema de não clonagem seja demasiado técnica para a nossa discussão aqui, a prova no caso de não haver qubits auxiliares adicionais está dentro do nosso âmbito (os qubits auxiliares são qubits usados para o espaço de risco durante uma computação e são facilmente utilizados e geridos em Q#, ver <xref:microsoft.quantum.techniques.qubits>).

Para um computador quântico deste tipo, a operação de clonagem deve ser descrita por uma matriz unitária.
Nós não permitimos a medição, já que corromperia o estado quântico que estamos a tentar clonar.
Para simular a operação de clonagem, queremos que a matriz unitária seja usada para ter a propriedade que $$ U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi} $$ para qualquer estado $\ket{\psi}$.
A propriedade linearidade da multiplicação da matriz implica então que para qualquer segundo estado quântico $\ket{\phi}$,

$$ \start{align} U \left[ \frac{1}{\sqrt{2}}\left (\ket{\phi+\ket{\psi} \right) \ket{0} & = \frac{1}{\sqrt{2}} U\ket{\phi}\ket{0} \ frac{1}{\sqrt{2}} U\ket{\psi \\ \\{0}\= \frac{1}{\sqrt{2}} \left( \ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi} \{2}{1}\\ \\toc esquerda( \frac{1}{\sqrt{2}}\left (\ket{\phi}+\ket{\psi} \right).
\end{align} $$

Isto fornece a intuição fundamental por trás do Teorema de Não Clonagem: qualquer dispositivo que copie um estado quântico desconhecido deve induzir erros em pelo menos alguns dos Estados que copia.
Embora o pressuposto fundamental de que o cloner atua linearmente sobre o estado de entrada possa ser violado através da adição e medição de qubits auxiliares, tais interações também vazam informações sobre o sistema através das estatísticas de medição e impedem a exatidão clonagem em tais casos também.
Para obter uma prova mais completa do Teorema de Não Clonagem consulte [Para mais informações](xref:microsoft.quantum.more-information).

O Teorema de Não Clonagem é importante para a compreensão qualitativa da computação quântica, porque se pudesse clonar estados quânticos baratos, então teria uma capacidade quase mágica de aprender com os estados quânticos.
Na verdade, pode violar o princípio da incerteza de Heisenberg.
Em alternativa, você poderia usar um cloner ideal para tirar uma única amostra de uma distribuição quântica complexa e aprender tudo o que você poderia aprender sobre essa distribuição a partir de apenas uma amostra.
Isto seria como se você lançasse uma moeda e observasse cabeças e, em seguida, ao contar a um amigo sobre o resultado, fazendo com que respondessem "Ah a distribuição dessa moeda deve ser Bernoulli com $p=0,512643\ldots$!"  Tal afirmação seria não-sensata porque um pouco de informação (o resultado dos cabeças) simplesmente não pode fornecer os muitos pedaços de informação necessários para codificar a distribuição sem informações prévias substanciais.
Da mesma forma, sem informações prévias, não podemos clonar perfeitamente um estado quântico, tal como não podemos preparar um conjunto de tais moedas sem saber $p$.

A informação não é gratuita na computação quântica.
Cada qubit medido dá um único pouco de informação, e o Teorema de Não Clonagem mostra que não há nenhuma porta traseira que possa ser explorada para contornar a troca fundamental entre informações obtidas sobre o sistema e a perturbação invocada sobre ele.
