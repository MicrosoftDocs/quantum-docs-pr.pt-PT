---
título: Descrição de conceitos de matriz avançada: Saiba mais sobre eigenvectors, eigenvalues e exponencials da matriz, as ferramentas fundamentais usadas para descrever e simular algoritmos quânticos.
autor: QuantumWriter uid: microsoft.quantum.concepts.matrix-advanced ms.author: v-benbra ms.date: 12/11/2017 ms.topic: article no-loc:
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "$$$"
- "$$$"
- "$$$"
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
# <a name="advanced-matrix-concepts"></a>Conceitos de matriz avançada #

Estendemos agora a nossa manipulação de Matrizes a [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) e [*Exponencials*](https://en.wikipedia.org/wiki/Matrix_exponential) que formam um conjunto fundamental de ferramentas que precisamos para descrever e implementar algoritmos quânticos.

## <a name="eigenvalues-and-eigenvectors"></a>Eigenvalues e Eigenvectors ##

Deixe $ M ser uma matriz quadrada e v ser um $ $ $ vetor que não é o vetor de todos os zeros (ou seja, o vetor com todas as entradas iguais a $ 0 $ ).

Dizemos que $ v $ é um [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) de  $ M se $ $ Mv cv para algum número = $ c $ $ . Dizemos que $ c $ é o [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) correspondente ao eigenvector $ v $ . Em geral, uma matriz $ M pode transformar um $ vetor em qualquer outro vetor, mas um eigenvector é especial porque é deixado inalterado exceto por ser multiplicado por um número. Note que se $ v $ é um eigenvector com eigenvalue $ $ c, então $ av é também um $ eigenvector (para qualquer não zero a $ ) com o mesmo $ eigenvalue.

Por exemplo, para a matriz de identidade, cada vetor $ v $ é um eigenvector com eigenvalue $ 1 $ .

Como outro exemplo, considere uma [*matriz diagonal*](https://en.wikipedia.org/wiki/Diagonal_matrix) $ D que só tem entradas $ nãozero na diagonal:

$$
\begin{bmatrix}
d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ & 0 0 & d_3 \end{bmatrix} .
$$

Os vetores

$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix} , \begin{bmatrix} 0 \\\\ 1 \\\\ 0 e \end{bmatrix} \begin{bmatrix} 0 \\\\ 0 \\\\ 1\end{bmatrix}$$

são os eigenvectors desta matriz com d_1 de eigenvalues,  $ $ d_2 e $ $ $ $ d_3, respectivamente. Se $ d_1 , d_2 , e d_3 são $ $ $ $ $ números distintos, então estes vetores (e seus múltiplos) são os únicos eigenvectors da matriz $ D $ . Em geral, para uma matriz diagonal é fácil ler os eigenvalues e os eigenvectors. Os eigenvalues são todos os números que aparecem na diagonal, e os respetivos eigenvectors são os vetores unitários com uma entrada igual a $ 1 $ e as restantes entradas iguais a $ 0 $ .

Note no exemplo acima que os eigenvectors de $ D $ formam uma base para $ $ vetores 3-dimensional. Uma base é um conjunto de vetores de modo que qualquer vetor pode ser escrito como uma combinação linear deles. Mais explicitamente, $ $ v_1, $ $ v_2, e $ v_3 $ formam uma base se qualquer vetor $ v pode ser escrito como v a_1 v_1 + a_2 v_2 + a_3 v_3 para $ $ = $ alguns números $ a_1 , a_2 , e $ $ $ $ $ a_3.

Recorde-se que uma matriz hermitiana (também chamada de auto-adjacente) é uma matriz quadrada complexa igual à sua própria transposição conjugada complexa, enquanto uma matriz unitária é uma matriz quadrada complexa cujo inverso é igual ao seu transposto conjugado adjacente ou complexo.
Para as matrizes hermitianas e unitárias, que são essencialmente as únicas matrizes encontradas na computação quântica, existe um resultado geral conhecido como [*teorema espectral,*](https://en.wikipedia.org/wiki/Spectral_theorem)que afirma o seguinte: Para qualquer matriz eremita ou unitária $ $ M, existe um U unitário $ tal que M $ $ = U^ D U para alguma \dagger matriz $ diagonal $ D $ . Além disso, as entradas diagonais de $ D $ serão os valores de eigenvalues de $ M $ .

Já sabemos calcular os eigenvalues e os eigenvectors de uma matriz diagonal $ D $ . Usando este teorema sabemos que se $ v $ é um eigenvector de $ D com $ eigenvalue $ c , isto $ é, Dv cv , $ = $ então $ U^ v será um \dagger $ eigenvector de $ M com $ eigenvalue $ c $ . Isto é porque

$$M(U^ \dagger v) = U^ \dagger D U (U^ \dagger v) = U^ D \dagger (U U^ \dagger ) v = U^ D v c \dagger = U^ \dagger v.$$

## <a name="matrix-exponentials"></a>Exponencial da Matriz
Uma [*matriz exponencial*](https://en.wikipedia.org/wiki/Matrix_exponential) também pode ser definida em analogia exata à função exponencial.  A matriz exponencial de uma matriz $ A pode ser expressa $ como

$$
e^A = \boldone + A + \frac { A^2 } { 2! } + \frac { A^3 } { 3!}+\cdots
$$

Isto é importante porque a evolução do tempo mecânico quântico é descrita por uma matriz unitária da forma $ e^ { iB } $ para a matriz hermitiana $ B $ .  Por esta razão, a realização de exponencials da matriz é uma parte fundamental da computação quântica e, como tal, Q# oferece rotinas intrínsecas para descrever estas operações.
Existem muitas maneiras na prática de calcular uma matriz exponencial em um computador clássico, e em geral numericamente aproximando tal exponencial está cheio de perigo.  Ver [*Cleve Moler e Charles Van Loan. "Dezanove formas duvidosas de calcular o exponencial de uma matriz." Revisão do SIAM 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) para mais informações sobre os desafios envolvidos.

A maneira mais fácil de entender como calcular o exponencial de uma matriz é através dos eigenvalues e eigenvectors dessa matriz.  Especificamente, o teorema espectral discutido acima diz que para cada matriz hermitiana ou unitária $ A existe uma matriz $ unitária U e uma matriz $ $ diagonal $ D tal que A $ $ = U^ D U \dagger $ .  Devido às propriedades da unitaridade temos que $ A^2 = U^ \dagger D^2 U $ e similarmente para qualquer potência $ p $ $ A^p = U^ \dagger D^p U $ .  Se substituirmos isto na definição do operador exponencial, obtemos:

$$
e^A = U^ \dagger \left \boldone (+D + \frac { D^2 } { 2! } + \cdots \right ) U = U^ \dagger \begin{bmatrix} \exp(D_ { 11 } ) & 0 & \cdots & 0 \\\\ 0 & \exp(D_ { 22 } ) & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0 & 0 & \cdots & \exp(D_ { NN } ) \end{bmatrix} U.$$

Por outras palavras, se se transformar na eigenbasis da matriz $ $ A, então a computação da matriz exponencial equivale a computação do exponencial comum dos valores eigenvalues da matriz.  Como muitas operações na computação quântica envolvem a realização de exponencials da matriz, este truque de transformar-se na eigenbasis de uma matriz para simplificar a execução exponencial do operador aparece frequentemente e é a base por trás de muitos algoritmos quânticos, como métodos de simulação quântica ao estilo Trotter-Suzuki discutidos mais tarde neste guia.

Outra propriedade útil é se $ B $ é simultaneamente unitário e hermitiano, ou seja, $ B = B^ { -1 } = B^ \dagger $ e $ B^2 = \boldone $ . Aplicando esta regra à expansão acima da matriz exponencial e agrupondo os $ \boldone $ termos e os termos $ B em $ conjunto, pode ver-se que por qualquer valor real $ x a $ identidade

$$e^ { iBx } = \boldone \cos (x)+ iB\sin(x)$$


mantém. Este truque é especialmente útil porque permite raciocinar sobre as ações que os exponenciales da matriz têm, mesmo que a dimensão de $ B $ seja exponencialmente grande, para o caso especial quando $ B é $ simultaneamente unitário e eremita.
