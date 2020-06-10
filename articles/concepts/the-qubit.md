---
title: O qubit na computação quântica
description: Conheça os qubits, a unidade fundamental de informação na computação quântica.
author: QuantumWriter
uid: microsoft.quantum.concepts.qubit
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
ms.openlocfilehash: 833c9649b7fbcf8b9fde62c37246b9345fe59a92
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630344"
---
# <a name="the-qubit"></a>O Qubit

Assim como os bits são o objeto fundamental da informação na computação clássica, [*os qubits*](https://en.wikipedia.org/wiki/Qubit) (bits quânticos) são o objeto fundamental da informação na computação quântica.  Para compreender esta correspondência, vejamos o exemplo mais simples: um único qubit.

## <a name="representing-a-qubit"></a>Representando um Qubit

Enquanto um pouco, ou dígito binário, pode ter valor de $0 $ ou $1, $ um qubit pode ter um valor que é um destes ou uma superposição quântica de $0 $ e $1 $ .

O estado de um único qubit pode ser descrito por um vetor de coluna bidimensional de norma unitária, ou seja, a magnitude ao quadrado das suas entradas deve ser de $1 $ . Este vetor, chamado vetor de estado quântico, contém toda a informação necessária para descrever o sistema quântico de um qubit, assim como um único bit contém toda a informação necessária para descrever o estado de uma variável binária.

Qualquer vetor de coluna bidimensional de números reais ou complexos com norma $1 $ representa um possível estado quântico detido por um qubit. Assim, $\begin\ bmatrix } \alpha \\ \\ \beta \end$ bmatrix } representa um estado qubit se $\alpha $ e $\beta $ são números complexos que satisfazem $\alpha | ^2 + \beta | ^2 = 1 $ . Alguns exemplos de vetores de estado quântico válidos que representam qubits incluem

$$\begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } , \start{ bmatrix } \\ \\ 0 1 \end{ bmatrix } , \start{ bmatrix } \frac{1 } {\sqrt{2 } } \\ \\ \frac{1 } {\sqrt{2 } } \end{ bmatrix } bmatrix } } {\sqrt{2 } } \\ \\ \frac { -1 } {\sqrt{2 } } \end{ , bmatrix } \text and { }\begin{ bmatrix } \frac{1 } {\sqrt{2 } } \\ \\ \frac{i } {\sqrt{2 } } \end{ bmatrix } .$$

Os vetores de estado quântico $\begin{ bmatrix } \\ \\ 10 \end{ bmatrix } $ e $\begin{ bmatrix } \\ \\ 0 1 \end$ bmatrix } assumem um papel especial. Estes dois vetores formam uma base para o espaço vetorial que descreve o estado do qubit. Isto significa que qualquer vetor de estado quântico pode ser escrito como uma soma destes vetores de base. Especificamente, o vetor $\begin{ bmatrix } x \\ \\ y \end$ bmatrix } pode ser escrito como $x \start{ bmatrix } \\ \\ 1 0 \end{ bmatrix } + y \begin{ bmatrix } \\ \\ 0 1 \end{end{$. bmatrix } Embora qualquer rotação destes vetores sirva como uma base perfeitamente válida para o qubit, escolhemos privilegiar este, chamando-lhe a *base computacional.*

Levamos estes dois estados quânticos para corresponder aos dois estados de um bit clássico, nomeadamente $0 $ e $1. $ A convenção padrão é escolher

$0 \equiv \start bmatrix } 1 \\ \\ 0 \end{, bmatrix } \qquad 1 \equiv \begin{ bmatrix } \\ \\ 0 1 \end{ bmatrix } ,$$

embora a escolha oposta poderia igualmente ser tomada. Assim, do número infinito de possíveis vetores de estado quântico de um único qubit, apenas dois correspondem a estados de bits clássicos; todos os outros estados quânticos não.

## <a name="measuring-a-qubit"></a>Medindo um Qubit

Agora que sabemos representar um qubit, podemos ganhar alguma intuição para o que estes Estados representam, discutindo o conceito de [*medição.*](https://en.wikipedia.org/wiki/Measurement_in_quantum_mechanics) Uma medição corresponde à ideia informal de "olhar" para um qubit, que imediatamente colapsa o estado quântico para um dos dois estados clássicos $\begin{ bmatrix } \\ \\ 10 \end$ bmatrix } ou $\start bmatrix } 0 \\ \\ 1 \end{ bmatrix } $. Quando um qubit dado pelo vetor de estado quântico $\begin\ bmatrix } \alpha \\ \\ \beta \end$ bmatrix } é medido, obtemos o resultado $0 $ com probabilidade $\alpha | ^2 $ e o resultado $1 $ com probabilidade $\beta | ^2 $ . No resultado $0, $ o novo estado do qubit é $\start{ bmatrix } 10 \\ \\ \end... bmatrix } $; no resultado $1 o seu estado é $ $\begin{ bmatrix } \\ \\ 0 1 \end{ bmatrix } $. Note que estas probabilidades resumem até $1 $ devido à condição de normalização $\alpha | ^2 + \beta | ^2 = 1 $ .

As propriedades da medição também significam que o sinal geral do vetor do estado quântico é irrelevante. A negação de um vetor é equivalente a $\alpha \rightarrow -\alpha $ e $\beta \rightarrow -\beta $ . Porque a probabilidade de medir $0 $ e $1 $ depende da magnitude ao quadrado dos termos, inserir tais sinais não altera as probabilidades. Tais fases são geralmente chamadas [ `` *fases globais*''](https://en.wikipedia.org/wiki/Phase_factor) e, de um modo geral, podem ser da forma $e^{i \phi } $ em vez de apenas $\pm 1 $ .

Uma propriedade importante final da medição é que não danifica necessariamente todos os vetores do estado quântico. Se começarmos com um qubit no estado $\begin{ bmatrix } \\ \\ 10 \end, bmatrix } o que corresponde ao estado clássico $0, $ medir este estado sempre renderá o resultado $0 $ e deixará o estado quântico inalterado. Neste sentido, se tivermos apenas bits clássicos (ou seja, qubits que são ou $\begin} bmatrix }1 \\ \\ 0 \end$ bmatrix } ou $\begin} bmatrix }0 \\ \\ 1 \end{ bmatrix } $) então a medição não danifica o sistema. Isto significa que podemos replicar dados clássicos e manipulá-lo num computador quântico, tal como se poderia fazer num computador clássico. A capacidade, no entanto, de armazenar informação em ambos os Estados ao mesmo tempo é o que eleva a computação quântica para além do que é possível clássicamente e rouba ainda mais computadores quânticos da capacidade de copiar dados quânticos indiscriminadamente, ver também [o teorema de não clonagem.](https://en.wikipedia.org/wiki/No-cloning_theorem)

## <a name="visualizing-qubits-and-transformations-using-the-bloch-sphere"></a>Visualização de Qubits e Transformações usando a Esfera bloch

Qubits também podem ser retratados em $3$D usando a representação da [*esfera bloch.*](https://en.wikipedia.org/wiki/Bloch_sphere)  A esfera bloch dá uma maneira de descrever um estado quântico de um único qubit (que é um vetor complexo bidimensional) como um vetor tridimensional de valor real.  Isto é importante porque nos permite visualizar estados de um único qubit e, assim, desenvolver um raciocínio que pode ser inestimável na compreensão de estados multi-qubits (onde infelizmente a representação da esfera bloch se decompõe).  A esfera bloch pode ser visualizada da seguinte forma:

<!--- ![](.\media\bloch.svg){ width=50% } --->
![Esfera de Bloch](~/media/concepts_bloch.png)

As setas deste diagrama mostram a direção em que o vetor de estado quântico está apontando e cada transformação da seta pode ser considerada como uma rotação sobre um dos eixos cardeais.
Ao pensar numa computação quântica como uma sequência de rotações é uma intuição poderosa, é um desafio usar esta intuição para desenhar e descrever algoritmos. Q# alivia esta questão fornecendo uma linguagem para descrever tais rotações.

## <a name="single-qubit-operations"></a>Operações single-Qubit

Os computadores quânticos processam dados aplicando um conjunto universal de portões quânticos que podem imitar qualquer rotação do vetor do estado quântico.
Esta noção de universalidade é semelhante à noção de universalidade para a computação tradicional (ou seja, clássica) onde um conjunto de portão é considerado universal se cada transformação dos bits de entrada pode ser realizada usando um circuito de comprimento finito.
Na computação quântica, as transformações válidas que nos são permitidas num qubit são transformações unitárias e medição.
A *operação adjacente* ou a transposição complexa do conjugado é de importância crucial para a computação quântica porque é necessária para inverter as transformações quânticas.
Q# reflete isto fornecendo métodos para compilar automaticamente as sequências do portão para o seu adjacente, o que evita que o programador tenha de entregar códigos adjacentes em muitos casos. Um exemplo disso é mostrado abaixo:

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Adj { // Auto-generate the adjoint of the operation
    H(qubit);
}
```

Embora este seja um exemplo trivial (como a <xref:microsoft.quantum.intrinsic.h[!OP.NO-LOC(> operação é auto-adjacente), você pode ver como isso se torna inestimável para operações de qubit mais complicadas.
Para mais informações, consulte [Operações e Funções.](xref:microsoft.quantum.guide.operationsfunctions)

Há apenas quatro funções que mapeiam um pouco a um bit num computador clássico. Em contraste, há um número infinito de transformações unitárias num único qubit num computador quântico. Portanto, nenhum conjunto finito de operações quânticas primitivas, [*chamados portões,*](https://en.wikipedia.org/wiki/Quantum_logic_gate)pode exatamente replicar o conjunto infinito de transformações unitárias permitidas na computação quântica. Isto significa que, ao contrário da computação clássica, é impossível para um computador quântico implementar todos os programas quânticos possíveis exatamente usando um número finito de portões. Assim, os computadores quânticos não podem ser universais no mesmo sentido dos computadores clássicos. Como resultado, quando dizemos que um conjunto de portas é *universal* para a computação quântica, na verdade, significamos algo ligeiramente mais fraco do que queremos dizer com a computação clássica.
Para a universalidade, exigimos que um computador quântico apenas *se aproxime* de cada matriz unitária dentro de um erro finito usando uma sequência de portão de comprimento finito.
Por outras palavras, um conjunto de portões é um conjunto de portão universal se qualquer transformação unitária pode ser escrita aproximadamente como um produto de portões deste conjunto. Exigimos que para qualquer erro prescrito vinculado, existam portões $G_{1, } G_{2 } ,\ldots, G_N $ do conjunto do portão de tal forma que

$$ G_N G_{N-1 } \cdots G_2 G_1 \aprox. $$

Note que porque a convenção para a multiplicação da matriz é multiplicar da direita para a esquerda a primeira operação do portão nesta sequência, $G_N $ , é na verdade a última aplicada ao vetor de estado quântico. Mais formalmente, dizemos que tal conjunto de porta é universal se para cada tolerância de erro $\epsilon>0 $ existe $G_1,\ldots, G_N $ tal que a distância entre $G_N\ldots G_1 $ e $U é no máximo $ $\epsilon $ . Idealmente, o valor de $N $ necessário para atingir esta distância de $\epsilon deve escalar $ poli-logaritmicamente com $1/\epsilon $ .

Como é um conjunto de portão universal na prática?  O portão universal mais simples definido para portas de um único qubit consiste em apenas dois portões: o portão Hadamard $H $ e o chamado portão $T $ -gate (também conhecido como portão $\pi/8): $

$$ H = \frac{1 } {\sqrt{2 } }\start{ bmatrix } 1 & \\ \\ 1 &-1 \end{,\qquad bmatrix } T = \begin{ bmatrix } 1 & \\ \\ 0 0 & e^{i\pi/4 } \end{ bmatrix } .
$$

No entanto, por razões práticas relacionadas com a correção de erros quânticos, pode ser mais conveniente considerar um conjunto de portão maior, nomeadamente um que pode ser gerado usando $H $ e $T $ .
Podemos classificar os portões quânticos em duas categorias: portas clifford e o $ $T-gate.
Esta subdivisão é útil porque em muitos esquemas de correção de erros quânticos os chamados portões Clifford são fáceis de implementar, ou seja, exigem muito poucos recursos em termos de operações e qubits para implementar falhas tolerantes, enquanto os portões não-Clifford são bastante dispendiosos quando exigem tolerância à falha. O conjunto padrão de portas clifford single-qubit, [incluído por padrão em Q#](xref:microsoft.quantum.libraries.standard.prelude), incluem

$$ H = \frac{1 } {\sqrt{2 } }\start{ bmatrix } 1 & 1 \\ \\ &-1 \end{ bmatrix } \qquad S =\begin{ bmatrix } 1 & \\ \\ 0 0 & i \end{ bmatrix } = T^2,\qquad X = \start{ bmatrix } 0 &\\ \\ 1 & 1 \end{ bmatrix } = HT^4H, $$

$$ Y = \start bmatrix } 0 & -i \\ \\ i & 0 \end{ bmatrix } =T^2HT^4 HT^6, \qquad Z = \begin{ bmatrix }1&\\\\ 0 & -1 \end{ bmatrix } =T^4.
$$

Aqui as operações $X $ , $Y e $Z são $ $ usadas com frequência e são nomeadas [*operadoras Pauli*](https://en.wikipedia.org/wiki/Pauli_matrices) em homenagem ao seu criador Wolfgang Pauli.
Juntamente com o portão não-Clifford (o $T $ -portão), estas operações podem ser compostas para aproximar qualquer transformação unitária num único qubit.

Para obter mais informações sobre estas operações, as suas representações de esfera bloch e implementações Q#, consulte [Operações e Funções Intrínsecas](xref:microsoft.quantum.libraries.standard.prelude#intrinsic-operations-and-functions).

Como exemplo de como as transformações unitárias podem ser construídas a partir destes primitivos, as três transformações representadas nas esferas bloch acima correspondem à sequência de portão $\begin{ bmatrix } \\ \\ 10 \end\ bmatrix } \maps to HZH \start{ bmatrix } \\ \\ 1 0 \end{ bmatrix } = \start{ bmatrix } \\ \\ 0 1 \end$ bmatrix }

Embora os anteriores constituam os portões primitivos mais populares para descrever operações no nível lógico da pilha (pense no nível lógico como o nível do algoritmo quântico), é muitas vezes conveniente considerar operações menos básicas a nível algorítmico, por exemplo operações mais próximas de um nível de descrição da função. Felizmente, o Q# também tem métodos disponíveis para implementar unitários de alto nível, que por sua vez permitem a implementação de algoritmos de alto nível sem decompor explicitamente tudo até Clifford e $ $T-gates.

O mais simples tão primitivo é a única rotação qubit. Três rotações de um único qubit são tipicamente consideradas: $R_x, $ $R_y $ e $R_z $ . Para visualizar a ação da rotação $R_x(\theta)$, por exemplo, imagine apontar o polegar direito ao longo da direção do $x $ -eixo da esfera Bloch e rodar o vetor com a mão através de um ângulo de raios $\theta/2. $ Este fator confuso de $2 $ decorre do facto de que os vetores ortogonais são de $180^\circ $ separados quando traçados na esfera bloch, mas na verdade são graus de $90^\circ $ separados geometricamente. As matrizes unitárias correspondentes são:

\start{align}*&R_z(\theta) = e^{-i\theta Z/2 } = \start{{-i\theta/2 bmatrix } & } \\\\ 0 & e^{i\theta/2 } \end{ bmatrix } , \\ \\ &R_x(\theta) = e^{-i\theta X/2 = } HR_z(\theta)H = \start\ bmatrix } \cos (\theta/2) & -i\sin(\theta/2) \\ \\ -i\sin (\theta/2) & \cos(\theta/2) \end{ bmatrix } , \\ \\ &R_y(\theta) = e^{-i\theta Y/2 } = SHR_z(\theta)HS^\dagger = \start{ bmatrix } \cos (\theta/2) & -\sin(\theta/2) \\ \\ \sin(\theta/2) & \cos (\theta/2) \end{align bmatrix } *}

Assim como qualquer três rotações podem ser combinadas para realizar uma rotação arbitrária em três dimensões, pode ser visto a partir da representação da esfera bloch que qualquer matriz unitária pode ser escrita como uma sequência de três rotações também. Especificamente, para cada matriz unitária $U $ existe $\alpha,\beta,\gama,\delta $ tal que $U = e^{i \alpha } R_x(\beta)R_z(\gama)R_x(\delta)$. Assim, $R_z (\theta)$ e $H $ também formam um conjunto universal de portão, embora não seja um conjunto discreto porque $\\theta $ pode ter qualquer valor. Por esta razão, e devido a aplicações em simulação quântica, tais portões contínuos são cruciais para a computação quântica, especialmente ao nível do design do algoritmo quântico. Para conseguir a implementação de hardware tolerante a falhas, acabarão por ser compilados em sequências discretas de portão que se aproximam destas rotações.
