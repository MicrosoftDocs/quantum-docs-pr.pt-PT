---
title: Notação Dirac
description: Aprenda a usar a notação de Dirac para representar estados quânticos e simular operações quânticas.
author: QuantumWriter
uid: microsoft.quantum.concepts.dirac
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 204e56cc97fe28f9c52dcfb882aadec7e09bb2dc
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907567"
---
# <a name="dirac-notation"></a>Notação Dirac

Embora a notação vetorial da coluna seja ubíqua na álgebra linear, é muitas vezes complicada na computação quântica especialmente quando se lida com vários qubits.  Por exemplo, quando definimos $\psi$ como um vetor, não é explicitamente claro se $\psi$ é uma linha ou um vetor de coluna.  Assim, se $\phi$ e $\psi$ são vetores, então é igualmente incerto se $\phi \psi$ é mesmo definido porque as formas de $\phi$ e $\psi$ podem não ser claras no contexto.  Para além da ambiguidade sobre as formas dos vetores, expressar mesmo vetores simples usando a notação algébrica linear introduzida anteriormente pode ser muito complicado. Por exemplo, se quisermos descrever um estado $n$-qubit onde cada qubit leva o valor $0$ então nós expressaríamos formalmente o estado como 

$$\start{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \cdots \otimes\start{bmatrix}1 \\\\ 0 \end{bmatrix}. $$  

Claro que avaliar este produto tensor é impraticável porque o vetor está num espaço exponencialmente grande e por isso esta notação é, de facto, a melhor descrição do estado que pode ser dada usando a notação anterior.  

[*A notação dirac*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) resolve estes problemas apresentando uma nova linguagem para se adaptar às necessidades precisas da mecânica quântica.  Por esta razão, recomendamos que o leitor não veja os exemplos nesta secção como uma prescrição rígida de como descrever estados quânticos, mas antes encorajar o leitor a encará-los como sugestões que podem ser usadas para expressar concisamente ideias quânticas.

Existem dois tipos de vetores na notação de Dirac: o vetor de *soutien* e o vetor de *ket,* assim chamado porque quando juntos formam um *travão* ou produto interno.  Se $\psi$ é um vetor de coluna, então podemos escrevê-lo na notação Dirac como $\ket{\psi}$, onde o $\ket{\cdot}$denota que é um vetor de coluna de unidade, ou seja, um vetor de *ket.*  Da mesma forma, o vetor de linha $\psi^\dagger$ é expresso como $\bra{\psi}$. Por outras palavras, $\psi^\dagger$ é obtido aplicando conjugação complexa em termos de entrada aos elementos da transposição de $\psi$. A notação do sutiã implica diretamente que $\braket{\psi}$é o produto interno do vetor $\psi$ consigo mesmo, que é, por definição, $1$.  

De uma forma mais geral, se $\psi$ e $\phi$ são vetores de estado quântico o seu produto interno é $\braket{\phi}}}},o que implica que a probabilidade de medir o estado $\ket{\psi}$ para ser $\ket{\phi}$ é $\travt{\phi\psi}\/^2$.  

A seguinte convenção é utilizada para descrever os estados quânticos que codificam os valores de zero e um (os estados de base computacional de um único qubit):

$$ \start{bmatrix} 1 \\\\ 0 \end{bmatrix} = \ket{0},\qquad \start {bmatrix} 0 \\\\ 1 \end{bmatrix} = \ket{1}.
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a>Exemplo: representar a operação Hadamard com notação de Dirac

A seguinte notação é frequentemente usada para descrever os estados que resultam da aplicação do portão Hadamard para $\ket{0}$ e $\ket{1}$ (que correspondem aos vetores unitários nas direções de $+x$ e $x$ na esfera bloch):

$$ \frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\ 1 \end{bmatrix}=H\ket{0} = \ket{+},\qquad \frac{1}{\sqrt{2}}\start{bmatrix} 1 \\\\ -1 \end{bmatrix} =H\ket{1} = \ket{-} .
$$

Estes estados também podem ser expandidos usando a notação Dirac como somas de $\ket{0}$ e $\ket{1}$:

$$ \ket{+} = \frac{1}{\sqrt{2}}(\ket{0} + \ket{1},\qquad \ket{-} = \frac{1}{\sqrt{2}}(\ket{0} - \ket{1}).
$$

### <a name="computational-basis-vectors"></a>Vetores de base computacional
Isto demonstra porque estes estados são muitas vezes chamados de *base computacional*: cada estado quântico pode sempre ser expresso como somas de vetores de base computacional e tais somas são facilmente expressas usando a notação de Dirac.  O inverso também é verdade na medida em que os Estados $\ket{+}$ e $\ket{-}$ também formam uma base para estados quânticos.  Pode ver isto pelo facto de que

$$ \ket{0} = \frac{1}{\sqrt{2}}(\ket{+} + \ket{-},\qquad \ket{1} = \frac{1}{\sqrt{2}}(\ket{+} - \ket{-}).
$$

Como exemplo da notação de Dirac, considere o travão $\braket{0 / 1}$, que é o produto interno entre $0$ e $1$1$.  Pode ser escrito como 

$$\braket{0 / 1}=\begin{bmatrix} 1 & 0 \end{bmatrix}\start{bmatrix}0\\\\ 1\end{bmatrix}=0,$$

Isto diz que $\ket{0}$ e $\ket{1}$ são vetores ortogonais, o que significa que $\braket{0 = 1} = \braket{1 } =0} =0$.  Também por definição $\braket{0 = \braket{1 / 1}=1$, o que significa que os dois vetores de base computacional também podem ser chamados *de ortonormal*.
Estas propriedades ortonormais serão úteis no seguinte exemplo. Se tivermos um estado $\ket{\psi} = {\frac{3}{5}} \ket{1} + {\frac{4}{5}} \ket{0}$ então porque $\braket{1 } =0$ a probabilidade de medir $1$ é  

$$\big\\travt{1  \psi}\big^^2= \left\frac{3}{5}\braket{1 } \frac{4}{5}\braket{1 / 0}\right\^2=\frac{9}{25}.$$ 

### <a name="tensor-product-notation"></a>Notação do produto tensor
A notação dirac também inclui uma estrutura implícita do produto tensor dentro dela.  Isto é importante porque na computação quântica, o vetor estatal descrito por dois registos quânticos não correlacionados são os produtos tensores dos dois vetores estatais.  Descrever concisamente a estrutura do produto tensor, ou falta dela, é vital se quiser explicar uma computação quântica.  A estrutura do produto tensor implica que podemos escrever $\psi \otimes \phi$ para qualquer dois vetores de estado quântico $\phi$ e $\psi$ como $\ket{\psi} \ket{\phi}$, às vezes explicitamente escrito como $\ket{\psi} \otimes \ket {\phi}},no entanto, por convenção que escreve $\otimes$ entre os vetores é desnecessário.  Por exemplo, o estado com dois qubits inicializados para o estado zero é dado por

$$ \start{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix}= \start{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \start {bmatrix} 1 \\\\ 0 \end{bmatrix} = \ket{0} \otimes \ket{0}= \ket{0} \ket{0}.
$$

Da mesma forma, o estado $\ket{p}$ para o inteiro $p$ representa um estado quântico que codifica em representação binária o inteiro $p$.  Por exemplo, se quisermos expressar o número $5$ usando uma codificação binária não assinada, poderíamos igualmente expressá-lo como

$$ \ket{1}\ket{0}\ket{1} = \ket{101} = \ket{5}.
$$

Dentro desta notação $\ket{0}$ não precisa se referir a um estado qubit único, mas sim a um *registo qubit* armazenando uma codificação binária de $0$.  As diferenças entre estas duas notações são geralmente claras do contexto.  Esta convenção é útil para simplificar o primeiro exemplo que pode ser escrito de qualquer das seguintes formas:

$$ \start{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \cdots \otimes\start{bmatrix}1 \\\\ 0 \end{bmatrix} = \ket{0} \otimes \cdots \otimes \ket{0}= 0\cdots 0\rangle = \ket{0}{\otimes n} = \{0}
$$

### <a name="example-describing-superposition-with-dirac-notation"></a>Exemplo: Descrever a superposição com notação de Dirac
Como outro exemplo de como pode usar a notação de Dirac para descrever um estado quântico, considere as seguintes formas equivalentes de escrever um estado quântico que é uma sobreposição igual em cada cadeia de comprimento possível $n$

$$ H^{\otimes n} \ket{0} = \frac{1}{2^{n/2}} \sum_{j=0}^{2^n-1} \ket{j} = \ket{{{\otimes n}.
$$

Aqui pode perguntar-se por que a soma vai de $0$ para $2^{n}-1$ por $n$.  Primeira nota que existem configurações diferentes de $2^{n}$ que $n bits de$$ podem tomar.  Pode ver isso notando que um bit pode levar valores de $2$, mas dois bits podem levar valores de $4$ e assim por diante. Em geral, isto significa que existem cordas de bits diferentes de $2^n$ diferentes, mas o maior valor codificado em qualquer uma delas $1\cdots 1=2^n-1$ e, portanto, é o limite superior para a soma.
Como nota lateral, neste exemplo não usámos $\ket{+}{\otimes n}=\ket{+}$ em analogia a $\ket{0}{\otimes n} = \ket{0}$ porque esta convenção de notação é normalmente reservada para o estado de base computacional com cada qubit inicializado a zero.  Embora tal convenção seja sensata neste caso, não está utilizada na literatura de computação quântica.

### <a name="expressing-linearity-with-dirac-notation"></a>Expressando linearidade com notação de Dirac
Outra boa característica da notação de Dirac é o facto de ser linear.  Se quisermos escrever para qualquer quatro vetores de estado quântico, 

$$(\alpha \ket{\psi} +\beta\ket{\phi}}\otimes (\gamma \ket{\chi} + \delta \ket{\omega})= \alpha\gamma \ket{\psi}\ket{\psi}\ket{\chi} + \alpha\delta \ket{\psi}\ket{\omega}\beta\gamma\ket{\phi}\ket{\chi}+beta\delta\ket{\phi}\ket{\phi}\ket{\}\ket{\omega}.$$$$$$

Ou seja, você pode distribuir a notação do produto tensor na notação Dirac para que tomar produtos tensores entre vetores estatais acaba por se parecer com a multiplicação ordinária.

Os vetores de sutiã seguem uma convenção semelhante aos vetores de ket.  Por exemplo, o vetor $\bra{\psi}\bra{\phi}$ é equivalente ao vetor estatal $\psi^\dagger \otimes \phi^\dagger=(\psi\otimes \phi)^\dagger$. Se o vetor de ket $\ket {\psi}$ for $\alpha \ket{0} + \beta \ket{1}$ então a versão vetor do soutien do vetor é $\bra{\psi}=\ket{\psi}^\dagger = (\bra{0}\alpha^* +\bra{1}\beta^*)$.

Como exemplo, imagine que queremos calcular a probabilidade de medir o estado $\ket{\psi} = \frac{3}{5} \ket{1} + \frac{4}{5} {0}$ usando um programa quântico para medir estados para ser $\ket{+}$ ou $\ket{-}$. Então a probabilidade de que o dispositivo iria output que o estado é $\ket{-}$ é 

$\\travão{-  \psi}\^2= \left\frac{1}{\sqrt{2}}(\bra{0} - \bra{1})(\frac{3}{5} \ket{1} + \frac{4}{5} \ket{0}) \direita/^2=\left;frac{3}{5\sqrt{2}} + {50}{1}{2}{4}frac

O facto de o sinal negativo aparecer no cálculo da probabilidade é uma manifestação de interferência quântica, que é um dos mecanismos pelos quais a computação quântica ganha vantagens em relação à computação clássica.

## <a name="ketbra-or-outer-product"></a>ketbra ou produto exterior
O item final que merece ser discutido na notação de Dirac é a *cesia* ou o produto exterior.  O produto exterior está representado dentro das notações de Dirac como $\ket{\psi} \bra{\phi}$, e às vezes chamado ketbras porque os soutiens e os kets ocorrem na ordem oposta como travões.  O produto exterior é definido através da multiplicação da matriz como $\ket{\psi} \bra{\phi} = \psi \phi^\dagger$ para vetores de estado quântico $\psi$ e $\phi$.  O exemplo mais simples, e indiscutivelmente mais comum desta notação, é

$$ \ket{0} \bra{0} = \begin {bmatrix}1\\\\ 0 \end{bmatrix}\start{bmatrix}1&0 \end{bmatrix}= \start{bmatrix}1 &0\\\\ 0 &0\end{bmatrix} \q quad \ket{1} \bra{1} = \start{bmatrix}0\\\\ 1 \end{bmatrix}\begin{bmatrix}0&1 \end{bmatrix}= \begin{bmatrix}0 &0\\\\ 0 &1\end{bmatrix}.
$$

As cetos são muitas vezes chamadas de projetores porque projetam um estado quântico num valor fixo.  Uma vez que estas operações não são unitárias (e nem sequer preservam a norma de um vetor), não deve surpreender-se que um computador quântico não possa aplicar determinicamente um projetor.  No entanto, os projetores fazem um belo trabalho ao descrever a ação que a medição tem num estado quântico.  Por exemplo, se medirmos um estado $\ket{\psi}$ para ser $0$ então a transformação resultante que o Estado experimenta como resultado da medição é

  $$\ket{\psi} \rightarrow \frac{(\ket{0} \bra{0})\ket{\psi}}{\travt{0  \psi}}} = \ket{0},$$

como se espera, se medir o Estado e encontrá-lo como $\ket{0}$.  Para reiterar, tais projetores não podem ser aplicados num estado num computador quântico determinicamente.  Em vez disso, podem, na melhor das hipóteses, ser aplicados aleatoriamente com o resultado $\ket{0}$ aparecendo com alguma probabilidade fixa.  A probabilidade de tal medição ter sucesso pode ser escrita como o valor de expectativa do projetor quântico no estado

$$ \bra{\psi} (\ket{0} \bra{0})\ket{\psi} = [\braket{\psi ] 0}\^^2, $$

que ilustra que os projetores simplesmente dão uma nova forma de expressar o processo de medição.

Se considerarmos, em vez disso, medir o primeiro qubit de um estado multiqubit a $1$ então também podemos descrever este processo convenientemente usando projetores e notação Dirac:

$$ P(\text{first qubit = 1})= \bra{\psi}\left(\ket{1}\bra{1}\otimes \boldone^{\otimes n-1}\right) \ket{\psi}.
$$

Aqui a matriz de identidade pode ser convenientemente escrita na notação Dirac como

$$ \boldone = \ket{0} \bra{0}+\ket{1} \sutiã{1}= \start{bmatrix}1&0\\\\ 0&1 \end{bmatrix}.
$$

Para o caso em que há dois qubits o projetor pode ser expandido como 

$$ \ket{1} \sutiã{1} \otimes \id = \ket{1}\bra{1} \otimes (\ket{0} \bra{0}+\ket{1} \bra{1})= \ket{10}\bra{10} + \ket{11}\bra{11}.
$$

Podemos então ver que isto é consistente com a discussão sobre as probabilidades de medição para estados multiqubit usando notação de vetor de coluna:

$$ P(\text{first qubit = 1})= \psi^\dagger (e\_{10}e\_{10}^\dagger + e\_{11}e\_{11}^\dagger)\psi = e\_{10}^\dagger \psi^2 + /e\_{11}\\apunhal \psi^2, $^2, $/

que corresponde à discussão de medição de vários qubits.  A generalização deste resultado ao caso multiqubit, no entanto, é ligeiramente mais simples de expressar usando a notação Dirac do que a notação do vetor de coluna, e é inteiramente equivalente ao tratamento anterior.

## <a name="density-operators"></a>Operadores de densidade

Outro operador útil para expressar usando a notação Dirac é um *operador de densidade*, por vezes também conhecido como operador *estatal*.
Um operador de densidade para um vetor de estado quântico toma a forma $\rho = \ket{\psi} \bra{\psi}$.
Este conceito de representar o estado como uma matriz, em vez de um vetor, é muitas vezes conveniente porque dá uma maneira conveniente de representar cálculos de probabilidade, e também permite descrever tanto a incerteza estatística como a incerteza quântica dentro do mesmo formalismo.
Os operadores gerais do estado quântico, em vez de vetores, são omnipresentes em algumas áreas da computação quântica, mas não são necessários para entender os fundamentos do campo.
Para o leitor que se pode ver, recomendamos a leitura de um dos livros de referência fornecidos para [mais informações.](xref:microsoft.quantum.more-information)

## <a name="q-gate-sequences-equivalent-to-quantum-states"></a>Q# sequências de portão equivalentes a estados quânticos
Um ponto final que vale a pena levantar sobre a notação quântica e a linguagem de programação Q#: no início deste documento mencionamos que o estado quântico é o objeto fundamental da informação na computação quântica.  Pode então ser uma surpresa que em Q# não há noção de um estado quântico.  Em vez disso, todos os Estados são descritos apenas pelas operações utilizadas para os preparar.  O exemplo anterior é uma excelente ilustração disso.  Em vez de expressar mossa uniforme sobre cada cadeia quântica num registo, podemos representar o resultado como $H^{\otimes n} \ket{0}$.  Esta descrição exponencialmente mais curta do estado não só tem a vantagem que podemos raciocinar clássicamente sobre isso, mas também define concisamente as operações necessárias para ser propagada através da pilha de software para implementar o algoritmo.  Por esta razão, Q# é projetado para emitir sequências de portão em vez de estados quânticos; no entanto, a nível teórico as duas perspetivas são equivalentes.
