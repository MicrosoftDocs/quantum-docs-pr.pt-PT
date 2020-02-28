---
title: Circuitos quânticos
description: Aprenda a representar visualmente operações quânticas simples e complexas com diagramas de circuito quântico.
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 8ba4648f1837065d15957a01ab4ca8dd2d490a42
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77905153"
---
# <a name="quantum-circuits"></a>Circuitos Quânticos
Considere por um momento a transformação unitária $\text{ CNOT}_{01}(H\otimes 1)$.
Esta sequência de portão é de importância fundamental para a computação quântica porque cria um estado de dois qubits maximamente emaranhado:

$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left (\ket{00} + \ket{11} \right),$$$$

As operações com esta ou maior complexidade são ubíquas em algoritmos quânticos e correção de erros quânticos, pelo que deve ser um grande alívio que existe um método simples para a sua visualização chamado diagrama de *circuito quântico.*
O diagrama do circuito para preparar este estado quântico maximamente emaranhado é:

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
Diagrama do Circuito ![para um estado de dois qubits maximamente emaranhado](~/media/Concepts1.png)

## <a name="quantum-circuit-diagram-conventions"></a>Convenções de diagramas de circuito quântico
Esta linguagem visual para operações quânticas pode ser mais facilmente digerível do que escrever a sua matriz equivalente uma vez que você entenda as convenções para expressar um circuito quântico.
Revemos estas convenções abaixo.

Num diagrama de circuito, cada linha sólida retrata um qubit ou, mais geralmente, um registo qubit.
Por convenção, a linha de cima é o registo qubit $0$ e o restante é rotulado sequencialmente. O circuito de exemplo acima é descrito como agindo em dois qubits (ou equivalentemente dois registos constituídos por um qubit).
Os portões que atuam num ou mais registos qubit são denotados como uma caixa.
Por exemplo, o símbolo

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Símbolo para uma operação Hadamard agindo num registo de um único qubit](~/media/concepts_2.png)

é uma operação [Hadamard](xref:microsoft.quantum.intrinsic.h) agindo num registo de qubit único.

Os portões quânticos são encomendados por ordem cronológica com o portão mais à esquerda, uma vez que o portão se aplicava primeiro aos qubits.
Por outras palavras, se imaginarmos os fios como segurando o estado quântico, os fios trazem o estado quântico através de cada um dos portões do diagrama da esquerda para a direita.
Isto é, 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![Diagrama de portões quânticos a ser aplicado](~/media/concepts_3.png) da esquerda para a direita

é a matriz unitária $CBA$.
A multiplicação da matriz obedece à convenção oposta: a matriz mais correta é aplicada primeiro. Nos diagramas de circuitos quânticos, no entanto, o portão mais à esquerda é aplicado primeiro.
Esta diferença pode, por vezes, levar à confusão, pelo que é importante notar esta diferença significativa entre a notação algébrica linear e os diagramas de circuitos quânticos.

## <a name="inputs-and-outputs-of-quantum-circuits"></a>Inputs e saídas de circuitos quânticos
Todos os exemplos anteriores dados tiveram precisamente o mesmo número de fios (qubits) de entrada para um portão quântico como o número de fios fora do portão quântico.
Pode parecer razoável que os circuitos quânticos possam ter mais, ou menos, saídas do que inputs em geral.
Isto é impossível, no entanto, porque todas as operações quânticas, exceto a medição, são unitárias e, portanto, reversíveis.
Se não tivessem o mesmo número de saídas que os inputs, não seriam reversíveis e, portanto, não unitários, o que constitui uma contradição.
Por esta razão, qualquer caixa desenhada num diagrama de circuito deve ter precisamente o mesmo número de fios que a entram como saída.

Os diagramas de circuitos multiqubits seguem convenções semelhantes às de um qubit único.
Como exemplo esclarecedor, podemos definir uma operação unitária de dois qubits $B$ para ser $(H S\otimes X)$ e expressar o circuito de forma equivalente como

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
Diagrama do Circuito ![de uma operação unitária de dois qubits](~/media/concepts_4.png)

Também podemos ver $B$ como tendo uma ação num único registo de dois qubits em vez de dois registos de um qubit dependendo do contexto em que o circuito é usado. Talvez a propriedade mais útil de tais diagramas de circuitos abstratos é que eles permitem que algoritmos quânticos complicados sejam descritos a um nível elevado sem ter que compilá-los até portões fundamentais.
Isto significa que você pode obter uma intuição sobre o fluxo de dados para um grande algoritmo quântico sem precisar entender todos os detalhes de como cada uma das subrotinas dentro do algoritmo funciona.

## <a name="controlled-gates"></a>Portões controlados
A outra construção que é incorporada em diagramas de circuito quântico multiqubit é o controlo.
A ação de um portão controlado por singly quântico, denotada $\Lambda(G)$, onde um único qubit controla a aplicação de $G$, pode ser entendida olhando para o exemplo seguinte de uma entrada do estado do produto $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket {\psi} = \ket{0} \ket {\psi+{1} \\
Ou seja, o portão controlado aplica-se $G$ ao registo que contém $\psi$ se e apenas se o qubit de controlo levar o valor $1$.
Em geral, descrevemos tais operações controladas em diagramas de circuitos como

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
Diagrama do circuito ![de um portão controlado](~/media/concepts_5.png)

Aqui o círculo negro denota a bit quântica em que o portão é controlado e um fio vertical denota o unitário que é aplicado quando o qubit de controlo leva o valor $1$.
Para os casos especiais em que $G=X$ e $G=Z$ introduzimos a seguinte notação para descrever a versão controlada dos portões (note que o portão controlado-X é o [portão $CNOT$](xref:microsoft.quantum.intrinsic.cnot)):

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
Diagrama do Circuito ![para casos especiais de portões controlados](~/media/concepts_6.png)

Q# fornece métodos para gerar automaticamente a versão controlada de uma operação, que evita que o programador tenha de codificar estas operações manualmente. Um exemplo disto é mostrado abaixo:

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a>Operador de medição
A operação restante para visualizar em diagramas de circuitos é a medição.
A medição tem um registo qubit, mede-o e produz o resultado como informação clássica.
Uma operação de medição é denotada por um símbolo de contador e toma sempre como entrada um registo qubit (denotado por uma linha sólida) e produz informações clássicas (denotadas por uma linha dupla).
Especificamente, tal subcircuito parece:

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
Símbolo ![que representa uma operação de medição](~/media/concepts_7.png)

Q# implementa um operador de [medida](xref:microsoft.quantum.intrinsic.measure) para o efeito.
Consulte a [secção sobre medições](xref:microsoft.quantum.libraries.standard.prelude#measurements) para obter mais informações.

Da mesma forma, o subcircuito

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
Diagrama do Circuito ![que representa uma operação controlada](~/media/concepts_8.png)

dá um portão controlado clássicamente, onde $G$ é aplicado condicionado na broca de controlo clássico sendo $1$.

## <a name="teleportation-circuit-diagram"></a>Diagrama do circuito de teletransporte
[A teleportação quântica](xref:microsoft.quantum.techniques.puttingittogether) é talvez o melhor algoritmo quântico para ilustrar estes componentes.
A teleportação quântica é um método para mover dados dentro de um computador quântico (ou mesmo entre computadores quânticos distantes numa rede quântica) através do uso do emaranhado e da medição.
Curiosamente, é realmente capaz de mover um estado quântico, digamos, o valor num determinado qubit, de um qubit para outro, sem sequer saber qual é o valor do qubit!
Isto é necessário para que o protocolo funcione de acordo com as leis da Mecânica Quântica.
O circuito de teletransporte quântico é dado abaixo; também fornecemos uma versão anotada do circuito para ilustrar como ler o circuito quântico.

<!--- ![](.\media\tp2.svg){ width=50% } --->
![circuito de teletransporte quântica](~/media/concepts_tp2.png)
