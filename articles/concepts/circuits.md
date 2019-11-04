---
title: Circuitos Quantum | Microsoft Docs
description: Circuitos Quantum
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 7c2afa58fd70d893529cf794ae07df480466aaec
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73210577"
---
# <a name="quantum-circuits"></a>Circuitos Quantum
Considere por um momento a transformação unitário $ \Text{CNOT} _{01}(H\otimes 1) $.
Essa sequência de portão é de importância fundamental para a computação Quantum porque ela cria um estado confusas de duas qubit de maneira máxima:

$ $ \mathrm{CNOT}_{01}(H\otimes 1) \ket{00} = \frac{1}{\sqrt{2}} \left (\ket{00} + \ket{11} \right), $ $

As operações com essa ou mais complexidade são onipresentes em algoritmos Quantum e correção de erro Quantum, portanto, deve ser um grande alívio de que há um método simples para sua visualização chamada de *diagrama de circuito Quantum*.
O diagrama de circuito para preparar esse estado de Quantum de confusas máximo é:

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/Concepts1.png)

## <a name="quantum-circuit-diagram-conventions"></a>Convenções de diagrama de circuito Quantum
Essa linguagem visual para operações Quantum pode ser mais prontamente fácil do que escrever sua matriz equivalente quando você entende as convenções para expressar um circuito Quantum.
Analisamos essas convenções abaixo.

Em um diagrama de circuito, cada linha sólida representa um qubit ou mais geralmente um registro de qubit.
Por convenção, a linha superior é o registro de qubit $0 $ e o resto é rotulado em sequência. O circuito de exemplo acima é representado como agindo em dois qubits (ou dois registros equivalentes que consistem em um qubit).
As Gates que atuam em um ou mais registros de qubit são indicadas como uma caixa.
Por exemplo, o símbolo

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_2.png)

é o portão [Hadamard](xref:microsoft.quantum.primitive.h) que atua em um registro de qubit único.

As Gates da Quantum são ordenadas em ordem cronológica com a porta mais à esquerda como a portão aplicada pela primeira vez ao qubits.
Em outras palavras, se você modelar os fios como tendo o estado Quantum, os fios trazem o estado da Quantum por meio de cada um dos Gates no diagrama da esquerda para a direita.
Isso é para dizer 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_3.png)

é a matriz unitário $CBA $.
A multiplicação de matriz obedece à Convenção oposta: a matriz mais à direita é aplicada primeiro. Em diagramas de circuito Quantum, no entanto, o portão mais à esquerda é aplicado primeiro.
Essa diferença pode, às vezes, levar à confusão. portanto, é importante observar essa diferença significativa entre a notação linear algébricas e os diagramas de circuito Quantum.

## <a name="inputs-and-outputs-of-quantum-circuits"></a>Entradas e saídas de circuitos Quantum
Todos os exemplos anteriores que tinham tido exatamente o mesmo número de fios (qubits) de entrada para uma porta Quantum como o número de cabos do portão Quantum.
A princípio, pode parecer razoável que os circuitos Quantum pudessem ter mais, ou menos, saídas do que as entradas em geral.
No entanto, isso é impossível, pois todas as operações de Quantum, salvar medida, são unitários e, portanto, reversível.
Se eles não tiverem o mesmo número de saídas que não seriam reversível e, portanto, não são unitários, o que é uma contradição.
Por esse motivo, qualquer caixa desenhada em um diagrama de circuito deve ter precisamente o mesmo número de fios inserindo-o como sendo encerrado.

Os diagramas de circuito qubit seguem convenções semelhantes para os qubit únicos.
Como um exemplo de esclarecimento, podemos definir uma operação qubit de dois unitários $B $ para ser $ (H S\otimes X) $ e expressar o circuito equivalentemente como

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_4.png)

Também podemos exibir $B $ como tendo uma ação em um único registro de duas qubit em vez de registros de 2 1-qubit, dependendo do contexto no qual o circuito é usado. Talvez a propriedade mais útil desses diagramas de circuito abstrato seja que eles permitam que algoritmos de Quantum complicados sejam descritos em um alto nível sem precisar compilá-los em Gates fundamentais.
Isso significa que você pode obter uma intuição sobre o fluxo de dados para um grande algoritmo Quantum sem a necessidade de entender todos os detalhes de como cada uma das sub-rotinas dentro do algoritmo funciona.

## <a name="controlled-gates"></a>Gates controlados
O outro constructo criado em diagramas de circuito Quantum qubit é Control.
A ação de um portão controlado de Quantum singular, denotado $ \Lambda (G) $, em que um único valor de qubit controla o aplicativo de $G $, pode ser compreendido examinando o exemplo a seguir de uma entrada de estado do produto $ \Lambda (G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket {\ psi} $.
Ou seja, a porta controlada se aplica $G $ ao registro que contém $ \psi $ If e somente se o qubit de controle usa o valor $1 $.
Em geral, descrevemos essas operações controladas em diagramas de circuito como

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_5.png)

Aqui, o círculo preto denota o bit quântico no qual o portão é controlado e uma transmissão vertical denota o unitário que é aplicado quando o qubit de controle usa o valor $1 $.
Para os casos especiais em que $G = X $ e $G = Z $ apresentamos a notação a seguir para descrever a versão controlada das Gates (Observe que a porta X controlada é a [porta do $CNOT $](xref:microsoft.quantum.primitive.cnot)):

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_6.png)

O Q # fornece métodos para gerar automaticamente a versão controlada de uma operação, o que evita que o programador tenha que codificar essas operações manualmente. Um exemplo disso é mostrado abaixo:

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a>Operador de medida
A operação restante a ser visualizada em diagramas de circuito é medida.
A medição usa um registro qubit, mede-o e gera o resultado como informações clássicas.
Uma operação de medição é denotada por um símbolo de medidor e sempre usa como entrada um registro de qubit (indicado por uma linha sólida) e gera informações clássicas (indicadas por uma linha dupla).
Especificamente, esse subcircuito é semelhante a:

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![circuito de medição](~/media/concepts_7.png)

Q # implementa um [operador de medida](xref:microsoft.quantum.primitive.measure) para essa finalidade.
Consulte a [seção sobre medições](xref:microsoft.quantum.libraries.standard.prelude#measurements) para obter mais informações.

Da mesma forma, o subcircuito

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_8.png)

fornece um portão controlado de forma clássica, em que $G $ é aplicado condicionalmente no bit de controle clássico sendo o valor de $1 $.

## <a name="teleportation-circuit-diagram"></a>Diagrama de circuito de teleportação
A [porta de transporte Quantum](xref:microsoft.quantum.techniques.puttingittogether) talvez seja o melhor algoritmo Quantum para ilustrar esses componentes.
A teleportabilidade Quantum é um método para mover dados dentro de um computador Quantum (ou até mesmo entre computadores Quantum distantes em uma rede Quantum) por meio do uso de Entanglement e medição.
Curiosamente, é realmente capaz de mover um estado Quantum, digamos o valor em um determinado qubit, de um qubit para outro, sem nem mesmo saber qual é o valor da qubit!
Isso é necessário para que o protocolo funcione de acordo com as leis da mecânica quantum.
O circuito de teleportabilidade Quantum é fornecido abaixo; também fornecemos uma versão anotada do circuito para ilustrar como ler o circuito Quantum.

<!--- ![](.\media\tp2.svg){ width=50% } --->
![](~/media/concepts_tp2.png)
