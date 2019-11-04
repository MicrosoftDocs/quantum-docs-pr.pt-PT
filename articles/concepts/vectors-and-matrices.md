---
title: Vetores e matrizes | Microsoft Docs
description: Vetores e matrizes
author: QuantumWriter
uid: microsoft.quantum.concepts.vectors
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 58c96f9cda22b712e1a408e5566e0a8ee987bd6e
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183748"
---
# <a name="vectors-and-matrices"></a>Vetores e matrizes

Alguma familiaridade com vetores e matrizes é essencial para entender a computação Quantum. Fornecemos uma breve introdução abaixo e os leitores interessados são recomendados para ler uma referência padrão em Algebra linear, como *Strang, G. (1993). Introdução à algebra linear (Vol. 3). Wellesley, MA: Wellesley-Cambridge, Press* ou uma referência online, como [Algebra linear](http://joshua.smcvt.edu/linearalgebra/).

Um vetor de coluna (ou simplesmente [*vetor*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v $ de Dimension (ou size) $n $ é uma coleção de números $n $ Complex $ (v_1, v_2, \ldots, v_n) $ organizados como uma coluna:

$ $v = \begin{bmatrix} v_1\\\\ v_2\\\\ \vdots\\\\ v_n \end{bmatrix} $ $

A norma de um vetor $v $ é definida como $ \sqrt{\sum\_i | v\_i | ^ 2} $. Um vetor é considerado como sendo a norma da unidade (ou, como alternativa, é chamado de [*vetor de unidade*](https://en.wikipedia.org/wiki/Unit_vector)) se sua norma for $1 $. O [*adjoin de um vetor*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v $ é indicado $v ^ \dagger $ e é definido para ser o seguinte vetor de linha, em que $\*$ denota o conjugado complexo,

$ $ \begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix} ^ \dagger = \begin{bmatrix}v_1 ^ * & \cdots & v_n ^ * \end{bmatrix} $ $

A maneira mais comum de multiplicar dois vetores juntos é por meio do [*produto interno*](https://en.wikipedia.org/wiki/Inner_product_space), também conhecido como produto de ponto.  O produto interno fornece a projeção de um vetor para outro e é inestimável na descrição de como expressar um vetor como uma soma de outros vetores mais simples.  O produto interno entre $u $ e $v $, denotado $ \left\langle u, v\right\rangle $ é definido como

$ $ \langle u, v\rangle = u ^ \dagger v = u\_1 ^ {\*} v_1 + \cdots + u\_n ^ {\*} v\_n.
$$

Essa notação também permite que a norma de um vetor $v $ seja escrita como $ \sqrt{\langle v, v\rangle} $.

Podemos multiplicar um vetor por um número $c $ para formar um novo vetor cujas entradas são multiplicadas por $c $. Também podemos adicionar dois vetores $u $ e $v $ para formar um novo vetor cujas entradas são a soma das entradas de $u $ e $v $. Essas operações são descritas abaixo:

$ $ \mathrm{If} ~ u = \begin{bmatrix} u_1\\\\ u_2\\\\ \vdots\\\\ u_n \end{bmatrix} ~ \mathrm{and} ~ v = \begin{bmatrix} v_1\\\\ v_2\\\\ \vdots @no__ t_10_ \\ v_n \end{bmatrix}, ~ \mathrm{then} ~ au + BV = \begin{bmatrix} au_1 + bv_1\\\\ au_2 + bv_2\\\\ \vdots\\\\ au_n + bv_n \end{bmatrix}.
$$

Uma [*matriz*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) de tamanho $m \times n $ é uma coleção de números $MN $ complexs, organizadas em $m $ rows e $n $ Columns, conforme mostrado abaixo:

$ $M = \begin{bmatrix} M_{11} ~ ~ M_{12} ~ ~ \cdots ~ ~ M_ {1N}\\\\ M_{21} ~ ~ M_{22} ~ ~ \cdots ~ ~ M_ {2n}\\\\ \ddots\\\\ M_ {M1} ~ ~ M_ {m2} ~ ~ \cdots ~ ~ M_ {MN}\\@no__ t_11_ \end{bmatrix}. $ $

Observe que um vetor de dimensão $n $ é simplesmente uma matriz de tamanho $n \times $1. Assim como acontece com os vetores, podemos multiplicar uma matriz por um número $c $ para obter uma nova matriz onde cada entrada é multiplicada com $c $, e podemos adicionar duas matrizes do mesmo tamanho para produzir uma nova matriz cujas entradas são a soma das respectivas entradas das duas matrizes. 

## <a name="matrix-multiplication-and-tensor-products"></a>Multiplicação de matriz e produtos tensor

Também podemos multiplicar duas matrizes $M $ da dimensão $m \times n $ e $N $ of Dimension $n \times p $ para obter uma nova matriz $P $ of Dimension $m \times p $ da seguinte maneira:

\begin{align} & \begin{bmatrix} M_{11} ~ ~ M_{12} ~ ~ \cdots ~ ~ M_ {1N}\\\\ M_{21} ~ ~ M_{22} ~ ~ \cdots ~ ~ M_ {2n}\\\\ \ddots\\\\ M_ {M1} ~ ~ M_ {m2} ~ ~ \cdots ~ ~ M_ {MN} \end{bmatrix} \ Begin {bmatrix} N_{11} ~ ~ N_{12} ~ ~ \cdots ~ ~ N_ {1p}\\\\ N_{21} ~ ~ N_{22} ~ ~ \cdots ~ ~ N_ {2P}\\\\ \ddots\\\\ N_ {N1} ~ ~ N_ {N2} ~ ~ \cdots ~ ~ N_ {NP} \end{bmatrix} = \begin{bmatrix} P_{11} ~ ~ P_{12} ~ ~ \cdots ~ ~ P_ {1p}\\\\ P_{21} ~ ~ P_{22} ~ ~ \cdots ~ ~ P_ {2P}\\\\ \ddots\\\\ P_ {M1} ~ ~ P_ {m2} ~ ~ \cdots ~ ~ P_ {MP} \end{bmatrix} \end{align}

onde as entradas de $P $ são $P _ {IK} = \sum_j M_ {IJ} N_ {JK} $. Por exemplo, a entrada $P _{11}$ é o produto interno da primeira linha de $M $ com a primeira coluna de $N $. Observe que, como um vetor é simplesmente um caso especial de uma matriz, essa definição se estende à multiplicação do vetor de matriz. 

Todas as matrizes que consideramos serão matrizes quadradas, em que o número de linhas e colunas são iguais, ou vetores, que corresponde a apenas $1 $ coluna. Uma matriz quadrada especial é a [*matriz de identidade*](https://en.wikipedia.org/wiki/Identity_matrix), denotada $ \boldone $, que tem todos os elementos diagonais iguais a $1 $ e os elementos restantes iguais a $0 $:

$ $ \boldone = \begin{bmatrix} 1 ~ ~ 0 ~ ~ \cdots ~ ~ 0\\\\ 0 ~ ~ 1 ~ ~ \cdots ~ ~ 0\\\\ ~ ~ \ddots\\\\ 0 ~ ~ 0 ~ ~ \cdots ~ ~ 1 \end{bmatrix}. $ $

Para uma matriz quadrada $A $, dizemos uma matriz $B $ é seu [*inverso*](https://en.wikipedia.org/wiki/Invertible_matrix) se $AB = BA = \boldone $. O inverso de uma matriz não precisa existir, mas quando ela existe, ela é exclusiva e a denotamos $A ^{-1}$. 

Para qualquer matriz $M $, a transpoção adjacente ou conjugada de $M $ é uma matriz $N $, que $N _ {IJ} = M_ {ji} ^\*$. O adjoin of $M $ geralmente é indicado $M ^ \dagger $. Dizemos uma matriz $U $ é [*unitário*](https://en.wikipedia.org/wiki/Unitary_matrix) se $uu ^ \Dagger = u ^ \dagger u = \boldone $ ou equivalente, $U ^{-1} = u ^ \dagger $.  Talvez a propriedade mais importante das matrizes de unitários seja que elas preservam a norma de um vetor.  Isso acontece porque 

$ $ \langle v, v \rangle = v ^ \dagger v = v ^ \dagger U ^{-1} U v = v ^ \dagger U ^ \dagger U v = \langle U v, U v\rangle. $ $  

Uma matriz $M $ é considerada [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) se $M = M ^ \dagger $.

Por fim, o [*produto tensor*](https://en.wikipedia.org/wiki/Tensor_product) (ou o produto Kronecker) de duas matrizes $M $ de tamanho $m \times n $ e $N $ de tamanho $p \times q $ é uma matriz maior $P = M\otimes n $ de tamanho $MP \times NQ $ e é obtida de $M $ e $N $ da seguinte maneira:

\begin{align} M \otimes N & = \begin{bmatrix} M_{11} ~ ~ \cdots ~ ~ M_ {1N} \\\\ \ddots\\\\ M_ {M1} ~ ~ \cdots ~ ~ M_ {MN} \end{bmatrix} \otimes \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1Q}\\\\ \ddots @no__ t_8_ \\ N_ {P1} ~ ~ \cdots ~ ~ N_ {pq} \end{bmatrix}\\\\ & = \begin{bmatrix} M_{11} \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1Q}\\\\ \ddots\\\\ N_ {P1} ~ ~ \cdots ~ ~ N_ {pq} \end{bmatrix} ~ ~ \cdots ~ ~ M_ {1N} \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1Q}\\\\ \ddots\\\\ N_ {P1} ~ ~ \cdots ~ ~ N_ {pq} \end{bmatrix}\\\\ \ddots\\\\ M_ {M1} \begin{bmatrix} N_{11} ~ ~ \ cdots ~ ~ N_ {1Q}\\\\ \ddots\\\\ N_ {P1} ~ ~ \cdots ~ ~ N_ {pq} \end{bmatrix} ~ ~ \cdots ~ ~ M_ {MN} \begin{bmatrix} N_{11} ~ ~ \cdots ~ ~ N_ {1Q}\\\\ \ddots\\\\ N_ {P1} ~ ~ \cdots ~ ~ N_ {pq} \end {bmatrix} \end{bmatrix}.
\end{align}

Isso é melhor demonstrado com alguns exemplos:

$ $ \begin{bmatrix} a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} = \begin{bmatrix} a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} @no__ t_10_ \\[1,5 em] b \begin{bmatrix} c \\\\ d \\\\ e\end {bmatrix} \end{bmatrix} = \begin{bmatrix} a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end {bmatrix} $ $

e em

$ $ \begin{bmatrix} a \ b \\\\ c \ d \end{bmatrix} \otimes \begin{bmatrix} e \ f\\\\g \ h \end{bmatrix} = \begin{bmatrix} a\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} b\begin {bmatrix} e \ f\\@no__ t_7_ g \ h \end{bmatrix} \\\\[1em] c\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} d\begin {bmatrix} e \ f\\\\ g \ h \end{bmatrix} \end{bmatrix} = \begin{bmatrix} AE \ AF \ is \ BF \\@no__ t_15_ AG \ Ah \ BG \ BH \\\\ CE \ CF \ de \ DF \\\\ CG \ ch \ DG \ DH \end{bmatrix}.
$$

Uma Convenção de notação útil final em relação aos produtos tensor é que, para qualquer vetor $v $ ou Matrix $M $, $v ^ {\otimes n} $ ou $M ^ {\otimes n} $ é curto para um produto de tensor repetido de $n $-fold.  Por exemplo:

\begin{align} & \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ {\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\-1 \end{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 1 \\\\-1 \\\\-1 \\\\1 \end{bmatrix}, \\\\ & \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ {\otimes 1} = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix}, \qquad\begin{bmatrix} 0 & 1 \\@no__ t_27_ 1 & 0 \end{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0\\\\ 1 & 0 & 0 & 0 \ fim {bmatrix}.
\end{align}

