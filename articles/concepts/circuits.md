---
title: Circuitos quânticos
description: Aprenda a representar visualmente operações quânticas simples e complexas com diagramas de circuito quântico.
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
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
ms.openlocfilehash: 745f0570bf62c5d98c2896cdc893ec385abd7115
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630397"
---
# <a name="quantum-circuits"></a>Circuitos Quânticos
Considere por um momento a transformação unitária $\text { CNOT}_{01 } (H \otimes 1)$.
Esta sequência de portão é de importância fundamental para a computação quântica porque cria um estado de dois qubits maximicamente emaranhado:

$$\mathrm{CNOT}_{01 } (H \otimes 1)\ket{00 } = \frac{1 } {\sqrt{2 } } \left(\ket{00 } + \ket{11 } \right),$$

As operações com esta ou maior complexidade são ubíquas em algoritmos quânticos e correção de erros quânticos, por isso deve ser um grande alívio que exista um método simples para a sua visualização chamado *diagrama de circuito quântico.*
O diagrama do circuito para preparar este estado quântico máximo emaranhado é:

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Diagrama de circuito para um estado máximo emaranhado de dois qubits](~/media/1.svg)

## <a name="quantum-circuit-diagram-conventions"></a>Convenções de diagrama de circuito quântico
Esta linguagem visual para operações quânticas pode ser mais facilmente digerível do que escrever a sua matriz equivalente uma vez que você entende as convenções para expressar um circuito quântico.
Revemos estas convenções abaixo.

Num diagrama de circuito, cada linha sólida representa um qubit ou, mais geralmente, um registo qubit.
Por convenção, a linha de cima é o qubit register $0 $ e o restante é rotulado sequencialmente. O circuito de exemplo acima é descrito como agindo em dois qubits (ou equivalentemente dois registos constituídos por um qubit).
Os portões que atuam em um ou mais registos qubit são denotados como uma caixa.
Por exemplo, o símbolo

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Símbolo para uma operação Hadamard agindo num registo de um único qubit](~/media/2.svg)

é uma operação [Hadamard](xref:microsoft.quantum.intrinsic.h) agindo num registo de um único qubit.

Os portões quânticos são ordenados por ordem cronológica com o portão mais à esquerda, como o portão aplicado pela primeira vez aos qubits.
Por outras palavras, se imaginarmos os fios como segurando o estado quântico, os fios trazem o estado quântico através de cada um dos portões do diagrama da esquerda para a direita.
Ou seja, 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Diagrama de portões quânticos sendo aplicado da esquerda para a direita](~/media/3.svg)

é a matriz unitária $CBA $ .
A multiplicação da matriz obedece à convenção oposta: a matriz mais direita é aplicada primeiro. Nos diagramas do circuito quântico, no entanto, o portão mais à esquerda é aplicado primeiro.
Esta diferença pode, por vezes, conduzir à confusão, pelo que é importante notar esta diferença significativa entre a notação algébrica linear e os diagramas do circuito quântico.

## <a name="inputs-and-outputs-of-quantum-circuits"></a>Entradas e saídas de circuitos quânticos
Todos os exemplos anteriores dados tiveram precisamente o mesmo número de fios (qubits) para um portão quântico que o número de fios fora do portão quântico.
Pode parecer razoável que os circuitos quânticos possam ter mais, ou menos, saídas do que as entradas em geral.
Isto é impossível, no entanto, porque todas as operações quânticas, exceto a medição, são unitárias e, portanto, reversíveis.
Se não tivessem o mesmo número de saídas que os inputs, não seriam reversíveis e, portanto, não unitários, o que constitui uma contradição.
Por esta razão, qualquer caixa desenhada num diagrama de circuito deve ter precisamente o mesmo número de fios que a entram na saída.

Os diagramas de circuitos multi-qubit seguem convenções semelhantes às de um único qubit.
Como exemplo esclarecedor, podemos definir uma operação unitária de dois qubits $B $ ser $(H S \otimes X)$ e expressar o circuito de forma equivalente a

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Diagrama de circuito de uma operação unitária de dois qubits](~/media/4.svg)

Também podemos considerar $B $ ter uma ação num único registo de dois qubits em vez de dois registos de um qubit, dependendo do contexto em que o circuito é utilizado. Talvez a propriedade mais útil de tais diagramas de circuito abstrato é que permitem que algoritmos quânticos complicados sejam descritos a um nível elevado sem ter que compilá-los até portões fundamentais.
Isto significa que você pode obter uma intuição sobre o fluxo de dados para um grande algoritmo quântico sem precisar de entender todos os detalhes de como cada um dos subrotinas dentro do algoritmo funciona.

## <a name="controlled-gates"></a>Portões controlados
A outra construção que é incorporada em diagramas de circuito quântico multi-qubit é o controlo.
A ação de um portão quântico controlado, denotados $\Lambda(G)$, onde o valor de um único qubit controla a aplicação de $ $G, pode ser entendido o seguinte exemplo de uma entrada do estado do produto $\Lambda(G) (\alpha \ket{0 } + \beta \ket{1 } ) \ket { \psi = } \alfa \ket{0\ket } { \\ \0\\\ket } \1 } \ket { }
Ou seja, o portão controlado aplica-se $G $ ao registo que contém $\psi se e $ somente se o qubit de controlo levar o valor $1 $ .
Em geral, descrevemos tais operações controladas em diagramas de circuitos como

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Diagrama de circuito de um portão controlado por singly](~/media/5.svg)

Aqui o círculo preto denota a bit quântica sobre a qual o portão é controlado e um fio vertical denota o unitário que é aplicado quando o qubit de controlo leva o valor $1 $ .
Para os casos especiais em que $G=X $ e $G=Z $ introduzimos a seguinte notação para descrever a versão controlada dos portões (note que o portão controlado-X é o [ $ portão $CNOT):](xref:microsoft.quantum.intrinsic.cnot)

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Diagrama de circuito para casos especiais de portões controlados](~/media/6.svg)

Q# fornece métodos para gerar automaticamente a versão controlada de uma operação, o que evita que o programador tenha de codificar estas operações. Um exemplo disso é mostrado abaixo:

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a>Operador de medição
A restante operação para visualizar em diagramas de circuitos é a medição.
A medição toma um registo qubit, mede-o e produz o resultado como informação clássica.
Uma operação de medição é denotada por um símbolo do medidor e toma sempre como entrada um registo qubit (denotado por uma linha sólida) e produz informações clássicas (denotadas por uma linha dupla).
Especificamente, tal subcircito parece:

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Símbolo que representa uma operação de medição](~/media/7.svg)

Q# implementa um [operador de medida](xref:microsoft.quantum.intrinsic.measure) para o efeito.
Consulte a [secção de medições](xref:microsoft.quantum.libraries.standard.prelude#measurements) para obter mais informações.

Da mesma forma, o subcircito

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Diagrama de circuito que representa uma operação controlada](~/media/8.svg)

dá um portão controlado clássicamente, onde $G $ é aplicado condicionado na bit de controlo clássica que é de valor $1 $ .

## <a name="teleportation-circuit-diagram"></a>Diagrama do circuito de teletransporte
O teletransporte quântico é talvez o melhor algoritmo quântico para ilustrar estes componentes.
Pode aprender prática com o teletransporte [Quantum Kata](xref:microsoft.quantum.overview.katas) correspondente é um método para mover dados dentro de um computador quântico (ou mesmo entre computadores quânticos distantes numa rede quântica) através da utilização de emaranhamento e medição.
Curiosamente, é realmente capaz de mover um estado quântico, digamos o valor num dado qubit, de um qubit para outro, sem sequer saber qual é o valor do qubit!
Isto é necessário para que o protocolo funcione de acordo com as leis da mecânica quântica.
O circuito de teletransporte quântico é dado abaixo; também fornecemos uma versão anotada do circuito para ilustrar como ler o circuito quântico.

<!--- ![](.\media\tp2.svg){ width=50% } --->
![Circuito de teletransporte quântico](~/media/tp2.svg)
