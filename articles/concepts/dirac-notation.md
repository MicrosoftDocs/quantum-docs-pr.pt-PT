---
title: Notação de Dirac | Microsoft Docs
description: Notação de Dirac
author: QuantumWriter
uid: microsoft.quantum.concepts.dirac
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 33d964d079c94bd947e35d2c09516b29df1bba11
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184768"
---
# <a name="dirac-notation"></a>Notação de Dirac

Embora a notação de vetor de coluna seja onipresente em Algebra linear, ela geralmente é complicada na computação Quantum, especialmente ao lidar com vários qubits.  Por exemplo, quando definimos $ \psi $ para ser um vetor, ele não fica explicitamente claro se $ \psi $ é uma linha ou um vetor de coluna.  Portanto, se $ \phi $ e $ \psi $ forem vetores, ele será igualmente desmarcado se $ \phi \psi $ for definido, já que as formas de $ \phi $ e $ \psi $ podem não ser claras no contexto.  Além da ambiguidade sobre as formas de vetores, expressar até mesmo vetores simples usando a notação algébricas linear introduzida anteriormente pode ser muito complicado. Por exemplo, se quisermos descrever um estado $n $-qubit, em que cada qubit usa o valor $0 $, formalmente expressos o estado como 

$ $ \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \cdots \otimes\begin{bmatrix}1 \\\\ 0 \end{bmatrix}. $$  

É claro que avaliar esse produto tensor é impraticável porque o vetor está em um espaço exponencialmente grande e, portanto, essa notação é, na verdade, a melhor descrição do estado que pode ser fornecido usando a notação anterior.  

A [*notação Dirac*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) resolve esses problemas apresentando uma nova linguagem para se adequar às necessidades exatas da mecânica quantum.  Por esse motivo, recomendamos que o leitor não exiba os exemplos nesta seção como uma receita rígida de como descrever os Estados da Quantum, mas, em vez disso, incentive o leitor a exibi-los como sugestões que podem ser usadas para expressar as ideias da Quantum de forma concisa.

Há dois tipos de vetores na notação Dirac: o vetor *Bra* e o vetor *ket* , portanto, nomeados porque, quando agrupados, formam um produto de *freio* ou interno.  Se $ \psi $ for um vetor de coluna, poderá escrevê-lo na notação Dirac como $ \ket{\psi} $, em que $ \ket{\cdot} $ denota que se trata de um vetor de coluna de unidade, ou seja, um vetor de *ket* .  Da mesma forma, o vetor de linha $ \psi ^ \dagger $ é expresso como $ \bra{\psi} $. Em outras palavras, $ \psi ^ \dagger $ é obtido pela aplicação de um conjugado complexo de entrada nos elementos da Transpose de $ \psi $. A notação bra-ket indica diretamente que $ \braket{\psi | \psi} $ é o produto interno do vector $ \psi $, que é por definição $1 $.  

Em geral, se $ \psi $ e $ \phi $ forem vetores de estado da Quantum, seu produto interno será $ \braket{\phi | \psi} $, o que significa que a probabilidade de medir o estado $ \ket{\psi} $ como $ \ket{\phi} $ é $ | \braket{\phi | \psi} | ^ 2 $.  

A Convenção a seguir é usada para descrever os Estados do Quantum que codificam os valores de zero e um (os Estados de base computacional de qubit único):

$ $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} = \ket{0}, \qquad \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} = \ket{1}.
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a>Exemplo: representando a operação Hadamard com notação Dirac

A notação a seguir é geralmente usada para descrever os Estados resultantes da aplicação da porta Hadamard a $ \ket{0}$ e $ \ket{1}$ (que correspondem aos vetores de unidade nas direções $ + x $ e $-x $ na esfera Bloch):

$ $ \frac{1}{\sqrt{2}} \begin{bmatrix} 1 \\\\ 1 \end{bmatrix} = H\ket{0} = \ket{+}, \qquad \frac{1}{\sqrt{2}} \begin{bmatrix} 1 \\\\-1 \end{bmatrix} = H\ket{1} = \ket{-} .
$$

Esses Estados também podem ser expandidos usando a notação Dirac como somas de $ \ket{0}$ e $ \ket{1}$:

$ $ \ket{+} = \frac{1}{\sqrt{2}} (\ket{0} + \ket{1}), \qquad \ket{-} = \frac{1}{\sqrt{2}} (\ket{0}-\ket{1}).
$$

### <a name="computational-basis-vectors"></a>Vetores de base computacional
Isso demonstra por que esses Estados geralmente são chamados de uma *base computacional*: cada Estado Quantum sempre pode ser expresso como somas de vetores de base computacional e essas somas são facilmente expressas usando a notação Dirac.  O inverso também é verdadeiro, pois os Estados $ \ket{+} $ e $ \ket{-}$ também formam uma base para os Estados da Quantum.  Você pode ver isso do fato de que

$ $ \ket{0} = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}), \qquad \ket{1} = \frac{1}{\sqrt{2}} (\ket{+}-\ket{-}).
$$

Como exemplo de notação Dirac, considere o freio $ \braket{0 | 1} $, que é o produto interno entre $0 $ e $1 $.  Ele pode ser escrito como 

$ $ \braket{0 | 1} = \begin{bmatrix} 1 & 0 \end{bmatrix}\begin{bmatrix}0\\\\ 1 \ fim {bmatrix} = 0. $ $

Isso diz que $ \ket{0}$ e $ \ket{1}$ são vetores ortogonal, o que significa que $ \braket{0 | 1} = \braket{1 | 0} = $0.  Também por definição $ \braket{0 | 0} = \braket{1 | 1} = 1 $, o que significa que os dois vetores de base computacional também podem ser chamados de *orthonormal*.
Essas propriedades orthonormal serão úteis no exemplo a seguir. Se tivermos um estado $ \ket{\psi} = {\frac{3}{5}} \ket{1} + {\frac{4}{5}} \ket{0}$, porque $ \braket{1 | 0} = $0 a probabilidade de medir $1 $ é  

$ $ \big | \braket{1 | \psi}\big | ^ 2 = \left | \frac{3}{5}\braket{1 | 1} + \frac{4}{5}\braket{1 | 0} \right | ^ 2 = \frac{9}{25}. $ $ 

### <a name="tensor-product-notation"></a>Notação de produto do tensor
A notação Dirac também inclui uma estrutura de produto tensor implícita dentro dela.  Isso é importante porque, na computação Quantum, o vetor de estado descrito por dois registros Quantum não correlacionados são os produtos tensor dos dois vetores de estado.  A descrição concisa da estrutura do produto tensor, ou a falta deles, é vital se você quiser explicar uma computação Quantum.  A estrutura do produto tensor implica que podemos escrever $ \psi \otimes \phi $ para quaisquer dois vetores de estado Quantum $ \phi $ e $ \psi $ como $ \ket{\psi} \ket{\phi} $, às vezes explicitamente escritos como $ \ket{\psi} \otimes \ket{\phi} $, porém por convenção escrevendo $ \otimes $ entre os vetores é desnecessário.  Por exemplo, o estado com dois qubits inicializados para o estado zero é fornecido por

$ $ \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} = \ket{0} \ OTimes \ket{0}= \ket{0} \ket{0}.
$$

Da mesma forma, o estado $ \ket{p} $ para Integer $p $ representa um estado Quantum que codifica na representação binária o inteiro $p $.  Por exemplo, se quisermos expressar o número $5 $ usando uma codificação binária não assinada, poderia ser expressado igualmente como

$ $ \ket{1}\ket{0}\ket{1} = \ket{101} = \ket{5}.
$$

Nesta notação $ \ket{0}$ não é necessário fazer referência a um estado de qubit único, mas sim um *registro de qubit* armazenando uma codificação binária de $0 $.  As diferenças entre essas duas notações geralmente são claras do contexto.  Essa convenção é útil para simplificar o primeiro exemplo que pode ser escrito de qualquer uma das seguintes maneiras:

$ $ \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \cdots \otimes\begin{bmatrix}1 \\\\ 0 \end{bmatrix} = \ket{0} \otimes \cdots \otimes \ket{0}= | 0 \ cdots 0 \ rangle = \ket{0}^ {\otimes n} = \ket{0}.
$$

### <a name="example-describing-superposition-with-dirac-notation"></a>Exemplo: descrevendo a superposição com a notação Dirac
Como outro exemplo de como você pode usar a notação Dirac para descrever um estado Quantum, considere as seguintes maneiras equivalentes de escrever um estado Quantum que seja uma superposição igual em cada cadeia de caracteres de bits possível de comprimento $n $

$ $ H ^ {\otimes n} \ket{0} = \frac{1}{2 ^ {n/2}} \sum_{j = 0} ^ {2 ^ n-1} \ket{j} = \ket{+} ^ {\otimes n}.
$$

Aqui você pode estar imaginando por que a soma vai de $0 $ a $2 ^ {n}-$1 para $n $ bits.  Primeiro, observe que há $2 ^ {n} $ configurações diferentes que $n $ bits pode executar.  Você pode ver isso observando que um bit pode receber de $2 $ valores, mas dois bits podem receber de $4 $ valores e assim por diante. Em geral, isso significa que há $2 ^ n $ diferentes cadeias de caracteres de bits possíveis, mas o maior valor codificado em qualquer um deles $1 \ cdots 1 = 2 ^ n-$1 e, portanto, é o limite superior para a soma.
Como uma observação adicional, neste exemplo, não usamos $ \ket{+} ^ {\otimes n} = \ket{+} $ em analogia com $ \ket{0}^ {\otimes n} = \ket{0}$ porque essa Convenção de notação é geralmente reservada para o estado de base computacional com cada qubit inicializada como zero.  Embora essa convenção seja sensata nesse caso, ela não é empregada na literatura de computação Quantum.

### <a name="expressing-linearity-with-dirac-notation"></a>Expressando a linearidade com a notação Dirac
Outro recurso interessante da notação Dirac é o fato de que ela é linear.  Se quisermos escrever para quaisquer quatro vetores de estado Quantum, 

$ $ (\alpha \ket{\psi} + \beta\ket{\phi}) \otimes (\gamma \ket{\chi} + \delta \ket{\omega}) = \alpha\gamma \ket{\psi}\ket{\chi} + \alpha\delta \ket{\psi}\ket{\omega} + \beta\gamma\ket{\phi}\ket{\chi} + \beta\delta\ket{\phi}\ket{\omega}. $ $

Ou seja, você pode distribuir a notação de produto do tensor na notação Dirac para que a obtenção de produtos tensor entre os vetores de estado termine de forma semelhante à multiplicação comum.

Os vetores Bra seguem uma convenção semelhante para vetores ket.  Por exemplo, o vetor $ \bra{\psi}\bra{\phi} $ é equivalente ao do estado vector $ \psi ^ \dagger \otimes \phi ^ \dagger = (\psi\otimes \phi) ^ \dagger $. Se o vetor de ket $ \ket{\psi} $ for $ \alpha \ket{0} + \beta \ket{1}$, a versão de vetor Bra do vetor será $ \bra{\psi} = \ket{\psi} ^ \dagger = (\bra{0}\alpha ^ * + \bra{1}\beta ^ *) $.

Como exemplo, imagine que desejamos calcular a probabilidade de medir o estado $ \ket{\psi} = \frac{3}{5} \ket{1} + \frac{4}{5} \ket{0}$ usando um programa Quantum para medir Estados como $ \ket{+} $ ou $ \ket{-}$. Em seguida, a probabilidade de o dispositivo gerar o estado como $ \ket{-}$ é 

$ $ | \braket{-| \psi} | ^ 2 = \left | \frac{1}{\sqrt{2}} (\bra{0}-\bra{1}) (\frac{3}{5} \ket{1} + \frac{4}{5} \ket{0}) \right | ^ 2 = \left |-\frac{3}{5 \ sqrt{2}} + \frac{4}{5 \ sqrt{2}} \right | ^ 2 = \frac{1}{50}. $ $

O fato de que o sinal negativo aparece no cálculo da probabilidade é uma manifestação da interferência Quantum, que é um dos mecanismos pelos quais a computação Quantum Obtém vantagens sobre a computação clássica.

## <a name="ketbra-or-outer-product"></a>produto ketbra ou externo
O item final que vale a pena discutir na notação Dirac é o produto *ketbra* ou externo.  O produto externo é representado em notações de Dirac como $ \ket{\psi} \bra{\phi} $ e às vezes é chamado de ketbras porque o Bras e o Kets ocorrem na ordem oposta como brakets.  O produto externo é definido por meio da multiplicação de matriz como $ \ket{\psi} \bra{\phi} = \psi \phi ^ \dagger $ para os vetores de estado Quantum $ \psi $ e $ \phi $.  O exemplo mais simples, e comprovadamente mais comum dessa notação, é

$ $ \ket{0} \bra{0} = \begin{bmatrix}1\\\\ 0 \end{bmatrix}\begin{bmatrix}1 & 0 \end{bmatrix} = \begin{bmatrix}1 & 0\\\\ 0 & 0 \ end {bmatrix} \qquad \ket{1} \bra{1} = \begin{bmatrix}0\\\\ 1 \end{bmatrix}\begin{bmatrix}0 & 1 \end{bmatrix} = \begin{bmatrix}0 & 0\\\\ 0 & 1 \ fim {bmatrix}.
$$

Ketbras geralmente são chamados de projetores porque projetam um estado Quantum em um valor fixo.  Como essas operações não são de forma uniforme (e nem mesmo preservam a norma de um vetor), ela deve ser tão surpresa que um computador Quantum não pode aplicar de forma determinística um projetor.  No entanto, os projetores fazem um lindo trabalho de descrever a ação que a medição tem em um estado Quantum.  Por exemplo, se medirmos um estado $ \ket{\psi} $ para ser $0 $, a transformação resultante que o estado enfrenta como resultado da medição é

  $ $ \ket{\psi} \rightarrow \frac{(\ket{0} \bra{0}) \ket{\psi}}{| \braket{0 | \psi} |} = \ket{0}, $ $

como esperado, se você pretende medir o estado e encontrá-lo como $ \ket{0}$.  Para reiterar, esses projetores não podem ser aplicados em um estado em um computador Quantum de forma determinista.  Em vez disso, eles podem ser aplicados aleatoriamente com o resultado $ \ket{0}$ aparecendo com alguma probabilidade fixa.  A probabilidade de tal medida ser realizada com sucesso pode ser escrita como o valor de expectativa do projetor Quantum no estado

$ $ \bra{\psi} (\ket{0} \bra{0}) \ket{\psi} = | \braket{\psi | 0} | ^ 2, $ $

que ilustra que os projetores simplesmente fornecem uma nova maneira de expressar o processo de medição.

Se, em vez disso, considerarmos medir a primeira qubit de um estado de qubit para ser $1 $, também podemos descrever esse processo convenientemente usando projetores e notação de Dirac:

$ $ P (\Text{First qubit = 1}) = \bra{\psi}\left (\ket{1}\bra{1}\otimes \boldone ^ {\otimes n-1} \right) \ket{\psi}.
$$

Aqui, a matriz de identidade pode ser convenientemente escrita em notação de Dirac como

$ $ \boldone = \ket{0} \bra{0}+ \ket{1} \bra{1}= \begin{bmatrix}1 & 0\\\\ 0 & 1 \end{bmatrix}.
$$

Para o caso em que há dois-qubits, o projetor pode ser expandido como 

$ $ \ket{1} \bra{1} \otimes \id = \ket{1}\bra{1} \otimes (\ket{0} \bra{0}+ \ket{1} \bra{1}) = \ket{10}\bra{10} + \ket{11}\bra{11}.
$$

Podemos ver que isso é consistente com a discussão sobre as chances de medição dos Estados multiqubit usando a notação de vetor de coluna:

$ $ P (\Text{First qubit = 1}) = \psi ^ \dagger (e\_{10}e\_{10}^ \dagger + e\_{11}e\_{11}^ \dagger) \psi = | e\_{10}^ \dagger \psi | ^ 2 + | e\_{11}^ \ Dagger \psi | ^ 2, $ $

que corresponde à discussão sobre a medição de várias qubit.  A generalização desse resultado para o caso qubit, no entanto, é um pouco mais simples de expressar usando notação de Dirac do que a notação de vetor de coluna e é totalmente equivalente ao tratamento anterior.

## <a name="density-operators"></a>Operadores de densidade

Outro operador útil para expressar usando a notação Dirac é um *operador de densidade*, às vezes também conhecido como um *operador de estado*.
Um operador de densidade para um vetor de estado Quantum tem a forma $ \rho = \ket{\psi} \bra{\psi} $.
Esse conceito de representar o estado como uma matriz, em vez de um vetor, geralmente é conveniente porque fornece uma maneira conveniente de representar cálculos de probabilidade e também permite que você descreva a incerteza estatística, bem como a incerteza de Quantum no mesmo formal.
Os operadores de estado geral do Quantum, em vez de vetores, são onipresentes em algumas áreas da computação Quantum, mas não são necessários para entender os conceitos básicos do campo.
Para o leitor interessado, é recomendável ler um dos livros de referência fornecidos no [para obter mais informações](xref:microsoft.quantum.more-information).

## <a name="q-gate-sequences-equivalent-to-quantum-states"></a>Sequências de portão Q # equivalentes a Estados Quantum
Um ponto final que vale a pena disparar a notação Quantum e a linguagem de programação Q #: no início deste documento, mencionamos que o estado do Quantum é o objeto fundamental das informações na computação Quantum.  Em seguida, ele pode ser uma surpresa que, em Q #, não há nenhuma noção de um estado Quantum.  Em vez disso, todos os Estados são descritos somente pelas operações usadas para prepará-los.  O exemplo anterior é uma ilustração excelente disso.  Em vez de expressar uma superposição uniforme em cada cadeia de caracteres de bit Quantum em um registro, podemos representar o resultado como $H ^ {\otimes n} \ket{0}$.  Essa descrição exponencialmente mais curta do estado não apenas tem a vantagem de que podemos, de forma clássica, a respeito disso, mas também define de forma concisa as operações necessárias para serem propagadas por meio da pilha de software para implementar o algoritmo.  Por esse motivo, o Q # foi projetado para emitir sequências de portão em vez de Estados de Quantum; no entanto, em um nível teórico, as duas perspectivas são equivalentes.

