---
título: Descrição da notação dirac: Saiba como usar a notação dirac para representar estados quânticos e simular operações quânticas.
autor: QuantumWriter uid: microsoft.quantum.concepts.dirac ms.author: nawiebe@microsoft.com ms.date: 12/11/2017 ms.topic: article no-loc:
- "Q#"
- "$$v"
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

# <a name="dirac-notation"></a>Notação dirac

Embora a notação vetorial da coluna seja ubíqua em álgebra linear, é frequentemente complicada na computação quântica, especialmente quando lida com múltiplos qubits.  Por exemplo, quando definimos $ \psi $ ser um vetor não é explicitamente claro se $ \psi $ é uma linha ou um vetor de coluna.  Assim, se $ \phi $ e $ \psi $ são vetores, então é igualmente incerto se $ \phi \psi $ é definido porque as formas $ \phi $ de e $ \psi $ pode ser pouco claro no contexto.  Além da ambiguidade sobre as formas dos vetores, expressar até vetores simples usando a notação algébrica linear introduzida anteriormente pode ser muito complicado. Por exemplo, se quisermos descrever um $ $ estado n-qubit onde cada qubit leva o valor $ $ 0, então nós expressar formalmente o estado como 

$$\begin{bmatrix}1 \\\\ 0 \end{bmatrix} \otimes \cdots \otimes \begin{bmatrix} \\\\ 10 \end{bmatrix} . $$  

É claro que avaliar este produto tensor é impraticável porque o vetor está em um espaço exponencialmente grande e, portanto, esta notação é na verdade a melhor descrição do estado que pode ser dada usando a notação anterior.  

[*A notação dirac*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) resolve estas questões apresentando uma nova linguagem que se adequa às necessidades precisas da mecânica quântica.  Por esta razão, recomendamos que o leitor não veja os exemplos nesta secção como uma prescrição rígida de como descrever estados quânticos, mas sim encorajar o leitor a envergonhá-los como sugestões que podem ser usadas para expressar concisamente ideias quânticas.

Existem dois tipos de vetores na notação dirac: o vetor *de sutiã* e o vetor *de ket,* assim chamado porque quando juntos formam um *travão* ou produto interno.  Se $ \psi $ for um vetor de coluna, então podemos escrevê-lo na notação de Dirac como $ \ket { \psi } $ , onde o $ \ket { \cdot } $ denota que é um vetor de coluna unitária, ou seja, um vetor *de ket.*  Da mesma forma, o vetor de linha $ \psi ^ \dagger $ é expresso como $ \bra { \psi } $ . Por outras palavras, $ \psi ^ \dagger $ obtém-se através da aplicação de conjugação complexa de entrada aos elementos da transposição de $ \psi $ . A notação bra-ket diretamente implica que $ \braket { \psi | \psi } $ é o produto interno do vetor $ \psi $ com si mesmo, que é por definição $ 1 $ .  

De uma forma mais geral, se $ \psi $ e $ \phi $ são vetores de estado quântico o seu produto interno $ \braket { \phi | \psi } $ é o que implica que a probabilidade de medir o estado $ \ket { \psi } $ a ser $ \ket { \phi } $ é $ | \braket { \phi | \psi } | ^2 $ .  

A convenção que se segue é utilizada para descrever os estados quânticos que codificam os valores de zero e um (os estados de base computacional de um único qubit):

$$
\begin{bmatrix}\\\\10 \end{bmatrix} = \ket { } 0,\qquad
\begin{bmatrix}0 \\\\ \end{bmatrix} = \ket { 11 } .
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a>Exemplo: representar a operação Hadamard com notação dirac

A seguinte notação é frequentemente usada para descrever os estados que resultam da aplicação do portão Hadamard para $ \ket { 0 } $ e $ \ket { 1 } $ (que correspondem aos vetores unitários nas $ direções +x $ e $ -x na esfera $ Bloch):

$$
\frac{1 } { \sqrt { 2 } } \begin{bmatrix} 1 \\\\ 1 \end{bmatrix} = H \ket { } = \ket { + } 0,\qquad
\frac{1 } { \sqrt { 2 } } \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} = H \ket { 1 } = \ket { - } .
$$

Estes Estados também podem ser expandidos usando a notação dirac como somas de $ \ket { 0 } $ e $ \ket { 1 } $ :

$$
\ket{+}= \frac{ 1 } { \sqrt { 2 } } ( \ket { 0 }  +  \ket { 1 } ), \qquad \ket { - } = \frac { 1 } { \sqrt { 2 } } ( \ket { 0 }  -  \ket { 1 } ).
$$

### <a name="computational-basis-vectors"></a>Vetores de base computacional
Isto demonstra porque é que estes Estados são muitas vezes chamados de *base computacional*: cada estado quântico pode sempre ser expresso como somas de vetores de base computacional e tais somas são facilmente expressas usando a notação dirac.  O inverso também é verdade na medida em que os Estados $ \ket { + } $ e $ \ket { - } $ também constituem uma base para os Estados quânticos.  Pode ver isto pelo facto de que

$$
\ket{} = \frac { 0 } { \sqrt { 12 } } ( \ket { + }  +  \ket { - } ), \qquad \ket { 1 } = \frac { } { \sqrt { 12 } } ( \ket { + }  -  \ket { - } ).
$$

Como exemplo de notação Dirac, considere o travão $ \braket { 0 | } $ 1, que é o produto interno entre $ 0 $ e $ 1 $ .  Pode ser escrito como 

$$\braket{0 | 1 } = \begin{bmatrix} 1 & 0 \end{bmatrix} \begin{bmatrix} 0 \\\\ \end{bmatrix} = 10.$$

Isto diz que $ \ket { 0 } $ e $ \ket { 1 } $ são vetores orthogonais, o que significa que $ \braket { 0 | 1 } = \braket { | 1 0 } = 0 $ .  Também por definição $ \braket { | 0 0 } = \braket { 1 | 1 } = $ 1, o que significa que os dois vetores de base computacional também podem ser chamados *ortormais*.
Estas propriedades oronormais serão úteis no seguinte exemplo. Se temos um estado $ \ket { \psi } = { \frac { } { 3 5 } } \ket { 1 }  +  { \frac { 4 } { 5 } } \ket { } $ 0, então porque $ \braket { 1 | 0 } = 0 $ a probabilidade de medir $ 1 $ é  

$$\big|\braket{1 | \psi } \big | ^2 = \left | \frac { 3 } { 5 } \braket { | 1 }  + \frac { 1 } { 4 5 } \braket { 1 | 0 } \right | ^2 = \frac { 9 } { 25 } .$$ 

### <a name="tensor-product-notation"></a>Notação do produto tensor
A notação dirac também inclui uma estrutura implícita do produto tensor dentro dela.  Isto é importante porque na computação quântica, o vetor de estado descrito por dois registos quânticos não correlacionados é os produtos de tensor dos dois vetores estatais.  Descrever concisamente a estrutura do produto tensor, ou falta dela, é vital se quiser explicar uma computação quântica.  A estrutura do produto tensor implica que podemos escrever $ \psi \otimes \phi $ para qualquer dois vetores de estado quântico $ \phi $ e $ \psi $ como $ \ket { \psi } \ket { \phi } $ , por vezes explicitamente escrito como $ \ket { \psi } \otimes \ket { \phi } $ , no entanto, por convenção escrita $ \otimes $ entre os vetores é desnecessário.  Por exemplo, o estado com dois qubits inicializados para o estado zero é dado por

$$
\begin{bmatrix}1 \\\\ 0 \\\\ \\\\ 0 0 \end{bmatrix} = \begin{bmatrix} 1 \\\\ \end{bmatrix} \otimes \begin{bmatrix} 0 1 \\\\ 0 \end{bmatrix} = \ket { } \otimes \ket { 0 } = \ket { 0 } \ket { 0 } 0 .
$$

Da mesma forma, o estado $ \ket { p para o } $ inteiro p representa um $ estado $ quântico que codifica na representação binária o inteiro $ p $ .  Por exemplo, se quisermos expressar o número $ 5 $ usando uma codificação binária não assinada, poderíamos igualmente expressá-lo como

$$
\ket{1 } \ket { 0 } \ket { 1 } = \ket { 101 } = \ket { 5 } .
$$

Dentro desta notação $ \ket { 0 } $ não é necessário referir-se a um estado de um único qubit, mas sim a um *registo qubit* que armazena uma codificação binária de $ 0 $ .  As diferenças entre estas duas notações são geralmente claras do contexto.  Esta convenção é útil para simplificar o primeiro exemplo que pode ser escrito de qualquer das seguintes formas:

$$
\begin{bmatrix}1 \\\\ \end{bmatrix} \otimes \cdots \otimes \begin{bmatrix} 0 1 \\\\ 0 \end{bmatrix} = \ket { } \otimes \cdots \otimes \ket { 0 } = | 0 \cdots \rangle = \ket { 0 0 } ^ { \otimes n } = \ket { 0 } .
$$

### <a name="example-describing-superposition-with-dirac-notation"></a>Exemplo: Descrever a sobreposição com notação dirac
Como outro exemplo de como pode usar a notação de Dirac para descrever um estado quântico, considere as seguintes formas equivalentes de escrever um estado quântico que é uma superposição igual sobre cada possível comprimento $ n$

$$
H^ { \otimes n } \ket { 0 } = \frac { 1 } { 2^ { n/2 } } \sum _ { j = 0 } ^ { 2^n-1 } \ket { j } = \ket { + } ^ { \otimes n } .
$$

Aqui pode perguntar-se por que razão a soma vai de $ 0 $ a $ 2^ { n } -1 $ para n $ $ bits.  Primeiro note que existem $ 2^ { n } $ configurações diferentes que $ n $ bits podem tomar.  Pode ver isso notando que uma parte pode levar $ 2 $ valores, mas dois bits podem levar $ 4 $ valores e assim por diante. Em geral, isto significa que $ existem 2^n $ diferentes cordas de bits possíveis, mas o maior valor codificado em qualquer um deles $ \cdots 1 = 1 2^n-1 $ e, portanto, é o limite superior para a soma.
Como nota lateral, neste exemplo não $ \ket { + } ^ { \otimes usamos n } = \ket { + } $ em analogia a $ \ket { 0 } ^ { \otimes n } = \ket { 0 } $ porque esta convenção notacional é geralmente reservada para o estado de base computacional com cada qubit inicializado a zero.  Embora tal convenção seja sensata neste caso, não é utilizada na literatura de computação quântica.

### <a name="expressing-linearity-with-dirac-notation"></a>Expressando linearidade com notação dirac
Outra característica agradável da notação de Dirac é o facto de ser linear.  Se quisermos escrever para qualquer quatro vetores de estado quântico, 

$$( \alpha \ket { \psi }  + \beta \ket { \phi } ( \otimes \gamma \ket { }  +  \delta \ket { \omega } \chi) = \alpha \gamma \ket { \psi } \ket { \chi }  +  \alpha \delta \ket { \psi } \ket { \omega } + \beta \gamma \ket { \phi } \ket { \chi } + \beta \delta \ket { \phi } \ket { \omega } .$$

Ou seja, você pode distribuir a notação de produto tensor na notação dirac de modo que tomar produtos de tensor entre vetores de estado acaba por parecer uma multiplicação normal.

Os vetores de sutiã seguem uma convenção semelhante aos vetores de ket.  Por exemplo, o vetor $ \bra { \psi } \bra { \phi } $ é equivalente ao vetor de estado $ \psi ^ \dagger \otimes \phi ^ \dagger = \psi \otimes \phi ()^ \dagger $ . Se o vetor ket $ \ket { \psi } $ for $ \alpha \ket { 0 }  +  \beta \ket { } $ 1, então a versão vetorial de soutien do vetor é $ \bra { \psi } = \ket { \psi } ^ \dagger = \bra { (0^* } \alpha + \bra { 1 } \beta ^**) $ .

Como exemplo, imagine que queremos calcular a probabilidade de medir o estado $ \ket { \psi } = \frac { } { 3 5 } \ket { 1 }  +  \frac { 4 } { 5 } \ket { 0 } $ usando um programa quântico para medir estados para ser $ \ket { + } $ ou $ \ket { - } $ . Então a probabilidade de que o dispositivo iria der o resultado que o estado $ \ket { - } $ é 

$$|\braket{- |\psi}| ^2 = \left | \frac { } { \sqrt { 1 2 } } ( \bra { 0 }  -  \bra { 1 } ) ( \frac { 3 } { 5 } \ket { 1 }  +  \frac { } { 4 } \ket { 5 0 ) } \right | ^2 = \left | - \frac { 3 } { \sqrt { 5 } }  +  \frac { 2 } { 4 \sqrt { 5 2 } } \right | ^2 = \frac { 1 } { 50 } .$$

O facto de o sinal negativo aparecer no cálculo da probabilidade é uma manifestação de interferência quântica, que é um dos mecanismos pelos quais a computação quântica ganha vantagens sobre a computação clássica.

## <a name="ketbra-or-outer-product"></a>ketbra ou produto externo
O item final que vale a pena discutir na notação dirac é o *ketbra* ou o produto exterior.  O produto exterior é representado nas notações de Dirac como $ \ket { \psi } \bra { \phi } $ , e às vezes chamado ketbras porque os sutiãs e kets ocorrem na ordem oposta como travões.  O produto exterior é definido através da multiplicação da matriz como $ \ket { \psi } \bra { \phi } = \psi \phi ^ \dagger $ para vetores de estado quântico $ \psi $ e $ \phi $ .  O exemplo mais simples, e indiscutivelmente mais comum desta notação, é

$$
\ket{0 } \bra { 0 } = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \begin{bmatrix} 1 & 0 \end{bmatrix} = \begin{bmatrix} 1 & 0 \\\\ & 0 \end{bmatrix} \qquad \ket { } \bra { 1 } = \begin{bmatrix} 1 \\\\ 1 0 \end{bmatrix} \begin{bmatrix} & 1 0 1 \end{bmatrix} = \begin{bmatrix} & 0 0 \\\\ 0 & 0 1 \end{bmatrix} .
$$

As Ketbras são muitas vezes chamadas de projetores porque projetam um estado quântico num valor fixo.  Uma vez que estas operações não são unitárias (e nem sequer preservam a norma de um vetor), não deve surpreender-se que um computador quântico não possa aplicar deterministicamente um projetor.  No entanto, os projetores fazem um belo trabalho de descrever a ação que a medição tem sobre um estado quântico.  Por exemplo, se medirmos um estado $ \ket { \psi } $ a $ ser $ 0, então a transformação resultante que o Estado experimenta como resultado da medição é

  $$\ket{\psi}\rightseta \frac { ( \ket { 0 } \bra { } 0) \ket { \psi } } { | \braket { 0 | \psi } | } = \ket { 0 } ,$$

como se espera que se medir o Estado e encontrá-lo ser $ \ket { 0 } $ .  Para reiterar, tais projetores não podem ser aplicados num estado num computador quântico deterministicamente.  Em vez disso, podem, na melhor das hipóteses, ser aplicados aleatoriamente com o resultado $ \ket { 0 } $ aparecendo com alguma probabilidade fixa.  A probabilidade de tal medição ser bem sucedida pode ser escrita como o valor de expectativa do projetor quântico no estado

$$
\bra{\psi}( \ket { 0 } \bra { 0 } ) \ket { \psi } = | \braket { \psi | 0 } | ^2,$$

o que ilustra que os projetores simplesmente dão uma nova forma de expressar o processo de medição.

Se, em vez disso, considerarmos medir o primeiro qubit de um estado multi-qubit para ser $ $ 1, então também podemos descrever este processo convenientemente usando projetores e notação Dirac:

$$
P( \text { primeiro qubit = 1 } ) = \bra { \psi } \left ( \ket { 1 } \bra { 1 } \otimes \boldone ^ { \otimes n-1 } \right ) \ket { \psi } .
$$

Aqui a matriz de identidade pode ser convenientemente escrita na notação dirac como

$$
\boldone= \ket{ 0 } \bra { 0 } + \ket { 1 } \bra { } = \begin{bmatrix} 1 & 1 0 \\\\ & 0 1 \end{bmatrix} .
$$

Para o caso em que há dois qubits o projetor pode ser expandido como 

$$
\ket{1 } \bra { 1 } \otimes \id = \ket { } \bra { 1 1 } \otimes 1 ( \ket { 0 } \bra { 0 } + \ket { 1 } \bra { 1 } ) = \ket { 10 } \bra { 10 }  +  \ket { 11 } \bra { 11 } .
$$

Podemos então ver que isso é consistente com a discussão sobre as probabilidades de medição para estados multiqubit usando notação de coluna-vector:

$$
P( \text { primeiro qubit = 1 } ) = \psi ^ \dagger (e \_ { 10 } e \_ { 10 + e } ^ \dagger \_ { 11 e } \_ { 11) } ^ \dagger e \psi = | \_ { 10 } ^ \dagger \psi | ^2 + | e \_ { 11 } ^ \dagger \psi | ^2,$$

que corresponde à discussão de medição de múltiplos qubits.  A generalização deste resultado para o caso multi-qubit, no entanto, é um pouco mais simples de expressar usando a notação dirac do que a notação de vetores de coluna, e é inteiramente equivalente ao tratamento anterior.

## <a name="density-operators"></a>Operadores de densidade

Outro operador útil para expressar usando a notação Dirac é um *operador de densidade,* por vezes também conhecido como *um operador estatal.*
Um operador de densidade para um vetor de estado quântico toma a forma $ \rho = \ket { \psi } \bra { \psi } $ .
Este conceito de representar o Estado como uma matriz, em vez de um vetor, é muitas vezes conveniente porque dá uma maneira conveniente de representar cálculos de probabilidade, e também permite descrever tanto a incerteza estatística como a incerteza quântica dentro do mesmo formalismo.
Os operadores gerais do Estado quântico, em vez de vetores, são omnipresentes em algumas áreas da computação quântica, mas não são necessários para entender os fundamentos do campo.
Para o leitor interessado, recomendamos a leitura de um dos livros de referência fornecidos para [mais informações.](xref:microsoft.quantum.more-information)

## <a name="no-locq-gate-sequences-equivalent-to-quantum-states"></a>Q#sequências de portão equivalentes a estados quânticos
Um último ponto que vale a pena levantar sobre a notação quântica e Q# a linguagem de programação: no início deste documento mencionamos que o estado quântico é o objeto fundamental da informação na computação quântica.  Pode então ser uma surpresa que Q# não haja noção de estado quântico.  Em vez disso, todos os Estados são descritos apenas pelas operações usadas para os preparar.  O exemplo anterior é uma excelente ilustração disto.  Em vez de expressar uma sobreposição uniforme sobre cada corda quântica num registo, podemos representar o resultado como $ H^ { \otimes n } \ket { 0 } $ .  Esta descrição exponencialmente mais curta do estado não só tem a vantagem de que podemos raciocinar clássicamente sobre ele, mas também define concisamente as operações necessárias para ser propagada através da pilha de software para implementar o algoritmo.  Por esta razão, Q# é projetado para emitir sequências de portão em vez de estados quânticos; no entanto, a um nível teórico as duas perspetivas são equivalentes.
