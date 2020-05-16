---
title: Glossário de computação quântica
description: Um glossário de termos comuns, ações e objetos usados na computação quântica.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: cbc473eb14d8afd255a7072475dc054e18b98e3e
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426710"
---
# <a name="quantum-computing-glossary"></a>Glossário de computação quântica

## <a name="adjoint"></a>Adjoint

O complexo conjugado transpõe de uma [operação.](xref:microsoft.quantum.glossary#operation) Para operações que implementem um operador [unitário,](xref:microsoft.quantum.glossary#unitary-operator) o adjoint é o inverso da operação e é indicado por um símbolo da adaga. Por exemplo, se a operação `U` representar o operador unitário $U$, então `Adjoint U` representa $U^\dagger$. Para mais informações, consulte [Adjoint](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).

## <a name="ancilla"></a>Ancilla

Um [qubit](xref:microsoft.quantum.glossary#qubit) que serve de memória temporária para um computador quântico e é atribuído e desalocado conforme necessário.  Para mais informações, consulte [Vários qubits](xref:microsoft.quantum.concepts.multiple-qubits).

## <a name="bell-state"></a>Estado do sino

Um dos quatro [estados quânticos](xref:microsoft.quantum.glossary#quantum-state) maximamente [emaranhados](xref:microsoft.quantum.glossary#entanglement) de dois qubits. Os quatro estados são definidos $\ket{\beta_{ij}} = (\mathbb{I} \otimes X^iZ^j) (\ket {00} + \ket {11} ) / \sqrt {2} $. Um estado bell também é conhecido como um [par EPR](xref:microsoft.quantum.glossary#epr-pair).

## <a name="bloch-sphere"></a>Esfera de Bloch

Uma representação gráfica de[qubit](xref:microsoft.quantum.glossary#qubit) um [estado quântico](xref:microsoft.quantum.glossary#quantum-state) único como ponto numa esfera de unidade tridimensional. Para mais informações, consulte [Visualizar Qubits e Transformações utilizando a Esfera bloch.](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere)

## <a name="callable"></a>Callable

Uma [operação](xref:microsoft.quantum.glossary#operation) ou [função](xref:microsoft.quantum.glossary#function) na língua Q#. Para mais informações, consulte [Operações e funções.](xref:microsoft.quantum.guide.operationsfunctions)

## <a name="clifford-group"></a>Grupo Clifford

O conjunto de operações que ocupam os octantes da [esfera bloch](xref:microsoft.quantum.glossary#bloch-sphere) e efeito permutações dos [operadores pauli.](xref:microsoft.quantum.glossary#pauli-operators) Estas incluem as operações [$X$](xref:microsoft.quantum.intrinsic.x), [$Y$,](xref:microsoft.quantum.intrinsic.y) [$Z$,](xref:microsoft.quantum.intrinsic.z) [$H$](xref:microsoft.quantum.intrinsic.h) e [$S$.](xref:microsoft.quantum.intrinsic.s)

## <a name="controlled"></a>Controlado

Uma [operação](xref:microsoft.quantum.glossary#operation) quântica que toma um ou mais [qubits](xref:microsoft.quantum.glossary#qubit) como facilitadores para a operação alvo. Para mais informações, consulte [operações controladas e adjoint.](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations)

## <a name="dirac-notation"></a>Notação Dirac

Uma abreviatura simbólica que simplifica a representação dos [Estados quânticos](xref:microsoft.quantum.glossary#quantum-state), também chamada de notação *de sutiã.*  A porção do *soutien* representa um vetor de linha, por exemplo $\bra{A} = \begin{bmatrix} A{_1} & A{_2} \end{bmatrix}$ e a porção do *ket* representa um vetor de coluna, $\ket{B} = \begin{bmatrix} \\ \\ B{_1} B{_2} \end{bmatrix}$. Para mais informações, consulte [A Notação Dirac](xref:microsoft.quantum.concepts.dirac).

## <a name="eigenvalue"></a>Eigenvalue

O fator pelo qual a magnitude de um [eigenvector](xref:microsoft.quantum.glossary#eigenvector) de uma determinada transformação é alterada pela aplicação da transformação.  Dada uma matriz quadrada $M$ e um eigenvector $v$, então $Mv = cv$, onde $c$ é o valor eigene pode ser um número complexo de qualquer argumento. Para mais informações, consulte conceitos de [matriz avançada.](xref:microsoft.quantum.concepts.matrix-advanced)

## <a name="eigenvector"></a>Eigenvetor

Um vetor cuja direção é inalterada por uma determinada transformação e cuja magnitude é alterada por um fator correspondente ao [eigenvalue](xref:microsoft.quantum.glossary#eigenvalue)desse vetor. Dada uma matriz quadrada $M$ e um eigenvalue $c$, então $Mv = cv$, onde $v$ é um eigenvector da matriz e pode ser um número complexo de qualquer argumento. Para mais informações, consulte conceitos de [matriz avançada.](xref:microsoft.quantum.concepts.matrix-advanced)

## <a name="entanglement"></a>Emaranhado

As partículas quânticas, como [qubits,](xref:microsoft.quantum.glossary#qubit)podem ser ligadas ou *emaranhadas* de modo a que não possam ser descritas independentemente umas das outras. Os seus resultados de medição estão correlacionados mesmo quando estão separados infinitamente para longe. O emaranhado é essencial para [medir](xref:microsoft.quantum.glossary#measurement) o [estado](xref:microsoft.quantum.glossary#quantum-state) de um qubit.  Para mais informações, consulte conceitos de [matriz avançada.](xref:microsoft.quantum.concepts.matrix-advanced)

## <a name="epr-pair"></a>Par de EPR

Um dos quatro estados quânticos maximamente [emaranhados específicos](xref:microsoft.quantum.glossary#quantum-state) de dois [qubits.](xref:microsoft.quantum.glossary#qubit) Os quatro estados são definidos $\ket{\beta_{ij}} = (\mathbb {1} \otimes X^iZ^j) (\ket {00} + \ket {11} ) / \sqrt {2} $. Um par de EPR também é conhecido como um [estado bell](xref:microsoft.quantum.glossary#bell-state)

## <a name="evolution"></a>Evolução

Como um [estado quântico](xref:microsoft.quantum.glossary#quantum-state) muda com o tempo. Para mais informações, consulte os [exponenciais da Matrix.](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials)

## <a name="function"></a>Função
Um tipo de subrotina na língua Q# que é puramente clássica (não quântica). Embora as funções sejam usadas dentro de algoritmos quânticos, não podem agir em [qubits](xref:microsoft.quantum.glossary#qubit) ou [operações](xref:microsoft.quantum.glossary#operation)de chamada . Para mais informações, consulte [Operações e funções.](xref:microsoft.quantum.guide.operationsfunctions)

## <a name="gate"></a>Portão

Um termo legado para uma [operação](xref:microsoft.quantum.glossary#operation)quântica, baseado no conceito de portas lógicas clássicas. Um [circuito quântico](xref:microsoft.quantum.glossary#quantum-circuit-diagram) é uma rede de portões (ou operações), com base no conceito semelhante de circuitos lógicos clássicos.

## <a name="global-phase"></a>Fase global

Quando dois [estados](xref:microsoft.quantum.glossary#quantum-state) são idênticos a um múltiplo de um número complexo $e^{{i\phi}$, dizem que diferem até uma fase global. Ao contrário das fases locais, as fases globais não podem ser observadas através de qualquer [mensuração](xref:microsoft.quantum.glossary#measurement). Para mais informações, consulte [o Qubit.](xref:microsoft.quantum.concepts.qubit)

## <a name="hadamard"></a>Hadamard

A operação Hadamard (também referida como o portão de Hadamard ou transformação) atua num único [qubit](xref:microsoft.quantum.glossary#qubit) e coloca-a numa [sobreposição](xref:microsoft.quantum.glossary#superposition) uniforme de $\ket {0} $ ou $\ket {1} $ se o qubit estiver inicialmente no estado $\ket {0} $. Em Q#, esta operação é aplicada pela [`H`](xref:microsoft.quantum.intrinsic.h) operação pré-definida.

## <a name="immutable"></a>Imutável

Uma variável cujo valor não pode ser alterado. Uma variável imutável em Q# é criada usando a `let` palavra-chave. Para declarar variáveis que *podem* ser alteradas, use a palavra-chave [mutável](xref:microsoft.quantum.glossary#immutable) para declarar e a `set` palavra-chave para modificar o valor. 

## <a name="measurement"></a>Medida

Uma manipulação de um [qubit](xref:microsoft.quantum.glossary#qubit) (ou conjunto de qubits) que produz o resultado de uma observação, obtendo efetivamente uma parte clássica. Para mais informações, consulte [o Qubit.](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit)

## <a name="mutable"></a>Mutável

Uma variável cujo valor pode ser alterado após a sua criação. Uma variável mutável em Q# é declarada usando a `mutable` palavra-chave e modificada usando a `set` palavra-chave. As variáveis criadas com a `let` palavra-chave são [imutáveis](xref:microsoft.quantum.glossary#immutable) e o seu valor não pode ser alterado.

## <a name="namespace"></a>Espaço de Nomes

Uma etiqueta para uma coleção de nomes relacionados (por e., [operações,](xref:microsoft.quantum.glossary#operation) [funções](xref:microsoft.quantum.glossary#function)e [tipos definidos pelo utilizador).](xref:microsoft.quantum.glossary#user-defined-type) Por exemplo, o espaço de nome [Microsoft.Quantum.A preparação](xref:microsoft.quantum.preparation) rotula todos os símbolos definidos na biblioteca padrão que ajudam na preparação dos estados iniciais.

## <a name="operation"></a>Operação

A unidade básica de execução quântica em Q#. É aproximadamente equivalente a uma função em C, C++ ou Python, ou um método estático em C# ou Java. Para mais informações, consulte [Operações e funções.](xref:microsoft.quantum.guide.operationsfunctions)

## <a name="operator-application"></a>Pedido do operador

A fazer uma operação quântica. Isto aplica tipicamente uma matriz unitária ao vetor do estado quântico atual.

## <a name="oracle"></a>Oracle

Uma subrotina que fornece informações dependentes de dados a um algoritmo quântico no tempo de execução. Tipicamente, o objetivo é fornecer uma [superposição](xref:microsoft.quantum.glossary#superposition) de saídas correspondentes a inputs que estão em superposição. Para mais informações, consulte [oRáculos.](xref:microsoft.quantum.libraries.data-structures#oracles)

## <a name="partial-application"></a>Aplicação parcial

Chamar uma [função](xref:microsoft.quantum.glossary#function) ou [operação](xref:microsoft.quantum.glossary#operation) sem todas as inputs necessárias. Isto devolve um novo [callable](xref:microsoft.quantum.glossary#callable) que só precisa que os parâmetros em falta (indicados por um sublinhado) sejam fornecidos durante uma futura aplicação. Por exemplo, dada a `MyFunc(x : int, y : int) : int {return x + y;}` função, pode aplicá-la parcialmente a uma nova função `let NewFunc = MyFunc(_, 3)` . Em seguida, pode ligar para a nova função mais tarde com o parâmetro em falta `NewFunc(2)` que devolve o valor *5*.  Para mais informações, consulte [A aplicação parcial](xref:microsoft.quantum.guide.operationsfunctions#partial-application).

## <a name="pauli-operators"></a>Operadores pauli

Um conjunto de três matrizes unitárias de 2 x 2 conhecidas como `X` as `Y` `Z` operações quânticas e quânticas. A matriz de identidade, $I$, é frequentemente incluída no conjunto também.  $I = \start{bmatrix} 1 & \\ \\ 0 0 & 1 \end{bmatrix}$, $X = \start{bmatrix} 0 & 1 \\ \\ 1 & 0 \end{bmatrix}$, $Y = \start{bmatrix} 0 & \\ \\ -i i & 0 \end{bmatrix}$, $Z = \begin{bmatrix} 1 & \\ \\ 0 0 & -1 \end{bmatrix}$.   Para mais informações, consulte [operações single-qubit](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).

## <a name="quantum-circuit-diagram"></a>Diagrama de circuito quântico

Um método para representar graficamente a sequência de [operações](xref:microsoft.quantum.glossary#operation) (ou [portões)](xref:microsoft.quantum.glossary#gate)para programas quânticos simples, por exemplo, diagrama de circuito de ![ amostra ](~/media/qpe.png) . Para mais informações, consulte [os circuitos quânticos.](xref:microsoft.quantum.concepts.circuits)

## <a name="quantum-libraries"></a>Bibliotecas quânticas

Coleções de [operações,](xref:microsoft.quantum.glossary#operation) [funções](xref:microsoft.quantum.glossary#function) e [tipos definidos pelo utilizador](xref:microsoft.quantum.glossary#user-defined-type) para a criação de programas Q#. A [biblioteca Standard](xref:microsoft.quantum.libraries.standard.intro) é instalada por padrão. Outras bibliotecas disponíveis são a [biblioteca de Química,](xref:microsoft.quantum.chemistry.concepts.intro)a [biblioteca numérica](xref:microsoft.quantum.numerics.intro) e a [biblioteca de machine learning.](xref:microsoft.quantum.machine-learning.concepts.intro)

## <a name="quantum-state"></a>Estado quântico

O estado exato de um sistema quântico isolado, a partir do qual as probabilidades de [medição](xref:microsoft.quantum.glossary#measurement) podem ser extraídas. Na computação quântica, o simulador quântico usa esta informação para simular como os qubits respondem às operações. Para mais informações, consulte [o Qubit.](xref:microsoft.quantum.concepts.qubit)

## <a name="qubit"></a>Qubit

Uma unidade básica de informação quântica, análoga a um *pouco* na computação clássica. Para mais informações, consulte [o Qubit.](xref:microsoft.quantum.concepts.qubit)

## <a name="repeat-until-success"></a>Repetir até ao sucesso

Um algoritmo quântico que probabilisticamente sucede. Após o fracasso, a rotina voltará a tentar até que tenha sido atingido um limite (ou um limite tenha sido atingido). Para mais informações, consulte [Repeat Until Success (RUS)](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop)

## <a name="standard-libraries"></a>Bibliotecas padrão

[Operações,](xref:microsoft.quantum.glossary#operation) [funções](xref:microsoft.quantum.glossary#function) e tipos [definidos pelo utilizador](xref:microsoft.quantum.glossary#user-defined-type) que são instalados juntamente com o compilador Q# durante a instalação. A implementação padrão da biblioteca é agnóstica no que diz respeito às máquinas-alvo. Para mais informações, consulte [as bibliotecas Standard.](xref:microsoft.quantum.libraries.standard.intro)

## <a name="superposition"></a>Superposição

O conceito na computação quântica de que um [qubit](xref:microsoft.quantum.glossary#qubit) é uma combinação linear de dois estados, $\ket{\0}$ e $\ket{\1}$, até que seja [medido](xref:microsoft.quantum.glossary#measurement).  Para mais informações, consulte [Understanding quantum computing](xref:microsoft.quantum.overview.understanding).

## <a name="target-machine"></a>Máquina-alvo

Um alvo de compilação que reduz um programa quântico abstrato para hardware ou simulação. Isto normalmente inclui re-writes para muitos fins, incluindo a substituição do portão, codificação para correção de erros, layout geométrico e outros. Para mais informações, consulte [simuladores quânticos e aplicações de acolhimento.](xref:microsoft.quantum.machines)

## <a name="teleportation"></a>Teletransporte

Um método de regeneração de dados, ou [o estado quântico,](xref:microsoft.quantum.glossary#quantum-state)de um [qubit](xref:microsoft.quantum.glossary#qubit) de um lugar para outro sem mover fisicamente o qubit, utilizando [o emaranhado](xref:microsoft.quantum.glossary#entanglement) e [a medição.](xref:microsoft.quantum.glossary#measurement)  Para mais informações, consulte [os circuitos quânticos](xref:microsoft.quantum.concepts.circuits) e a respetiva kata em [Quantum Katas.](xref:microsoft.quantum.overview.katas)

## <a name="tuple"></a>Rio Tuple

Uma coleção de valores separados de vírem que atua como um único valor. O *tipo* de tuple é definido pelos tipos de valores que contém. Em Q#, os tuples são [imutáveis](xref:microsoft.quantum.glossary#immutable) e podem ser aninhados, conter matrizes ou usados numa matriz. Para mais informações, consulte [os tipos Tuple](xref:microsoft.quantum.guide.types#tuple-types).

## <a name="unitary-operator"></a>Operador unitário

Um operador cujo inverso é igual ao seu [adjoint](xref:microsoft.quantum.glossary#adjoint), ou seja, $UU^{\dagger} = \id$.

## <a name="user-defined-type"></a>Tipo definido pelo utilizador

Uma coleção de tipos incorporados ou previamente definidos que podem ser referidos como uma única unidade. Para mais informações, consulte [os tipos definidos pelo Utilizador](xref:microsoft.quantum.guide.types#user-defined-types).