---
title: Vetores e matrizes em computação quântica
description: Aprenda o básico de como trabalhar com vetores e matrizes.
author: QuantumWriter
uid: microsoft.quantum.concepts.vectors
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- $
- $
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
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: f9d4e14742b7d06a6e90af0902b31fbdf17aedab
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269546"
---
# <a name="vectors-and-matrices"></a>Vetores e Matrizes

Alguma familiaridade com vetores e matrizes é essencial para entender a computação quântica. Fornecemos uma breve introdução abaixo e os leitores interessados são recomendados a ler uma referência padrão em álgebra linear como *Strang, G. (1993). Introdução à álgebra linear (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* ou uma referência online como [álgebra linear.](http://joshua.smcvt.edu/linearalgebra/)

Um vetor de coluna (ou simplesmente [*vetor)*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))$v $ de dimensão (ou tamanho) $n $ é uma coleção de números complexos $n $ $(v_1,v_2,\ldots,v_n)$ dispostos como uma coluna:

$$v =\start{bmatrix}
v_1\\\\
v_2\\\\
\vdots\\\\
v_n \end{bmatrix}$$

A norma de um vetor $v $ é definida como $\sqrt { \sum i \_ \_ #v i | ^2 } $. Diz-se que um vetor é de norma unitária (ou, em alternativa, é chamado de [*vetor unitário)*](https://en.wikipedia.org/wiki/Unit_vector)se a sua norma for $1 $ . O [*adjacente de um vetor*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v é $ denotado $v^\dagger $ e é definido como o vetor de linha seguinte onde $ \* $ denota o conjugado complexo,

$$\begin{ bmatrix }v_1 \\ \\ \vdots \\ \\ v_n \end{\dagger bmatrix } = \begin{ bmatrix }v_1^* & \cdots & v_n^* \end{bmatrix}$$

A forma mais comum de multiplicar dois vetores juntos é através do [*produto interno,*](https://en.wikipedia.org/wiki/Inner_product_space)também conhecido como um produto ponto.  O produto interno dá a projeção de um vetor para outro e é inestimável na descrição de como expressar um vetor como uma soma de outros vetores mais simples.  O produto interno entre $u $ e $v $ , denotado $\left \langle u, v é definido \right \rangle $ como

$$ \langle u, v \rangle = u^\dagger v=u \_ 1^{ \* } v_1 + \cdots + u \_ n^} \* } v \_ n.
$$

Esta notação também permite que a norma de um vetor $v $ ser escrito como $\sqrt { \langle v, \rangle } v$.

Podemos multiplicar um vetor com um número $c $ para formar um novo vetor cujas entradas são multiplicadas por $ $c. Também podemos adicionar dois vetores $u $ e $v para formar um novo $ vetor cujas entradas são a soma das entradas de $u $ e $ $v. Estas operações são retratadas abaixo:

$$\mathrm{If } ~u =\begin{bmatrix}
u_1\\\\
u_2\\\\
\vdots\\\\
u_n bmatrix } \end{~\mathrm{e } ~ v =\start{bmatrix}
    v_1\\\\
    v_2\\\\
    \vdots\\\\
    v_n \{ bmatrix } .~\mathrm{then } ~ au+bv =\begin{bmatrix}
au_1+bv_1\\\\
au_2+bv_2\\\\
\vdots\\\\
au_n+bv_n \end{ bmatrix } .
$$

Uma [*matriz*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) de tamanho $m \times n $ é uma coleção de números complexos $mn $ dispostos em $m $ linhas e colunas $n $ como mostrado abaixo:

$$M = \start{bmatrix}
M_{11 } ~~ M_{12 } ~~ \cdots ~~ M_{1n } \\ \\ M_{21 } ~~ M_{22 } ~~ \cdots ~~ M_{2n } \\ \\ \ddots\\\\
M_{m1 } ~~ M_{m2 } ~~ \cdots ~~ M_{mn } \\ \\ \end. bmatrix }

Note que um vetor de dimensão $n $ é simplesmente uma matriz de tamanho $n \vezes 1 $ . Tal como acontece com os vetores, podemos multiplicar uma matriz com um número $c $ para obter uma nova matriz onde cada entrada é multiplicada com $ $c, e podemos adicionar duas matrizes do mesmo tamanho para produzir uma nova matriz cujas entradas são a soma das respetivas entradas das duas matrizes. 

## <a name="matrix-multiplication-and-tensor-products"></a>Multiplicação de matriz e produtos de tensor

Podemos também multiplicar duas matrizes $M $ de dimensão $m \times n e $N de $ $ dimensão $n \times p $ para obter uma nova matriz $P de $ dimensão $m \vezes p $ da seguinte forma:

\iniciar{alinhar}
&\{bmatrix}
    M_{11 } ~~ M_{12 } ~~ \cdots ~~ M_{1n } \\ \\ M_{21 } ~~ M_{22 } ~~ \cdots ~~ M_{2n } \\ \\ \ddots\\\\
    M_{m1 } ~~ M_{m2 } ~~ \cdots ~~ M_{mn}
\end{bmatrix}
\começar{bmatrix}
N_{11 } ~~ N_{12 } ~~ \cdots ~~ N_{1p } \\ \\ N_{21 } ~~ N_{22 } ~~ \cdots ~~ N_{2p } \\ \\ \ddots\\\\
N_{n1 } ~~ N_{n2 } ~~ \cdots ~~ N_{np}
bmatrix } \end{\beginbmatrix}
P_{11 } ~~ P_{12 } ~~ \cdots ~~ P_{1p } \\ \\ P_{21 } ~~ P_{22 } ~~ \cdots ~~ P_{2p } \\ \\ \ddots\\\\
P_{m1 } ~~ P_{m2 } ~~ \cdots ~~ P_{mp}
\end{bmatrix}
\end{align}

onde as entradas de $P $ são $P_{ik } = \sum_j M_{ij}N_{jk } $. Por exemplo, a entrada $P_{11$ } é o produto interno da primeira linha de $M com a primeira coluna de $N $ $ . Note que uma vez que um vetor é simplesmente um caso especial de uma matriz, esta definição estende-se à multiplicação de vetores de matriz. 

Todas as matrizes que consideramos serão matrizes quadradas, onde o número de linhas e colunas são iguais, ou vetores, o que corresponde apenas a uma coluna de $ $1. Uma matriz quadrada especial é a [*matriz identitária,*](https://en.wikipedia.org/wiki/Identity_matrix)denotada $\boldone, $ que tem todos os seus elementos diagonais iguais a $1 e os $ restantes elementos iguais a $0 $ :

$$\boldone = \beginbmatrix}
1 ~~ ~~ ~~ \cdots ~~ 0\\\\
0 ~~ ~~ ~~ \cdots ~~ 0\\\\
~~ \ddots\\\\
0 ~~ ~~ ~~ \cdots ~~ 1 bmatrix } \end{.$$

Para uma matriz quadrada $ $A, dizemos que uma matriz $B $ é o seu [*inverso*](https://en.wikipedia.org/wiki/Invertible_matrix) se $AB = BA = \boldone $ . O inverso de uma matriz não precisa de existir, mas quando existe é único e denotamos $A^{-1 } $. 

Para qualquer $M matriz $ , o transposto cont ou conjugado de $M $ é uma matriz $N tal que $ $N_{ij } = M_{ji } ^ \* $. O contíguo de $M $ é geralmente denotado $M^\dagger $ . Dizemos que uma matriz $U $ é [*unitária*](https://en.wikipedia.org/wiki/Unitary_matrix) se $UU^\dagger = U^\dagger U = \boldone $ ou equivalentemente, $U^{-1 } = U^\dagger $ .  Talvez a propriedade mais importante das matrizes unitárias é que eles preservam a norma de um vetor.  Isto acontece porque 

$$\langle v,v \rangle=v^\\dagger v = v^\dagger U^{-1 } U v = v^\dagger U^\dagger U v = \langle U v, U v \rangle .$$  

Diz-se que uma matriz $M $ é [*hermitiana*](https://en.wikipedia.org/wiki/Hermitian_matrix) se $M=M^\dagger $ .

Por último, o [*produto tensor*](https://en.wikipedia.org/wiki/Tensor_product) (ou produto Kronecker) de duas matrizes $M $ de tamanho $m n e $N de tamanho $p \times $ $ \vezes q $ é uma matriz maior $P=M \otimes N de tamanho $mp $ \times $ nq, e é obtido a partir de $M e $N $ $ seguintes:

\iniciar{alinhar}
    M\otimes N &= \start{bmatrix}
        M_{11 } ~~ \cdots ~~ M_{1n } \\ \\ \ddots\\\\
        M_{m1 } ~~ \cdots ~~ M_{mn}
    \end{bmatrix}
    \otimes \{bmatrix}
        N_{11 } ~~ \cdots ~~ N_{1q } \\ \\ \ddots\\\\
        N_{p1 } ~~ \cdots ~~ N_{pq}
    \end{ bmatrix } \\ \\ &= \start{bmatrix}
        M_{11 } \start{N_ bmatrix } 11 {11 } ~~ \cdots ~~ N_{1q } \\ \\ \ddots \\\\ N_{p1 } ~~ \cdots ~~ N_{pq } \end{ bmatrix } ~~ \cdots ~~ M_{1n } \start{ bmatrix } N_ {11 } ~~ \cdots ~~ N_{1q } \\ \\ \ddots \\\\ N_{p1 } ~~ \cdots ~~ N_{pq } \end{ bmatrix } \\ \\ \ddots\\\\
        M_{m1 } \start{{N_ bmatrix } 11 } ~~ \cdots ~~ N_{1q } \\ \\ \ddots \\\\ N_{p1 } ~~ \cdots ~~ N_{pq } \end{ bmatrix } ~~ \cdots ~~ M_{mn } \start{ bmatrix } N_ {11 } ~~ \cdots ~~ N_{1q } \\ \\ \ddots \\\\ N_{p1 } ~~ \cdots ~~ N_{pq } \end{bmatrix}
    bmatrix } \end{.
\end{align}

Isto é melhor demonstrado com alguns exemplos:

$$ \begin{bmatrix}
        a \\ \\ b \end{ bmatrix } \otimes \begin{d bmatrix } e \\ \\ \\ \\ \end{ bmatrix } = \begin{bmatrix}
        a \begin{ bmatrix } c d e \\ \\ \\ \\ \end{bmatrix}
        \\\\[1.5em] b \start{d bmatrix } \\ \\ \\ \\ e\end{bmatrix}
    \end{bmatrix}
    = \start{ bmatrix } a c a d a \\ \\ e b \\ \\ b b \\ \\ \\ \\ d \\ \\ ser\end{bmatrix}
$$

e

$$ \begin{bmatrix}
        a\ b \\ \\ c\ d \end{bmatrix}
    \otimes \{bmatrix}
        e\ f \\ \\ g\ h \end{bmatrix}
     = \start{bmatrix}
    um\begin{bmatrix}
    e\ f \\\\ g\ h \end{bmatrix}
    b\begin{bmatrix}
    e\ f \\\\ g\ h \end{bmatrix}
    \\\\[1em] c\begin{bmatrix}
    e\ f \\\\ g\ h \end{bmatrix}
    d\begin{bmatrix}
    e\ f \\\\ g\ h \end{bmatrix}
    \end{bmatrix}
    = \start{bmatrix}
    ae\ af\ be\ bf \\ \\ ag\ ah\ bg\ bh \\ \\ ce\ cf\ de\ df \\ \\ cg\ ch\ d\dh \end{ bmatrix } .
$$

Uma convenção notacional útil final em torno de produtos tensores é que, para qualquer $v vetorial $ ou $M matriz , $ $v^{\otimes n } $ ou $M^{\otimes } n$ é mão curta para um $ produto de tensor repetido $n- fold repetida.  Por exemplo:

\iniciar{alinhar}
&\start{ bmatrix } 1 \\ \\ 0 bmatrix \end{\\otimes } 1 } = \start{ bmatrix } \\ \\ 1 0 \end{ bmatrix } , \qquad \begin{bmatrix} 1 \\ \\ 0 \end{ bmatrix } {\otimes 2 } = \start{ bmatrix } 1 \\ \\ 0 \\ \\ \\ \\ 0 0 \0 \fim{ bmatrix } , \qquad \begin{bmatrix} 1 \\ \\ -1 bmatrix \end{\otimes } 2 } = \start{ bmatrix } 1 \\ \\ \\ \\ -1 \\ \\ -1 1 \end{ bmatrix } , \\ \\ &\begin{ bmatrix } 0 & \\ \\ 1 & 0 \end{\\\\\\\\\\\\\\\\\\\\\\\otimes bmatrix } 1 } = \start{ bmatrix } & 0 \\ \\ 1 & 1 0 \end{ bmatrix }&&&\begin{bmatrix} &0 \\ \\ & bmatrix } } bmatrix } 10 &\\ \\ 0&1&\\ \\ 0 &1&0&0 \\\\ 1 &0&0&0 \end{bmatrix} 0 .
\end{align}
