---
título: Vetores e matrizes na descrição da computação quântica: Aprenda os fundamentos de como trabalhar com vetores e matrizes.
autor: QuantumWriter uid: microsoft.quantum.concepts.vectors ms.author: nawiebe@microsoft.com ms.date: 12/11/2017 ms.topic: article no-loc:
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "\cdots"
- "bmatrix"
- "\ddots"
- "\equiv"
- "\sum"
- "\begin"
- "\end"
- "\sqrt"
- "\otimes"
- "{"
- "}"
- "\text"
- "\phi"
- "\kappa"
- "\psi"
- "\alpha"
- "\beta"
- "\gamma"
- "\delta"
- "\omega"
- "\bra"
- "\ket"
- "\boldone"
- "\\\\"
- "\\"
- "="
- "\frac"
- "\text"
- "\mapsto"
- "\dagger"
- "\to"
- "\begin{cases}"
- "\end{cases}"
- "\operatorname"
- "\braket"
- "\id"
- "\expect"
- "\defeq"
- "\variance"
- "\dd"
- "&"
- "\begin{align}"
- "\end{align}"
- "\Lambda"
- "\lambda"
- "\Omega"
- "\mathrm"
- "\left"
- "\right"
- "\qquad"
- "\times"
- "\big"
- "\langle"
- "\rangle"
- "\bigg"
- "\Big"
- "|"
- "\mathbb"
- "\vec"
- "\in"
- "\texttt"
- "\ne"
- "<"
- ">"
- "\leq"
- "\geq"
- "~~"
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- "\_"

---

# <a name="vectors-and-matrices"></a>Vetores e Matrizes

Alguma familiaridade com vetores e matrizes é essencial para entender a computação quântica. Fornecemos uma breve introdução abaixo e os leitores interessados são recomendados a ler uma referência padrão em álgebra linear como *Strang, G. (1993). Introdução à álgebra linear (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* ou uma referência online como [álgebra linear.](http://joshua.smcvt.edu/linearalgebra/)

Um vetor de coluna (ou simplesmente [*vetor)*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics)) $ v de $ dimensão (ou tamanho) $ n é uma coleção de $ $ $ números n complexos $ (v_1,v_2,\ldots,v_n) $ dispostos como uma coluna:

$$v=\begin{bmatrix}
v_1\\\\
v_2\\\\
\vdots\\\\
v_n\end{bmatrix}$$

A norma de um vetor $ v é definida como i v $ i $ \sqrt { \sum \_ | \_ | ^2 } $ . Diz-se que um vetor é de norma unitária (ou, em alternativa, é chamado de [*vetor unitário)*](https://en.wikipedia.org/wiki/Unit_vector)se a sua norma for $ 1 $ . O [*adjacente de um vetor*](https://en.wikipedia.org/wiki/Adjoint_matrix) v é $ $ denotado $ v^ e é definido como o \dagger $ vetor de linha seguinte onde $ \* $ denota o conjugado complexo,

$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix} ^ \dagger = \begin{bmatrix} v_1^* & \cdots & v_n^*\end{bmatrix}$$

A forma mais comum de multiplicar dois vetores juntos é através do [*produto interno,*](https://en.wikipedia.org/wiki/Inner_product_space)também conhecido como um produto ponto.  O produto interno dá a projeção de um vetor para outro e é inestimável na descrição de como expressar um vetor como uma soma de outros vetores mais simples.  O produto interno entre $ u e v , $ $ $ denotado $ \left \langle u, v \right \rangle $ é definido como

$$
\langleu, v \rangle = u^ \dagger v = \_ 1^ { \* } v_1 + + \cdots u \_ n^ v { \* } \_ n.
$$

Esta notação também permite que a norma de um vetor $ v seja escrita como $ $ \sqrt { \langle v, v \rangle } $ .

Podemos multiplicar um vetor com um número $ c para formar um novo $ vetor cujas entradas são multiplicadas por $ c $ . Também podemos adicionar dois vetores $ u e v para formar um novo $ $ $ vetor cujas entradas são a soma das entradas de $ u e v $ $ $ . Estas operações são retratadas abaixo:

$$\mathrm{If } ~ u=\begin{bmatrix}
u_1\\\\
u_2\\\\
\vdots\\\\
u_n \end{bmatrix} ~ \mathrm { e}~
v=\begin{bmatrix}
    v_1\\\\
    v_2\\\\
    \vdots\\\\
    v_n, \end{bmatrix} ~ \mathrm { então}~
au+bv=\begin{bmatrix}
au_1+bv_1\\\\
au_2+bv_2\\\\
\vdots\\\\
\end{bmatrix}au_n+bv_n.
$$

Uma [*matriz*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) de tamanho $ m n é uma coleção de \times $ $ números complexos mn $ dispostos em $ linhas m $ e n $ $ colunas como mostrado abaixo:

$$M= 
\begin{bmatrix}
M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1n}\\\\
M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2n}\\\\
\ddots\\\\
M_ { m1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { mn}\\\\
\end{bmatrix}.$$

Note que um vetor de dimensão $ n é simplesmente uma matriz de tamanho n $ $ \times 1 $ . Tal como acontece com os vetores, podemos multiplicar uma matriz com um número $ c para obter uma nova matriz onde cada entrada é $ multiplicada com $ $ c, e podemos adicionar duas matrizes do mesmo tamanho para produzir uma nova matriz cujas entradas são a soma das respetivas entradas das duas matrizes. 

## <a name="matrix-multiplication-and-tensor-products"></a>Multiplicação de matriz e produtos de tensor

Também podemos multiplicar duas matrizes $ M $ de dimensão m n e $ N de \times $ $ $ dimensão n p para $ obter uma nova matriz P de \times $ $ $ dimensão m p da $ seguinte \times $ forma:

\begin{align}
&\begin{bmatrix}
    M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1n}\\\\
    M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2n}\\\\
    \ddots\\\\
    M_ { m1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { mn}
\end{bmatrix}
\begin{bmatrix}
N_ { 11 } ~~ N_ { 12 N_ } ~~ \cdots ~~ { 1p}\\\\
N_ { 21 } ~~ N_ { 22 N_ } ~~ \cdots ~~ { 2p}\\\\
\ddots\\\\
N1 { } ~~ N_ n1 N_ { n2 } ~~ \cdots ~~ N_ { np}
\end{bmatrix}=\begin{bmatrix}
P_ { 11 } ~~ P_ { 12 P_ } ~~ \cdots ~~ { 1p}\\\\
P_ { 21 } ~~ P_ { 22 P_ } ~~ \cdots ~~ { 2p}\\\\
\ddots\\\\
P_ { m1 } ~~ P_ { m2 } ~~ \cdots ~~ P_ { mp}
\end{bmatrix}
\end{align}

onde as entradas de $ P $ são P_ $ { ik j } = \sum _M_ { ij N_ } { jk } $ . Por exemplo, a entrada $ P_ { 11 } $ é o produto interno da primeira linha de $ M com a primeira coluna de N $ $ $ . Note que uma vez que um vetor é simplesmente um caso especial de uma matriz, esta definição estende-se à multiplicação de vetores de matriz. 

Todas as matrizes que consideramos serão matrizes quadradas, onde o número de linhas e colunas são iguais, ou vetores, o que corresponde a apenas $ 1 $ coluna. Uma matriz quadrada especial é a [*matriz identitária,*](https://en.wikipedia.org/wiki/Identity_matrix)denotada, $ \boldone $ que tem todos os seus elementos diagonais iguais a $ 1 $ e os restantes elementos iguais a $ 0 $ :

$$\boldone=\begin{bmatrix}
~~10 ~~ \cdots ~~ 0\\\\
0 ~~ ~~ \cdots ~~ 10\\\\
~~ \ddots\\\\
0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix} .$$

Para uma matriz quadrada $ $ A, dizemos que uma matriz $ B é o seu $ [*inverso*](https://en.wikipedia.org/wiki/Invertible_matrix) se AB $ BA = = \boldone $ . O inverso de uma matriz não precisa de existir, mas quando existe é único e denotamos $ A^ { -1 } $ . 

Para qualquer matriz $ M $ , a transposição contígua ou conjugada de $ M é uma matriz N tal que N_ $ $ $ $ { ij } = M_ ji { } ^ \* $ . O adjacente de $ M $ é geralmente denotado $ M^ \dagger $ . Dizemos que uma matriz $ U $ é [*unitária*](https://en.wikipedia.org/wiki/Unitary_matrix) se $ UU^ \dagger = U^ \dagger U ou = \boldone $ equivalentemente, $ U^ { -1 } = U^ \dagger $ .  Talvez a propriedade mais importante das matrizes unitárias é que eles preservam a norma de um vetor.  Isto acontece porque 

$$\langle\rangle = v,v^ \dagger v^ = \dagger U^ { -1 } U = v^ \dagger U^ \dagger U^ U vy = \langle v, U v, U v, U v \rangle .$$  

Diz-se que uma matriz $ M $ é [*eremita*](https://en.wikipedia.org/wiki/Hermitian_matrix) se $ = M. M^ \dagger $ .

Finalmente, o [*produto tensor*](https://en.wikipedia.org/wiki/Tensor_product) (ou produto Kronecker) de duas matrizes $ M de tamanho m n e N de tamanho p $ q é uma matriz maior P $ M \times N de tamanho $ $ mp $ $ \times $ $ = \otimes $ $ \times nq , e é obtido a $ partir de M e N da seguinte $ $ $ $ forma:

\begin{align}
    M \otimes N&=
    \begin{bmatrix}
        M_ { 11 } ~~ \cdots ~~ M_ { 1n }\\\\
        \ddots\\\\
        M_ { m1 } ~~ \cdots ~~ M_ { mn  }
    \end{bmatrix}
    \otimes
    \begin{bmatrix}
        N_ { 11 } ~~ \cdots ~~ N_ { 1q  }\\\\
        \ddots\\\\
        P1 { } ~~ \cdots ~~ p1 N_ N_ { pq}
    \end{bmatrix}\\\\
    &=
    \begin{bmatrix}
        M_ { 11 } \begin{bmatrix} N_ { 11 N_ } ~~ \cdots ~~ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq } \end{bmatrix} ~~ \cdots  ~~ 
        M_ { 1n } \begin{bmatrix} N_ { 11 N_ } ~~ \cdots ~~ { 1q N_ } \\\\ \ddots \\\\ { p1 N_ } ~~ \cdots ~~ { pq }  \end{bmatrix}\\\\
        \ddots\\\\
        M_ { m1 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ { p1 } ~~ \cdots ~~ N_ p1 N_ { pq } \end{bmatrix} ~~ \cdots  ~~ 
        M_ { mn } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q N_ } \\\\ \ddots \\\\ { p1 } ~~ \cdots ~~ N_ { pq }  \end{bmatrix}
    \end{bmatrix}.
\end{align}

Isto é melhor demonstrado com alguns exemplos:

$$
    \begin{bmatrix}
        a \\\\ b c d \end{bmatrix} \otimes \begin{bmatrix} \\\\ \\\\ e \end{bmatrix}=
    \begin{bmatrix}
        a \begin{bmatrix} \\\\ c d \\\\ e\end{bmatrix}
        \\\\[1.5em] b \begin{bmatrix} \\\\ c d \\\\ e\end{bmatrix}
    \end{bmatrix}
    =\begin{bmatrix}a c \\\\ a d a e b b d \\\\ \\\\ \\\\ \\\\ ser\end{bmatrix}
$$

e

$$
    \begin{bmatrix}
        a\ b \\\\ c\ d\end{bmatrix}
    \otimes 
    \begin{bmatrix}
        e\ f \\\\ g\ h\end{bmatrix}
     =
    \begin{bmatrix}
    um\begin{bmatrix}
    e\ f \\\\ g\ h\end{bmatrix}
    b\begin{bmatrix}
    e\ f \\\\ g\ h\end{bmatrix}
    \\\\[1em] c\begin{bmatrix}
    e\ f \\\\ g\ h\end{bmatrix}
    d\begin{bmatrix}
    e\ f \\\\ g\ h\end{bmatrix}
    \end{bmatrix}
    =
    \begin{bmatrix}
    ae\ af\ ser\ bf\\\\
    ag\ ah\ bg\ bh\\\\
    ce\ cf\ de\ df\\\\
    cg\ ch\ dg\ dh \end{bmatrix} .
$$

Uma convenção notacional útil final em torno dos produtos tensores é que, para qualquer vetor $ v $ ou matriz $ $ M, $ v^ n ou { \otimes } $ $ M^ n { \otimes é mão curta para } $ um produto $ $ tensor repetido n-fold.  Por exemplo:

\begin{align}
&\begin{bmatrix}1 \\\\ 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} \\\\ 10 , \end{bmatrix} \qquad \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ 0 \\\\ \\\\ 0 0 \end{bmatrix} 0 , \qquad \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ \\\\ -1 -1 \\\\ 1 \end{bmatrix} 1 ,\\\\
  &\begin{bmatrix}0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 1 & 1 \\\\ 1 & 1 0 \end{bmatrix} , \qquad \begin{bmatrix} & \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 0 } = \begin{bmatrix} & 0 & 0 & 1 \\\\ & 0 & 1 0 0 0 & \\\\ 0 & 0 0 1 & & 0 0 \\\\ 0 1 & 0 & 0 & 0 0 \end{bmatrix} .
\end{align}
