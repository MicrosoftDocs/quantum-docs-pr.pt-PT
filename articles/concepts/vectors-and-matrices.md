---
title: Vetores e matrizes na computação quântica
description: Aprenda o básico de como trabalhar com vetores e matrizes.
author: QuantumWriter
uid: microsoft.quantum.concepts.vectors
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 076ab6242b7ae31d4936ae8505034f1f13fa4727
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904915"
---
# <a name="vectors-and-matrices"></a>Vetores e Matrizes

Alguma familiaridade com vetores e matrizes é essencial para entender a computação quântica. Fornecemos uma breve introdução abaixo e os leitores interessados são recomendados a ler uma referência padrão sobre álgebra linear como *Strang, G. (1993). Introdução à álgebra linear (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* ou uma referência online como [Álgebra Linear](http://joshua.smcvt.edu/linearalgebra/).

Um vetor de coluna (ou simplesmente [*vetor)* ](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))$v$ de dimensão (ou tamanho) $n$ é uma coleção de números complexos de $n$ $(v_1,v_2,\ldots,v_n)$ disposta como coluna:

$$v =\start{bmatrix} v_1\\\\ v_2\\\\ \vdots\\\\ v_n \end{bmatrix}$$

A norma de um vetor $v$ é definida como $\sqrt{\sum\_i v\_i/^2}$. Um vetor é dito ser de norma unitária (ou, em alternativa, é chamado de [*vetor unitário*](https://en.wikipedia.org/wiki/Unit_vector)) se a sua norma é $1$1$. O [*adjoint de um vetor*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v$ é denotado $v^\dagger$ e é definido como o vetor de linha seguinte onde $\*$ denota o conjugado complexo,

$$\start{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix}\!adagger = \start{bmatrix}v_1^* & \cdots & v_n^* \end{bmatrix}$$

A forma mais comum de multiplicar dois vetores em conjunto é através do [*produto interno,* ](https://en.wikipedia.org/wiki/Inner_product_space)também conhecido como um produto de pontos.  O produto interno dá a projeção de um vetor para outro e é inestimável na descrição de como expressar um vetor como uma soma de outros vetores mais simples.  O produto interno entre $u$ e $v$, denotado $\left\langle u, v\right\rangle$ é definido como

$$ \langle u, v\rangle = u^\dagger v=u\_1^{\*} v_1 + \cdots + u\_n^{\*} v\_n.
$$

Esta notação também permite que a norma de um vetor $v$ seja escrita como $\sqrt{\langle v, v\rangle}$.

Podemos multiplicar um vetor com um número $c$ para formar um novo vetor cujas entradas são multiplicadas por $c$. Também podemos adicionar dois vetores $u$ e $v$ para formar um novo vetor cujas entradas são a soma das entradas de $u$ e $v$. Estas operações são retratadas abaixo:

$$\mathrm{If}~u =\begin{bmatrix} u_1\\u_2 \\ \\ \\ \vdots\\\\ u_n \end {bmatrix}~\mathrm{and}~ v =\begin{bmatrix} v_1\\\\ v_2 \\\\ vdots\\\\ v_n \end{bmatrix},~\mathrm{then}~ au+bv =\start{bmatrix} au_1+bv_1\\\\ au_2+bv_2\\\\  \vdots\\\\ au_n+bv_n \end{bmatrix}.
$$

Uma [*matriz*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) de tamanho $m \vezes n$ é uma coleção de números complexos de $mn$ dispostos em $m linhas de$ e colunas $n$ como mostrado abaixo:

$$M = \start{bmatrix} M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\ M_{21} ~~ M_{22} ~~ M_ ~~ \cdots ~~ M_{2n}\\\\ \ddots\\\\ M_{m1} ~~ M_ {m2} ~\\\\M_~ ~~

Note que um vetor de dimensão $n$ é simplesmente uma matriz de tamanho $n \vezes 1$. Tal como acontece com os vetores, podemos multiplicar uma matriz com um número $c$ para obter uma nova matriz onde cada entrada é multiplicada com $c$, e podemos adicionar duas matrizes do mesmo tamanho para produzir uma nova matriz cujas entradas são a soma das respetivas entradas das duas matrizes. 

## <a name="matrix-multiplication-and-tensor-products"></a>Multiplicação matriz e produtos tensores

Também podemos multiplicar duas matrizes $M$ de dimensão $m\vezes n$ e $N$ de dimensão $n \vezes p$ para obter uma nova matriz $P$ de dimensão $m \vezes p$ da seguinte forma:

\begin{align} &\begin{bmatrix} M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\ M_{21} ~~ M_{22} ~~ ~~ ~~ M_ {2n}\\\\  \ddots\\\\ M_{m1} ~~ M_{m2} ~~ ~M_~ começar{bmatrix} N_{11} ~~ N_{12} ~~ \cdots ~~ N_{1p}\\\\ N_{21} ~~ N_{22} ~~ \cdots ~N_~ {2p} \\\\\ddots\\\\ N_{n1} ~~ N_{n2~ ~~ \cdots ~~ N_ {np} \end{bmatrix}=\start{bmatrix P_}{11} ~~ P_{12} ~~ \cdots ~~ P_{1p}\\\\ P_{21} ~~ P_{22} ~~ \cdots ~~ P_{2p}\\\\  \ddots\\\\ P_{m1} ~~ P_{m2} ~~ \cdots ~~ P_{mp} \end{bmatrix} \end{{align}

onde as entradas de $P$ são $P_{ik} = \sum_j M_{ij}N_{jk}$. Por exemplo, a entrada $P_{11}$ é o produto interno da primeira linha de $M$ com a primeira coluna de $N$. Note que uma vez que um vetor é simplesmente um caso especial de uma matriz, esta definição estende-se à multiplicação do vetor matriz. 

Todas as matrizes que consideramos serão matrizes quadradas, onde o número de linhas e colunas são iguais, ou vetores, o que corresponde a apenas $1$ coluna. Uma matriz quadrada especial é a [*matriz de identidade,* ](https://en.wikipedia.org/wiki/Identity_matrix)denotada $\boldone$, que tem todos os seus elementos diagonais iguais a $1$ e os restantes elementos iguais a $0$:

$$\boldone=\begin{bmatrix} 1 ~~ ~~ ~~ ~~ \cdots ~~ 0\\\\ 0 ~~ 1 ~~ ~~ 0\\\\ ~~ \ddots\\\\ 0 ~~ 0 ~~ ~~ ~~ \cdots ~~ 1 \end{bmatrix}.$$

Para uma matriz quadrada $A$, dizemos que uma matriz $B$ é o seu [*inverso*](https://en.wikipedia.org/wiki/Invertible_matrix) se $AB = BA = \boldone$. O inverso de uma matriz não precisa de existir, mas quando existe é único e denotamos $A^{-1}$. 

Para qualquer matriz $M$, a transposição adjoint ou conjugada de $M$ é uma matriz $N$ tal que $N_{ij} = M_{ji}^\*$. O anúncio de $M$ é geralmente denotado $M^\apunhalar$. Dizemos que uma matriz $U$ é [*unitária*](https://en.wikipedia.org/wiki/Unitary_matrix) se $UU^\dagger = U^\dagger U = \boldone$ ou equivalente, $U^{-1} = U^\dagger$.  Talvez a propriedade mais importante das matrizes unitárias seja que eles preservam a norma de um vetor.  Isto acontece porque 

$$\langle v,v \rangle=v^\dagger v = v^\dagger U^{-1} U v = v^\dagger U^\dagger U v = \langle U v, U v\rangle.$$  

Uma matriz $M$ é dito ser [*hermitiano*](https://en.wikipedia.org/wiki/Hermitian_matrix) se $M=M^\dagger$.

Finalmente, o [*produto tensor*](https://en.wikipedia.org/wiki/Tensor_product) (ou produto Kronecker) de duas matrizes $M$ de tamanho $m\vezes n$ e $N$ de tamanho $p \vezes q$ é uma matriz maior $P=M\otimes N$ de tamanho $mp \vezes nq$, e é obtido a partir de $M$ e $N$ da seguinte forma:

\begin{align} M \otimes N &= \begin{bmatrix} M_{11} ~~ \cdots ~~ M_{1n} \\\\ \ddots\\\\ M_{m1} ~~ \cdots ~~ M_{mn} \end{bmatrix} \otimes \start {bmatrix}{11} N_ ~\\\\N_~ ts\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}\\\\ & amp; start{bmatrix} M_{11} \start{bmatrix} N_{11} ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ {cdots ~~ N_ {{ {{ {{ ~~ \cdots ~~ M_{1n} \begin{bmatrix} N_{11} ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix} \\\\\ddots\\M_ \\{m1 N_{11} N_} qq}\\\\ \ddots\\\\ N_ {p1} ~~ \cdots ~~ N_{pq} \end{bmatrix~~~ \cdots ~~ M_{mn} \start{bmatrix} N_{11} ~~ ~~ {~ N_ {1q} \\\\\\\\ N_ {p1} ~N_~ bmatrix} \fim{bmatrix}.
\fim{align}

Isto é melhor demonstrado com alguns exemplos:

$$ \start{bmatrix} a \\\\ b \end{bmatrix} \otimes \start{bmatrix} c \\\\ d \\\\ e \end{bmatrix} = \start{bmatrix} a \start{bmatrix} c \\\\ d \\\\ e \end{bmatrix} \\\\[1,5em] b \start{bmatrix} c \\\\ d \\\\ e\end{bmatrix} \end{bmatrix} = \begin{bmatrix} c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ ser\end{bmatrix} $$

e

$$ \start{bmatrix} a\ b \\\\ c\ d \end{bmatrix} \otimes \start{bmatrix} e\ f\\\\g\ h \end{bmatrix} = \start{bmatrix} a\start{bmatrix} e\ f\\\\ g\ h \end{bmatrix} b\start{bmatrix} e} f\\\\ g\ h \end{bmatrix} \\\\[1em] c\start{bmatrix} e\ f\\\\ g\ h \end{bmatrix} d\start{bmatrix} e\ f\\\\ g\ h \end{bmatrix} \end{bmatrix} = \start{bmatrix} ae\ af\ be\ \\@no__ t_15_ ag\ ah\ bg\ bh \\\\ ce\ cf\ de\ df \\\\ cg\ ch\ dg\ dh \end{bmatrix}.\\
$$

Uma convenção notacional útil final em torno dos produtos tensores é que, para qualquer vetor $v$ ou matriz $M$, $v^{\otimes n}$ ou $M^{\otimes n}$ é uma mão curta para um produto de tensor repetido de $n$-fold.  Por exemplo:

\begin{align} &\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}{\otimes 1} = \start{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\start{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 2} = \start{bmatrix} 1 \\\\ 0 \\0 \\0 \\\\0 \end{bmatrix}, \qquad\start{bmatrix} 1 \\\\ -1 \end{bmatrix}{{{otimes 2} = \start {bmatrix} 1 \\\\ -1 \\\\-\\1 \\1 bmatrix}, \\\\ &\begin{bmatrix} 0 & 1 \\\\ 1& 0 \end{bmatrix}{{{\otimes 1}= \begin{bmatrix} 0& 1 \\\\ 1& 0 \end{bmatrix}, \qquad\begin{bmatrix} 0 & 1 \\\\ 1& 0 \end{bmatrix}^{\otimes 2}= \start{bmatrix} 0 &amp;0&1 \\\\ 0 &amp;1&0 \\\\ 0 &1&0&0\\\\ 1 &0&0&0&0&0 bmatrix}.
\fim{align}
