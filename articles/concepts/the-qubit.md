---
title: O qubit na computação quântica
description: Conheça qubits, a unidade fundamental de informação na computação quântica.
author: QuantumWriter
uid: microsoft.quantum.concepts.qubit
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: f5e5c2a66899c552ad39e63703c34718818b1452
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426961"
---
# <a name="the-qubit"></a>O Qubit

Assim como os bits são o objeto fundamental da informação na computação clássica, [*qubits*](https://en.wikipedia.org/wiki/Qubit) (bits quânticos) são o objeto fundamental da informação na computação quântica.  Para compreender esta correspondência, vamos olhar para o exemplo mais simples: um único qubit.

## <a name="representing-a-qubit"></a>Representando um Qubit

Enquanto um pouco, ou dígito binário, pode ter valor de $0$ ou $1$1$, um qubit pode ter um valor que é um destes ou uma superposição quântica de $0$ e $1$1$.

O estado de um único qubit pode ser descrito por um vetor de coluna bidimensional da norma unitária, ou seja, a magnitude quadrada das suas entradas deve resumir-se a $1$1$. Este vetor, chamado vetor do estado quântico, contém toda a informação necessária para descrever o sistema quântico de um qubit, assim como uma única bit contém toda a informação necessária para descrever o estado de uma variável binária.

Qualquer vetor de coluna bidimensional de números reais ou complexos com norma $1$ representa um possível estado quântico detido por um qubit. Assim, $\start{bmatrix} \alpha \\ \\ \beta \beta {bmatrix}$ representa um estado qubit se $\alpha$ e $\beta$ são números complexos que satisfazem $\//alfa^2 + \\beta^2 = 1$. Alguns exemplos de vetores de estado quântico válidos que representam qubits incluem

$$\start{bmatrix} 1 \\ \\ 0 \end{bmatrix}, \start{bmatrix} 0 \\ \\ 1 \end{bmatrix}, \begin{bmatrix} \frac {1} {\sqrt {2} } \\ \\ \frac {1} {\sqrt {2} } \end{bmatrix}, \start{bmatrix} \frac {1} {\sqrt {2} } \\ \\ \frac {-1} {\sqrt {2} } \end{bmatrix}, \text{ e {\start{bmatrix} \frac {1} {\sqrt {2} } \\ \\ {{{{{}}}}} {2}

Os vetores do estado quântico $\start{bmatrix} 1 \\ \\ 0 \end{bmatrix}$ e $\start{bmatrix} 0 \\ \\ 1 \end{bmatrix}$ assumem um papel especial. Estes dois vetores formam uma base para o espaço vetorial que descreve o estado do qubit. Isto significa que qualquer vetor de estado quântico pode ser escrito como uma soma destes vetores base. Especificamente, o vetor $\begin{bmatrix} x \\ \\ y \end{bmatrix}$ pode ser escrito como $x \start{bmatrix} 1 \\ \\ 0 \end{bmatrix} + y \begin{bmatrix} 0 \\ \\ 1 \end{bmatrix}$. Embora qualquer rotação destes vetores serviria como uma base perfeitamente válida para o qubit, optamos por privilegiar este, chamando-lhe a *base computacional*.

Levamos estes dois estados quânticos para corresponder aos dois estados de uma parte clássica, ou seja, $0$ e $1$. A convenção padrão é escolher

$$0\equiv \start{bmatrix} 1 \\ \\ 0 \end{bmatrix}, \qquad 1 \equiv \start{bmatrix} 0 \\ \\ 1 \end{bmatrix},$$

embora a escolha oposta poderia igualmente bem ser tomada. Assim, do número infinito de possíveis vetores de estado quântico de qubit, apenas dois correspondem a estados de bits clássicos; todos os outros estados quânticos não.

## <a name="measuring-a-qubit"></a>Medindo um Qubit

Agora que sabemos representar um qubit, podemos ganhar alguma intuição para o que estes Estados representam, discutindo o conceito de [*medição.*](https://en.wikipedia.org/wiki/Measurement_in_quantum_mechanics) Uma medição corresponde à ideia informal de "olhar" para um qubit, que imediatamente colapsa o estado quântico para um dos dois estados clássicos $\start{bmatrix} 1 \\ \\ 0 \end{bmatrix}} ou $\start{bmatrix} 0 \\ \\ 1 \end{bmatrix}$. Quando um qubit dado pelo vetor do estado quântico $\start{bmatrix} \alpha \\ \\ \beta \end {bmatrix}$ é medido, obtemos o resultado $0$ com probabilidade $\alfa^^2$ e o resultado $1$ com probabilidade $\beta^^^2$. No resultado $0$, o novo estado do qubit é $\start{bmatrix} \\ \\ 10 \end{bmatrix}$; no resultado $1$ o seu estado é $\start{bmatrix} 0 \\ \\ \end{bmatrix}$. Note que estas probabilidades são até $1$ devido à condição de normalização $\alfa^2 + \beta^2 = 1$.

As propriedades da medição também significam que o sinal geral do vetor do estado quântico é irrelevante. Negar um vetor é equivalente a $\alfa \alfa -\alfa$ e $\beta \rightarrow -\beta$. Porque a probabilidade de medir $0$ e $1$ depende da magnitude quadrada dos termos, inserir tais sinais não altera as probabilidades. Tais fases são geralmente chamadas [ `` *de fases globais*''](https://en.wikipedia.org/wiki/Phase_factor) e geralmente podem ser da forma $e{i \phi}$ em vez de apenas $\pm 1$.

Uma propriedade importante final da medição é que não danifica necessariamente todos os vetores do estado quântico. Se começarmos com um qubit no estado $\start{bmatrix} \\ \\ 10 \end{bmatrix}$, que corresponde ao estado clássico $0$, medindo este estado sempre renderá o resultado $0$ e deixará o estado quântico inalterado. Neste sentido, se tivermos apenas bits clássicos (isto é, qubits que são $\start{bmatrix}1 \\ \\ 0 \end{bmatrix}$ ou $\begin{bmatrix}0 \\ \\ \end{bmatrix}$$) então a medição não danifica o sistema. Isto significa que podemos replicar dados clássicos e manipulá-lo num computador quântico, tal como se poderia fazer num computador clássico. A capacidade, no entanto, de armazenar informação em ambos os estados é o que eleva a computação quântica para além do que é possível clássicamente e rouba ainda mais computadores quânticos da capacidade de copiar dados quânticos indiscriminadamente, ver também [o teorema de não clonagem.](https://en.wikipedia.org/wiki/No-cloning_theorem)

## <a name="visualizing-qubits-and-transformations-using-the-bloch-sphere"></a>Visualizar Qubits e Transformações usando a Esfera bloch

Os qubits também podem ser retratados em $3$D usando a representação da [*esfera bloch.*](https://en.wikipedia.org/wiki/Bloch_sphere)  A esfera bloch dá uma maneira de descrever um estado quântico monodimensional (que é um vetor complexo bidimensional) como um vetor de valor real tridimensional.  Isto é importante porque nos permite visualizar estados de qubit único e, assim, desenvolver raciocínios que podem ser inestimáveis na compreensão de estados multiqubit (onde, infelizmente, a representação da esfera bloch se decompõe).  A esfera bloch pode ser visualizada da seguinte forma:

<!--- ![](.\media\bloch.svg){ width=50% } --->
![Esfera de Bloch](~/media/concepts_bloch.png)

As setas neste diagrama mostram a direção em que o vetor do estado quântico está apontando e cada transformação da seta pode ser considerada como uma rotação sobre um dos eixos cardeais.
Embora pensar numa computação quântica como uma sequência de rotações seja uma intuição poderosa, é um desafio usar esta intuição para desenhar e descrever algoritmos. Q# alivia esta questão fornecendo uma linguagem para descrever tais rotações.

## <a name="single-qubit-operations"></a>Operações De Qubit Único

Os computadores quânticos processam dados aplicando um conjunto universal de portões quânticos que podem imitar qualquer rotação do vetor do estado quântico.
Esta noção de universalidade é semelhante à noção de universalidade para a computação tradicional (isto é, clássica) onde um conjunto de portão é considerado universal se cada transformação dos bits de entrada puder ser realizada usando um circuito de comprimento finito.
Na computação quântica, as transformações válidas que podemos realizar num qubit são transformações e medição unitárias.
A *operação adjoint* ou a complexa transposição conjugada é de importância crucial para a computação quântica porque é necessário inverter as transformações quânticas.
Q# reflete-o fornecendo métodos para compilar automaticamente as sequências do portão para o seu adjoint, o que evita que o programador tenha de ter de entregar adjoints de código manual em muitos casos. Um exemplo disto é mostrado abaixo:

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Adj { // Auto-generate the adjoint of the operation
    H(qubit);
}
```

Embora este seja um exemplo trivial (como a <xref:microsoft.quantum.intrinsic.h> operação é auto-adjoint), você pode ver como isso se torna inestimável para operações qubit mais complicadas.
Para mais informações, consulte [Operações e Funções.](xref:microsoft.quantum.guide.operationsfunctions)

Há apenas quatro funções que mapeiam um pouco a um pouco num computador clássico. Em contraste, há um número infinito de transformações unitárias num único qubit num computador quântico. Portanto, nenhum conjunto finito de operações quânticas primitivas, chamadas [*portões,*](https://en.wikipedia.org/wiki/Quantum_logic_gate)pode exatamente replicar o conjunto infinito de transformações unitárias permitidas na computação quântica. Isto significa que, ao contrário da computação clássica, é impossível para um computador quântico implementar todos os programas quânticos possíveis exatamente usando um número finito de portões. Assim, os computadores quânticos não podem ser universais no mesmo sentido dos computadores clássicos. Como resultado, quando dizemos que um conjunto de portões é *universal* para a computação quântica, na verdade significamos algo ligeiramente mais fraco do que queremos dizer com a computação clássica.
Para a universalidade, exigimos que um computador quântico *apenas se aproximar* de cada matriz unitária dentro de um erro finito usando uma sequência de portão de comprimento finito.
Por outras palavras, um conjunto de portões é um conjunto de portão universal se qualquer transformação unitária pode ser escrita aproximadamente como um produto de portões deste conjunto. Exigimos que, para qualquer erro prescrito, existam portões $G_ {1} , G_ {2} ,\ldots, G_N$ do portão definido de tal forma que

$$ G_N G_{N-1} \cdots G_2 G_1 \aprox U. $$

Note que, como a convenção para a multiplicação da matriz é multiplicar da direita para a esquerda a primeira operação do portão nesta sequência, $G_N$, é na verdade a última aplicada ao vetor do estado quântico. Mais formalmente, dizemos que tal conjunto de portão é universal se por cada erro tolerância $\epsilon>0$ existe $G_1,\ldots, G_N$ de tal forma que a distância entre $G_N\ldots G_1$ e $U$ é no máximo $\epsilon$. Idealmente, o valor de $N$ necessário para atingir esta distância de $\epsilon$ deve escalar poli-logarithmly com $1/\epsilon$.

Como é que um portão tão universal se parece na prática?  O portão universal mais simples para portões de um único qubit consiste em apenas dois portões: o portão hadamard $H$ e o chamado $T$-gate (também conhecido como portão $\pi/8$):

$$ H=\frac {1} {\sqrt {2} }\begin{bmatrix} 1 & 1 \\ \\ 1 &-1 \end{bmatrix},\qquad T=\start{bmatrix} 1 & \\ \\ 0 & e^{i\pi/4} \end{bmatrix}.
$$

No entanto, por razões práticas relacionadas com a correção de erros quânticos, pode ser mais conveniente considerar um conjunto de portamaior, nomeadamente um que pode ser gerado usando $H$ e $T$.
Podemos classificar os portões quânticos em duas categorias: portões Clifford e o $T$-gate.
Esta subdivisão é útil porque em muitos esquemas de correção de erros quânticos os chamados portões Clifford são fáceis de implementar, ou seja, exigem muito poucos recursos em termos de operações e qubits para implementar falhas tolerantemente, enquanto os portões não Clifford são bastante dispendiosos quando exigem tolerância à falha. O conjunto padrão de portões Clifford de monoqubit, [incluído por padrão em Q#](xref:microsoft.quantum.libraries.standard.prelude), incluem

$$ H=\frac {1} {\sqrt {2} }\begin{bmatrix} 1 & 1 \\ \\ 1 &-1 \end{bmatrix} ,\qquad S =\start{bmatrix} 1 & \\ \\ 0 & i \end{bmatrix}= T^2,\qquad X=\start{bmatrix} 0 &\\ \\ 1& 0 \end{bmatrix}= HT^4H, $$

$$ Y = \begin{bmatrix} 0 & \\ \\ -i i & 0 \end{bmatrix}=T^2HT^4 HT^6, \qquad Z=\start{bmatrix} 1&\\ \\ 0 0&-1 \end{bmatrix}=T^4.
$$

Aqui as operações $X$, $Y$ e $Z$ são usadas especialmente frequentemente e são chamadas [*operadoras Pauli*](https://en.wikipedia.org/wiki/Pauli_matrices) em homenagem ao seu criador Wolfgang Pauli.
Juntamente com o portão não Clifford (o $T$-gate), estas operações podem ser compostas para aproximar qualquer transformação unitária num único qubit.

Para obter mais informações sobre estas operações, as suas representações na esfera bloch e as implementações q#, ver [Operações e Funções Intrínsecas.](xref:microsoft.quantum.libraries.standard.prelude#intrinsic-operations-and-functions)

Como exemplo de como as transformações unitárias podem ser construídas a partir destes primitivos, as três transformações retratadas nas esferas do Bloch acima correspondem à sequência do portão $\start{bmatrix} 1 \\ \\ 0 \end{bmatrix} \mapsto HZH \start{bmatrix} 1 \\ \\ 0 \end{bmatrix} = \begin{bmatrix} 0 \\ \\ 1 \end{bmatrix}}$.

Embora os anteriores constituam os portões primitivos mais populares para descrever operações ao nível lógico da pilha (pense no nível lógico como o nível do algoritmo quântico), é muitas vezes conveniente considerar operações menos básicas a nível algorítmico, por exemplo operações mais próximas de um nível de descrição da função. Felizmente, q# também tem métodos disponíveis para implementar unitários de alto nível, que por sua vez permitem que algoritmos de alto nível sejam implementados sem decompor explicitamente tudo para Clifford e $T$-gates.

O mais simples é o mais simples é a rotação qubit única. Três rotações de qubit simples são tipicamente consideradas: $R_x$, $R_y$ e $R_z$. Para visualizar a ação da rotação $R_x(\theta)$, por exemplo, imagine apontar o polegar direito ao longo da direção do eixo $x$da esfera bloch e rodar o vetor com a mão através de um ângulo de radianos de $\theta/2$. Este fator confuso de $2$ surge do facto de os vetores ortogonais estarem a $180^\circ$ separados quando traçados na esfera bloch, mas na verdade são graus de $90^\circ$ separados geometricamente. As matrizes unitárias correspondentes são:

\begin{align *} &R_z(\theta) = e^{-i\theta Z/2} = \start{bmatrix} e{-i\theta/2} & \\ \\ 0& e^{i\theta/2} \end{bmatrix}, \\ \\ &R_x(\theta) = e^{-i\theta X/2} = HR_z(\theta)H = \start{bmatrix} \cos(\theta/2) & -i\sin(\theta/2) \\ \\ -i\sin(\theta/2) & \cos (\theta/2) \end{bmatrix} \\ \\ &R_y(\theta) = e^{-i\theta Y/2} = SHR_z(\theta)HS^\dagger = \start{bmatrix} \cos(\theta/2) & -\sin(\theta/2) \\ \\ \sin (\theta/2) & \cos(\theta/2) \end{bmatrix.*

Assim como quaisquer três rotações podem ser combinadas para realizar uma rotação arbitrária em três dimensões, pode ser visto a partir da representação da esfera bloch que qualquer matriz unitária pode ser escrita como uma sequência de três rotações também. Especificamente, para cada matriz unitária $U$ existe $\alpha,\beta,\gamma,\delta$ tal que $U= e^{i\alfa} R_x(\beta)R_z(\gama)R_x(\delta)$. Assim, $R_z (\theta)$ e $H$ também formam um conjunto de portão universal, embora não seja um conjunto discreto porque $\theta$ pode ter qualquer valor. Por esta razão, e devido a aplicações em simulação quântica, tais portas contínuas são cruciais para a computação quântica, especialmente ao nível do design de algoritmos quânticos. Para conseguir a implementação de hardware tolerante a falhas, eles serão, em última análise, compilados em sequências discretas de porta que aproximam de perto estas rotações.
