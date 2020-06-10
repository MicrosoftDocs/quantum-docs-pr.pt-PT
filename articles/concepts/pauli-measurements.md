---
title: Medições Pauli
description: Aprenda a trabalhar com operações de medição de Pauli de solteiro e multi-qubit.
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
ms.openlocfilehash: 115c1703e433f24930e4be61b545048c95da28d1
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630307"
---
# <a name="pauli-measurements"></a>Medições Pauli

Nas discussões anteriores, concentrámo-nos em medições computacionais.
Na verdade, existem outras medições comuns que ocorrem na computação quântica que, do ponto de vista notacional, são convenientes de expressar em termos de medições de base computacional.
À medida que trabalha com Q#, o tipo de medições mais comum que irá encontrar provavelmente serão *as medições de Pauli*, que generalizam as medições de base computacional para incluir medições em outras bases, e de paridade entre diferentes qubits.
Nestes casos, é comum discutir a medição de um operador Pauli, em geral um operador como $X,Y,Z $ ou $Z \otimes Z, X \otimes X, X \otimes Y , $ etc.

> [!TIP]
> Em Q#, os operadores de Pauli multi-qubit são geralmente representados por matrizes do tipo `Pauli[]` .
> Por exemplo, para representar $X \otimes Z \otimes $ Y, pode utilizar a matriz `[PauliX, PauliZ, PauliY]` .

Discutir a medição em termos de operadores pauli é especialmente comum no subcampo da correção de erros quânticos.
Em Q#, seguimos uma convenção semelhante; agora explicamos esta visão alternativa das medições.

Antes de aprofundar os detalhes de como pensar de uma medição de Pauli, é útil pensar sobre o que medir um único qubit dentro de um computador quântico faz ao estado quântico.
Imagine que temos um $ estado quântico $n-qubit; em seguida, medir um qubit imediatamente exclui metade das possibilidades de $2^n em que o $ estado poderia estar dentro.
Por outras palavras, a medição projeta o estado quântico num dos dois semi-espaços.
Podemos generalizar a forma como pensamos sobre a medição para refletir esta intuição.

Para identificar concisamente estes subespaços, precisamos de uma linguagem para os descrever.
Uma forma de descrever os dois subespaços é especificando-os através de uma matriz que tem apenas dois valores eigenvalues únicos, tomados por convenção para ser $\pm 1 $ .
Para um simples exemplo de descrever subespaços desta forma, considere $ $Z:

$$ \start{align}
  Z & = \{ bmatrix } 1 & 0 \\ \\ 0 & -1 \end{ bmatrix } .
\end{align}
$$

Ao ler os elementos diagonais da matriz Pauli-$Z, $ podemos ver que $Z $ tem dois eigenvectors, $\ket{0$ } e $\ket{1 } $, com correspondentes eigenvalues $\pm 1 $ .
Assim, se medirmos o qubit e `Zero` obtermos (correspondente ao estado $\ket{0 } $), sabemos que o estado do nosso qubit é um estado de $+1 $ do operador $ $Z.
Da mesma forma, se `One` obtivermos, sabemos que o estado do nosso qubit é um estado de $ $1 de $Z $ .
Este processo é referido na linguagem das medições de Pauli como "medição de Pauli $Z $ ", e é inteiramente equivalente a realizar uma medição de base computacional.

Qualquer matriz de \times $2 2 $ que seja uma transformação unitária de $Z $ também satisfaz estes critérios.
Ou seja, também poderíamos usar uma matriz $A=U^\dagger Z $ U, onde $U $ é qualquer outra matriz unitária, para dar uma matriz que define os dois resultados de uma medição nos seus $\pm 1 $ eigenvectors.
A notação das medições de Pauli refere esta equivalência unitária identificando as medições $X,Y,Z $ como medidas equivalentes que se poderia fazer para obter informações a partir de um qubit.
Estas medições são dadas abaixo para conveniência.


|Medição de Pauli  |Transformação unitária  |
|-------------------|------------------------|
| $Z$               | $\boldone$             |
| $X$               | $H$                    |
| $Y$               | $HS^{\dagger}$         |

Ou seja, usando esta linguagem, "medir $ $Y" é equivalente a aplicar $HS^\dagger $ e, em seguida, medir na base computacional, onde [`S`](xref:microsoft.quantum.intrinsic.s) é uma operação quântica intrínseca às vezes chamada de "portão de fase", e pode ser simulada pela matriz unitária

$$ \start{align}
    S = \start{bmatrix}
        1 & 0 \\ \\ 0 & i \end{ bmatrix } .
\end{align}
$$

É também equivalente à aplicação de $HS^\dagger $ ao vetor de estado quântico e, em seguida, medir $Z $ , de modo que a seguinte operação é equivalente `Measure([PauliY], [q])` a:

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

O estado correto seria então encontrado transformando-se de volta à base computacional, que equivale a aplicar $SH $ ao vetor de estado quântico; no corte acima, a transformação de volta à base computacional é tratada automaticamente pela utilização do `within … apply` bloco.

Em Q#, dizemos o resultado---é, a informação clássica extraída de interagir com o estado---is é dada por um `Result` valor $j \in \\ {\texttt{Zero, } \texttt{One } \\ }$ indicando se o resultado está no espaço $(-1)^j $ eigenspace do operador Pauli medido.


## <a name="multiple-qubit-measurements"></a>Medições de múltiplos qubits

As medições dos operadores de Pauli multi-qubit são definidas da mesma forma, como visto a partir de:

$$ Z \otimes Z = \start} bmatrix }1 &0 &0&\\\\ 0 & 0 -1&0&0 \\\\ 0&0 & -1&0 \\\\&0&0&1 { \end bmatrix } .
$$

Assim, os produtos de tensor de dois operadores Pauli-$Z $ formam uma matriz composta por dois espaços compostos por $+1 $ e $-1 $ egévaues.
Tal como acontece com o caso single-qubit, ambos constituem um meio espaço, o que significa que metade do espaço vetorial acessível pertence ao espaço de $+1 $ e a restante metade para o espaço eigenspace de $-1. $
Em geral, é fácil constatar pela definição do produto tensor que qualquer produto tensor de operadores pauli-$Z $ e a identidade também obebe.
Por exemplo,

$$ \start{align}
    Z \otimes \boldone = \start{bmatrix}
        1 & 0 & 0 & \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & -1 & 0 \\ \\ & 0 & 0 & -1 \end. bmatrix }
\end{align}
$$

Como antes, qualquer transformação unitária de tais matrizes também descreve dois semi-espaços rotulados por $\pm 1 $ eigenvalues.
Por exemplo, $X \otimes X = \otimes H(Z \otimes Z)H \otimes H da identidade que $ $Z=HXH $ .
Semelhante ao caso de um qubit, todas as medições pauli de dois qubits podem ser escritas como $U^\dagger (Z \otimes \id) U $ por $4 \times 4 $ matrizes unitárias $U $ . Enumeramos as transformações na tabela seguinte.

> [!NOTE]
> Na tabela abaixo, usamos $\operatorname{SWAP } $ para indicar a matriz $$ \start{align}
>     \operatorname{SWAP } & = \left(\start{matrix}
>         1 & 0 & 0 & 0 \\ \\ & 0 & 1 & \\ \\ 0 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{matrix } \end {right) \end{align}
> $$ usado para simular a operação intrínseca. [`SWAP`](xref:microsoft.quantum.intrinsic)

|Medição de Pauli     |Transformação unitária  |
|----------------------|------------------------|
| $Z \otimes \boldone$ | $\boldone \otimes \boldone$ |
| $Z \otimes \boldone$ | $\boldone \otimes \boldone$ |
| $X \otimes \boldone$ | $H \otimes \boldone$ |
| $Y \otimes \boldone$ | $HS^\dagger \otimes \boldone$ |
| $\boldone \otimes Z$ | $\operatorname{SWAP}$ |
| $\boldone \otimes X$ | $(H \otimes \boldone)\operatorname{SWAP}$ |
| $\boldone \otimes Y$ | $(HS^\dagger \otimes \boldone)\operatorname{SWAP}$ |
| $Z \otimes Z$ | $\operatorname{CNOT } \_ {10}$ |
| $X \otimes Z$ | $\operatorname{CNOT } \_ {10 } (H \otimes \boldone)$ |
| $Y \otimes Z$ | $\operatorname{CNOT } \_ {10 } (HS^\dagger \otimes \boldone)$ |
| $Z \otimes X$ | $\operatorname{CNOT } \_ {10 } (\boldone \otimes H)$ |
| $X \otimes X$ | $\operatorname{CNOT } \_ {10 } (H \otimes H)$ |
| $Y \otimes X$ | $\operatorname{CNOT } \_ {10 } (HS^\dagger \otimes H)$ |
| $Z \otimes Y$ | $\operatorname{CNOT } \_ {10 } (\boldone \otimes HS^\dagger)$ |
| $X \otimes Y$ | $\operatorname{CNOT } \_ {10 } \otimes (HS^\dagger)$ |
| $Y \otimes Y$ | $\operatorname{CNOT } \_ {10 } (HS^\dagger \otimes HS^\dagger)$ |

Aqui, a [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operação aparece pelo seguinte motivo.
Cada medição de Pauli que não inclua a matriz de $\boldone $ equivale a um unitário a $Z Z \otimes pelo raciocínio $ acima.
Os valores de eigenvalus de $Z \otimes Z $ dependem apenas da paridade dos qubits que compõem cada vetor de base computacional, e as operações não controladas servem para calcular esta paridade e armazená-la na primeira parte.
Depois, uma vez medida a primeira parte, podemos recuperar a identidade do meio-espaço resultante, o que equivale a medir o operador Pauli.

Uma nota adicional: embora possa ser tentador assumir que medir $Z Z é o mesmo que \otimes $ medir sequencialmente $Z \otimes \mathbb{1$ } e, em seguida, $\mathbb{1 } \otimes $ Z, esta suposição seria falsa.
A razão é que a medição $Z \otimes Z projeta o estado $ quântico para o estado de $+1 $ ou $-1 $ destes operadores.
Medindo $Z \otimes \mathbb{1$ } e, em seguida, $\mathbb{1 } \otimes Z $ projeta o vetor de estado quântico primeiro em um meio espaço de $Z \otimes \mathbb{1$ } e, em seguida, em um meio espaço de $\mathbb{1 } \otimes Z $ . Como existem quatro vetores de base computacional, realizar ambas as medições reduz o estado a um quarto de espaço e, portanto, reduz-o a um único vetor de base computacional.

## <a name="correlations-between-qubits"></a>Correlações entre qubits
Outra forma de olhar para a medição de produtos de tensor de matrizes Pauli, como $X \otimes X $ ou $Z \otimes $ Z, é que estas medições permitem olhar para a informação armazenada nas correlações entre os dois qubits.
Medir $X \otimes \id $ permite-lhe olhar para informações que são armazenadas localmente no primeiro qubit.
Embora ambos os tipos de medições sejam igualmente valiosos na computação quântica, o primeiro ilumina o poder da computação quântica.
Revela que na computação quântica, muitas vezes a informação que deseja aprender não é armazenada em qualquer qubit, mas sim armazenada não localmente em todos os qubits ao mesmo tempo, e, portanto, apenas olhando para ela através de uma medição conjunta (por exemplo, $Z \otimes Z $ ) esta informação torna-se manifesta.

Por exemplo, na correção de erros, muitas vezes queremos saber que erro ocorreu enquanto não aprendemos nada sobre o estado que estamos a tentar proteger.
A [amostra de código bit-flip](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) mostra um exemplo de como pode fazê-lo usando medidas como $Z \otimes Z \otimes \id $ e $\id \otimes Z \otimes Z $ .
<!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded. -->

Operadores arbitrários de Pauli, tais como $X \otimes Y \otimes Z \otimes \boldone $ também podem ser medidos.
Todos estes produtos de tensor dos operadores pauli têm apenas dois eigenvalues $\pm 1 $ e ambos os espaços eigen constituem meio espaço de todo o espaço vetorial.
Assim, coincidem com os requisitos acima indicados.

Em Q#, tais medições regressam $j $ se a medição render um resultado no espaço eigen do sinal $(-1)^j $ .
Ter as medidas Pauli como uma característica incorporada em Q# é útil porque a medição de tais operadores requer longas cadeias de portões NÃO controlados e transformações de base para descrever a diagonalização $U $ portão necessário para expressar a operação como um produto de tensor de $Z e $ $\id $ . Ao ser capaz de especificar que deseja fazer uma destas medições pré-definidas, não precisa de se preocupar em como transformar a sua base de modo a que uma medição de base computacional forneça as informações necessárias.
Q# lida automaticamente com todas as transformações de base necessárias para si.
Para mais informações, consulte as [`Measure`](xref:microsoft.quantum.intrinsic.measure) [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operações e operações.

## <a name="the-no-cloning-theorem"></a>O Teorema da Não Clonagem

A informação quântica é poderosa.
Permite-nos fazer coisas incríveis, como números de fatores exponencialmente mais rápidos do que os algoritmos clássicos mais conhecidos, ou simular eficientemente sistemas de eletrões correlacionados que clássicamente requerem custos exponenais para simular com precisão.
No entanto, existem limitações ao poder da computação quântica.
Uma dessas limitações é dada pelo Teorema da *Não Clonagem.*

O teorema de não clonagem tem o nome apropriado.
Não permite a clonagem de estados quânticos genéricos por um computador quântico.
A prova do teorema é notavelmente simples.
Embora uma prova completa do teorema da não clonagem seja um pouco técnica demais para a nossa discussão aqui, a prova no caso de não haver qubits auxiliares adicionais está dentro do nosso âmbito (qubits auxiliares são qubits usados para o espaço de risco durante um cálculo e são facilmente utilizados e geridos em Q#, ver [qubits emprestados).](xref:microsoft.quantum.guide.qubits#borrowed-qubits)

Para tal computador quântico, a operação de clonagem deve ser descrita por uma matriz unitária.
Não permitimos a medição, uma vez que iria corromper o estado quântico que estamos a tentar clonar.
Para simular a operação de clonagem, queremos que a matriz unitária tenha a propriedade que $$ U \ket { } \psi \ket {0 } = \ket { } \psi \ket { \ket \psi}
$$ por qualquer estado $\ket { \psi } $.
A propriedade linear da multiplicação da matriz implica então que para qualquer segundo estado quântico $\ket { \phi } $,

$$ \start{align}
    U\frac{1 } {\sqrt{2 } }\left\ket { \phi } \ket { \\ket \psi } \direita) \ket{0}
    & = \frac{1 } {\sqrt{2 } } U \ket { \phi } \ket{0}
      + \frac{1 } {\sqrt{2 } } U \ket { } \ket {0 } \\ \\ & = \frac{1 } {\sqrt{2 } } \ket { } \phi \ket { \phi } \ket \ket { \ket \ket } \ket { \ket \ket \ket \psi \ket \ket \psi}
        \direita) \\ \\ & \ne \esquerda\ \frac{1 } {\sqrt{2}\left\ket } { \ket \phi } +\ket { \psi } \right) \otimes \f\frac{1 } {\sqrt{2}\left(\ket } { \phi } +\ket { \psi } \right).
\end{align}
$$

Isto fornece a intuição fundamental por trás do Teorema da Não Clonagem: qualquer dispositivo que copie um estado quântico desconhecido deve induzir erros em pelo menos alguns dos estados que copia.
Embora o pressuposto-chave de que o cloner age linearmente sobre o estado de entrada pode ser violado através da adição e medição de qubits auxiliares, tais interações também vazam informações sobre o sistema através das estatísticas de medição e impedem a clonagem exata em tais casos também.
Para obter uma prova mais completa do teorema de não clonagem consulte [para mais informações](xref:microsoft.quantum.more-information).

O teorema da não clonagem é importante para a compreensão qualitativa da computação quântica, porque se pudéssemos clonar estados quânticos de forma barata, então seria-lhe concedida uma capacidade quase mágica de aprender com os estados quânticos.
Na verdade, pode violar o princípio vago de Heisenberg.
Em alternativa, você poderia usar um clone ideal para tirar uma única amostra de uma distribuição quântica complexa e aprender tudo o que você poderia aprender sobre essa distribuição a partir de apenas uma amostra.
Seria como se lançasses uma moeda e observasses as cabeças e, em seguida, ao contares a um amigo sobre o resultado, respondendo "Ah, a distribuição dessa moeda deve ser Bernoulli com $p=0,512643\ldots!" $  Tal declaração não seria sensata porque uma parte da informação (o resultado das cabeças) simplesmente não pode fornecer as muitas informações necessárias para codificar a distribuição sem informações prévias substanciais.
Da mesma forma, sem informação prévia não podemos perfeitamente clonar um estado quântico, tal como não podemos preparar um conjunto de tais moedas sem saber $p $ .

A informação não é gratuita na computação quântica.
Cada qubit medido dá um único pedaço de informação, e o Teorema de Não Clonagem mostra que não há uma porta traseira que possa ser explorada para contornar a troca fundamental entre a informação obtida sobre o sistema e a perturbação invocada sobre ele.
