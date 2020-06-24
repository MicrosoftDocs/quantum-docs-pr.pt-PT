---
title: Glossário de computação quântica
description: Um glossário de termos, ações e objetos comuns usados na computação quântica.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
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
ms.openlocfilehash: ba4d171d84d808f082b919dcc6156d9c65df7c05
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275364"
---
# <a name="quantum-computing-glossary"></a>Glossário de computação quântica

## <a name="adjoint"></a>Adjacente

O complexo conjugado transpõe de uma [operação.](xref:microsoft.quantum.glossary#operation) Para as operações que implementam um operador [unitário,](xref:microsoft.quantum.glossary#unitary-operator) o adjacente é o inverso da operação e é indicado por um símbolo da adaga. Por exemplo, se a operação `U` representar o operador unitário $ $U, representa `Adjoint U` $U^\dagger $ . Para mais informações, consulte [Adjacente.](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations)

## <a name="ancilla"></a>Ancilla

Um [qubit](xref:microsoft.quantum.glossary#qubit) que serve de memória temporária para um computador quântico e é atribuído e desatribuido conforme necessário.  Para obter mais informações, consulte [Múltiplos qubits.](xref:microsoft.quantum.concepts.multiple-qubits)

## <a name="bell-state"></a>Estado do sino

Um dos quatro [estados quânticos](xref:microsoft.quantum.glossary#quantum-state) maximicamente [emaranhados](xref:microsoft.quantum.glossary#entanglement) de dois qubits. Os quatro estados são definidos $\ket { \beta_{ij } } = (\mathbb{I } \otimes X^iZ^j) (\ket{00 } + \ket{11) } / \sqrt{2 } $. Um estado bell também é conhecido como um [par de EPR](xref:microsoft.quantum.glossary#epr-pair).

## <a name="bloch-sphere"></a>Esfera de Bloch

Uma representação gráfica de um [único estado qubit qubit qubit quádrico](xref:microsoft.quantum.glossary#quantum-state) como um ponto numa esfera de unidade tridimensional.[qubit](xref:microsoft.quantum.glossary#qubit) Para obter mais informações, consulte [a visualização de Qubits e Transformações utilizando a Esfera bloch.](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere)

## <a name="callable"></a>Callable

Uma [operação](xref:microsoft.quantum.glossary#operation) ou [função](xref:microsoft.quantum.glossary#function) no idioma Q#. Para mais informações, consulte [Operações e funções.](xref:microsoft.quantum.guide.operationsfunctions)

## <a name="clifford-group"></a>Grupo Clifford

O conjunto de operações que ocupam os octantes da [esfera bloch](xref:microsoft.quantum.glossary#bloch-sphere) e efeitos permutações dos [operadores Pauli.](xref:microsoft.quantum.glossary#pauli-operators) Estes incluem as operações [ $ $X,](xref:microsoft.quantum.intrinsic.x) [ $ ](xref:microsoft.quantum.intrinsic.y) [ $ ](xref:microsoft.quantum.intrinsic.h) [ $ ](xref:microsoft.quantum.intrinsic.z)$Y, $Z, [ $ ](xref:microsoft.quantum.intrinsic.s)$H e $S.

## <a name="controlled"></a>Controlado

Uma [operação](xref:microsoft.quantum.glossary#operation) quântica que leva um ou mais [qubits](xref:microsoft.quantum.glossary#qubit) como facilitadores para a operação alvo. Para obter mais informações, consulte [operações controladas e adjacentes.](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations)

## <a name="dirac-notation"></a>Notação dirac

Uma abreviatura simbólica que simplifica a representação dos [Estados quânticos,](xref:microsoft.quantum.glossary#quantum-state)também chamada de notação *bra-ket.*  A parte *do soutien* representa um vetor de linha, por exemplo $\bra{A } = \start{A{_1 bmatrix } & } A{_2 } \end$ bmatrix } e a porção *de ket* representa um vetor de coluna, $\ket{B } = \begin{_1 bmatrix } } \\ \\ B{_2 } \end{ bmatrix } $. Para mais informações, consulte [a Notação De Dirac.](xref:microsoft.quantum.concepts.dirac)

## <a name="eigenvalue"></a>Rio Eigenvalue

O fator pelo qual a magnitude de um [eigenvector](xref:microsoft.quantum.glossary#eigenvector) de uma determinada transformação é alterada pela aplicação da transformação.  Dada uma matriz quadrada $M $ e um $v de eigenvector, $ então $Mv = cv , onde $c $ é o $ eigenvalue e pode ser um número complexo de qualquer argumento. Para mais informações, consulte [conceitos de matriz avançada.](xref:microsoft.quantum.concepts.matrix-advanced)

## <a name="eigenvector"></a>Eigenvector

Um vetor cuja direção é inalterada por uma determinada transformação e cuja magnitude é alterada por um fator correspondente ao [eigenvalue](xref:microsoft.quantum.glossary#eigenvalue)desse vetor. Dada uma matriz quadrada $M $ e um $c de eigenvalue, $ então $Mv = cv , onde $ $v é um $ eigenvector da matriz e pode ser um número complexo de qualquer argumento. Para mais informações, consulte [conceitos de matriz avançada.](xref:microsoft.quantum.concepts.matrix-advanced)

## <a name="entanglement"></a>Entrelaçamento

Partículas quânticas, como [qubits,](xref:microsoft.quantum.glossary#qubit)podem ser ligadas ou *emaranhadas* de modo a que não possam ser descritas independentemente umas das outras. Os seus resultados de medição estão correlacionados mesmo quando estão separados infinitamente longe. O emaranhado é essencial para [medir](xref:microsoft.quantum.glossary#measurement) o [estado](xref:microsoft.quantum.glossary#quantum-state) de um qubit.  Para mais informações, consulte [conceitos de matriz avançada.](xref:microsoft.quantum.concepts.matrix-advanced)

## <a name="epr-pair"></a>Par EPR

Um dos quatro [estados quânticos](xref:microsoft.quantum.glossary#quantum-state) maximicamente emaranhados de dois [qubits.](xref:microsoft.quantum.glossary#qubit) Os quatro estados são definidos $\ket { \beta_{ij } } = (\mathbb{1 } \otimes X^iZ^j) (\ket{00 } + \ket{11) } / \sqrt{2 } $. Um par de EPR também é conhecido como um [estado bell](xref:microsoft.quantum.glossary#bell-state)

## <a name="evolution"></a>Evolução

Como um [estado quântico](xref:microsoft.quantum.glossary#quantum-state) muda com o tempo. Para obter mais informações, consulte [os exponencial da Matrix.](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials)

## <a name="function"></a>Função
Um tipo de subrotina na língua Q# que é puramente clássica (não quântica). Embora as funções sejam utilizadas dentro de algoritmos quânticos, não podem agir em [qubits](xref:microsoft.quantum.glossary#qubit) ou [operações](xref:microsoft.quantum.glossary#operation)de chamada . Para mais informações, consulte [Operações e funções.](xref:microsoft.quantum.guide.operationsfunctions)

## <a name="gate"></a>Portão

Um termo legado para uma [operação](xref:microsoft.quantum.glossary#operation)quântica, baseado no conceito de portas lógicas clássicas. Um [circuito quântico](xref:microsoft.quantum.glossary#quantum-circuit-diagram) é uma rede de portões (ou operações), baseado no conceito semelhante de circuitos lógicos clássicos.

## <a name="global-phase"></a>Fase global

Quando dois estados são [idênticos](xref:microsoft.quantum.glossary#quantum-state) até um múltiplo de um número complexo $e^{i \phi } $, dizem que diferem até uma fase global. Ao contrário das fases locais, as fases globais não podem ser observadas através de qualquer [medição](xref:microsoft.quantum.glossary#measurement). Para mais informações, consulte [o Qubit.](xref:microsoft.quantum.concepts.qubit)

## <a name="hadamard"></a>Hadamard

A operação Hadamard (também referida como o portão Hadamard ou transformação) atua num único [qubit](xref:microsoft.quantum.glossary#qubit) e coloca-a numa [superposição](xref:microsoft.quantum.glossary#superposition) uniforme de $\ket{0$ } ou $\ket{1 } $ se o qubit estiver inicialmente no estado $\ket{0$ } Em Q#, esta operação é aplicada pela [`H`](xref:microsoft.quantum.intrinsic.h) operação pré-definida.

## <a name="immutable"></a>Imutável

Uma variável cujo valor não pode ser alterado. Uma variável imutável em Q# é criada usando a `let` palavra-chave. Para declarar variáveis que *podem* ser alteradas, use a palavra-chave [mutável](xref:microsoft.quantum.glossary#immutable) para declarar e a `set` palavra-chave para modificar o valor. 

## <a name="measurement"></a>Medida

Uma manipulação de um [qubit](xref:microsoft.quantum.glossary#qubit) (ou conjunto de qubits) que produz o resultado de uma observação, obtendo efetivamente um pouco clássico. Para mais informações, consulte [o Qubit.](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit)

## <a name="mutable"></a>Mutável

Uma variável cujo valor pode ser alterado após a sua criação. Uma variável mutável em Q# é declarada usando a `mutable` palavra-chave e modificada usando a `set` palavra-chave. As variáveis criadas com a `let` palavra-chave são [imutáveis](xref:microsoft.quantum.glossary#immutable) e o seu valor não pode ser alterado.

## <a name="namespace"></a>Espaço de Nomes

Uma etiqueta para uma coleção de nomes relacionados (isto é, [operações,](xref:microsoft.quantum.glossary#operation) [funções](xref:microsoft.quantum.glossary#function)e [tipos definidos pelo utilizador).](xref:microsoft.quantum.glossary#user-defined-type) Por exemplo, o espaço de nome [Microsoft.Quantum.Preparation](xref:microsoft.quantum.preparation) rotula todos os símbolos definidos na biblioteca padrão que ajudam na preparação dos estados iniciais.

## <a name="operation"></a>Operação

A unidade básica de execução quântica em Q#. É aproximadamente equivalente a uma função em C, C++ ou Python, ou um método estático em C# ou Java. Para mais informações, consulte [Operações e funções.](xref:microsoft.quantum.guide.operationsfunctions)

## <a name="operator-application"></a>Aplicação do operador

A fazer uma operação quântica. Isto aplica tipicamente uma matriz unitária ao vetor de estado quântico atual.

## <a name="oracle"></a>Oracle

Uma sub-rotina que fornece informações dependentes de dados a um algoritmo quântico em tempo de execução. Normalmente, o objetivo é fornecer uma [superposição](xref:microsoft.quantum.glossary#superposition) de saídas correspondentes a entradas que estão em superposição. Para mais informações, consulte [o Oráculos.](xref:microsoft.quantum.libraries.data-structures#oracles)

## <a name="partial-application"></a>Aplicação parcial

Convocar uma [função](xref:microsoft.quantum.glossary#function) ou [funcionamento](xref:microsoft.quantum.glossary#operation) sem todas as entradas necessárias. Isto devolve uma nova [chamada](xref:microsoft.quantum.glossary#callable) que só necessita dos parâmetros em falta (indicados por um sublinhado) a serem fornecidos durante uma futura aplicação. Por exemplo, dada a função `MyFunc(x : int, y : int) : int {return x + y;}` pode aplicá-la parcialmente a uma nova função `let NewFunc = MyFunc(_, 3)` . Em seguida, pode ligar para a nova função mais tarde com o parâmetro em falta `NewFunc(2)` que devolve o valor *5*.  Para mais informações, consulte [aplicação parcial.](xref:microsoft.quantum.guide.operationsfunctions#partial-application)

## <a name="pauli-operators"></a>Operadores Pauli

Um conjunto de três matrizes unitárias de 2 x 2 conhecidas como `X` `Y` `Z` operações quânticas. A matriz identitária, $ $I, também está incluída no conjunto.  $I = \{ bmatrix } 1 & 0 \\ \\ 0 & 1 \end{ bmatrix } $, $X = \{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } $, $Y = \start{ bmatrix } 0 & -i \\ \\ & 0 bmatrix } \end, $Z = \start{ bmatrix } 1 & \\ \\ 0 0 & -1 \end bmatrix } {$.   Para obter mais informações, consulte [as operações Single-qubit](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).

## <a name="quantum-circuit-diagram"></a>Diagrama do circuito quântico

Um método para representar graficamente a sequência de [operações](xref:microsoft.quantum.glossary#operation) (ou [portões)](xref:microsoft.quantum.glossary#gate)para programas quânticos simples, por exemplo 

![Diagrama do circuito da amostra](~/media/qpe.png). 

Para mais informações, consulte [os circuitos quânticos.](xref:microsoft.quantum.concepts.circuits)

## <a name="quantum-libraries"></a>Bibliotecas quânticas

Recolhas de [operações,](xref:microsoft.quantum.glossary#operation) [funções](xref:microsoft.quantum.glossary#function) e [tipos definidos](xref:microsoft.quantum.glossary#user-defined-type) pelo utilizador para a criação de programas Q#. A [biblioteca Standard](xref:microsoft.quantum.libraries.standard.intro) é instalada por defeito. Outras bibliotecas disponíveis são a [biblioteca de Química,](xref:microsoft.quantum.chemistry.concepts.intro)a [biblioteca numérica](xref:microsoft.quantum.numerics.intro) e a [biblioteca machine learning.](xref:microsoft.quantum.machine-learning.concepts.intro)

## <a name="quantum-state"></a>Estado quântico

O estado exato de um sistema quântico isolado, a partir do qual as probabilidades de [medição](xref:microsoft.quantum.glossary#measurement) podem ser extraídas. Na computação quântica, o simulador quântico utiliza esta informação para simular como os qubits respondem às operações. Para mais informações, consulte [o Qubit.](xref:microsoft.quantum.concepts.qubit)

## <a name="qubit"></a>Qubit

Uma unidade básica de informação quântica, análoga a um *pouco* na computação clássica. Para mais informações, consulte [o Qubit.](xref:microsoft.quantum.concepts.qubit)

## <a name="repeat-until-success"></a>Repetição até ao sucesso

Um algoritmo quântico que probabilisticamente tem sucesso. Após o fracasso, a rotina tentará novamente até que tenha sido alcançado um limite(ou um limite). Para mais informações, consulte [Repeat Until Success (RUS)](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop)

## <a name="standard-libraries"></a>Bibliotecas padrão

[Operações](xref:microsoft.quantum.glossary#operation), [funções](xref:microsoft.quantum.glossary#function) e [tipos definidos pelo utilizador](xref:microsoft.quantum.glossary#user-defined-type) que são instalados juntamente com o compilador Q# durante a instalação. A implementação padrão da biblioteca é agnóstica no que diz respeito às máquinas-alvo. Para mais informações, consulte [as bibliotecas Standard.](xref:microsoft.quantum.libraries.standard.intro)

## <a name="superposition"></a>Superposição

O conceito na computação quântica de que um [qubit](xref:microsoft.quantum.glossary#qubit) é uma combinação linear de dois estados, $\ket{0$ } e $\ket{1 } $, até que seja [medido](xref:microsoft.quantum.glossary#measurement).  Para obter mais informações, consulte [compreensão da computação quântica.](xref:microsoft.quantum.overview.understanding)

## <a name="target-machine"></a>Máquina-alvo

Um alvo de compilação que reduz um programa quântico abstrato para hardware ou simulação. Isto normalmente inclui reescrever para muitos fins, incluindo a substituição do portão, codificação para correção de erros, layout geométrico e outros. Para obter mais informações, consulte [simuladores quânticos e aplicações de anfitrião.](xref:microsoft.quantum.machines)

## <a name="teleportation"></a>Teletransporte

Um método para regenerar dados, ou o [estado quântico,](xref:microsoft.quantum.glossary#quantum-state)de um [qubit](xref:microsoft.quantum.glossary#qubit) de um lugar para outro sem mover fisicamente o qubit, utilizando [o emaranhado](xref:microsoft.quantum.glossary#entanglement) e [a medição](xref:microsoft.quantum.glossary#measurement).  Para mais informações, consulte os [circuitos quânticos](xref:microsoft.quantum.concepts.circuits) e as respetivas kata na [Quantum Katas.](xref:microsoft.quantum.overview.katas)

## <a name="tuple"></a>Rio Tuple

Uma coleção de valores separados por vírgula que funciona como um único valor. O *tipo* de tuple é definido pelos tipos de valores que contém. Em Q#, os tuples são [imutáveis](xref:microsoft.quantum.glossary#immutable) e podem ser aninhados, conter matrizes ou usados numa matriz. Para obter mais informações, consulte [os tipos Tuple.](xref:microsoft.quantum.guide.types#tuple-types)

## <a name="unitary-operator"></a>Operador unitário

Um operador cujo inverso seja igual ao seu [adjacente,](xref:microsoft.quantum.glossary#adjoint)ou seja, $UU^{\dagger } = \id $ .

## <a name="user-defined-type"></a>Tipo definido pelo utilizador

Uma coleção de tipos incorporados ou previamente definidos que podem ser referidos como uma única unidade. Para obter mais informações, consulte [os tipos definidos pelo Utilizador.](xref:microsoft.quantum.guide.types#user-defined-types)