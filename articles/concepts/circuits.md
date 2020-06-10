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
# <a name="quantum-circuits"></a><span data-ttu-id="f780d-103">Circuitos Quânticos</span><span class="sxs-lookup"><span data-stu-id="f780d-103">Quantum Circuits</span></span>
<span data-ttu-id="f780d-104">Considere por um momento a transformação unitária $\text { CNOT}_{01 } (H \otimes 1)$.</span><span class="sxs-lookup"><span data-stu-id="f780d-104">Consider for a moment the unitary transformation $\text{ CNOT}_{01}(H\otimes 1)$.</span></span>
<span data-ttu-id="f780d-105">Esta sequência de portão é de importância fundamental para a computação quântica porque cria um estado de dois qubits maximicamente emaranhado:</span><span class="sxs-lookup"><span data-stu-id="f780d-105">This gate sequence is of fundamental significance to quantum computing because it creates a maximally entangled two-qubit state:</span></span>

<span data-ttu-id="f780d-106">$$\mathrm{CNOT}_{01 } (H \otimes 1)\ket{00 } = \frac{1 } {\sqrt{2 } } \left(\ket{00 } + \ket{11 } \right),$$</span><span class="sxs-lookup"><span data-stu-id="f780d-106">$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right),$$</span></span>

<span data-ttu-id="f780d-107">As operações com esta ou maior complexidade são ubíquas em algoritmos quânticos e correção de erros quânticos, por isso deve ser um grande alívio que exista um método simples para a sua visualização chamado *diagrama de circuito quântico.*</span><span class="sxs-lookup"><span data-stu-id="f780d-107">Operations with this or greater complexity are ubiquitous in quantum algorithms and quantum error correction, so it should come as a great relief that there is a simple method for their visualization called a *quantum circuit diagram*.</span></span>
<span data-ttu-id="f780d-108">O diagrama do circuito para preparar este estado quântico máximo emaranhado é:</span><span class="sxs-lookup"><span data-stu-id="f780d-108">The circuit diagram for preparing this maximally entangled quantum state is:</span></span>

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="f780d-109">![Diagrama de circuito para um estado máximo emaranhado de dois qubits](~/media/1.svg)</span><span class="sxs-lookup"><span data-stu-id="f780d-109">![Circuit diagram for a maximally entangled two-qubit state](~/media/1.svg)</span></span>

## <a name="quantum-circuit-diagram-conventions"></a><span data-ttu-id="f780d-110">Convenções de diagrama de circuito quântico</span><span class="sxs-lookup"><span data-stu-id="f780d-110">Quantum circuit diagram conventions</span></span>
<span data-ttu-id="f780d-111">Esta linguagem visual para operações quânticas pode ser mais facilmente digerível do que escrever a sua matriz equivalente uma vez que você entende as convenções para expressar um circuito quântico.</span><span class="sxs-lookup"><span data-stu-id="f780d-111">This visual language for quantum operations can be more readily digestible than writing down its equivalent matrix once you understand the conventions for expressing a quantum circuit.</span></span>
<span data-ttu-id="f780d-112">Revemos estas convenções abaixo.</span><span class="sxs-lookup"><span data-stu-id="f780d-112">We review these conventions below.</span></span>

<span data-ttu-id="f780d-113">Num diagrama de circuito, cada linha sólida representa um qubit ou, mais geralmente, um registo qubit.</span><span class="sxs-lookup"><span data-stu-id="f780d-113">In a circuit diagram, each solid line depicts a qubit or more generally a qubit register.</span></span>
<span data-ttu-id="f780d-114">Por convenção, a linha de cima é o qubit register $0 $ e o restante é rotulado sequencialmente.</span><span class="sxs-lookup"><span data-stu-id="f780d-114">By convention, the top line is qubit register $0$ and the remainder are labeled sequentially.</span></span> <span data-ttu-id="f780d-115">O circuito de exemplo acima é descrito como agindo em dois qubits (ou equivalentemente dois registos constituídos por um qubit).</span><span class="sxs-lookup"><span data-stu-id="f780d-115">The above example circuit is depicted as acting on two qubits (or equivalently two registers consisting of one qubit).</span></span>
<span data-ttu-id="f780d-116">Os portões que atuam em um ou mais registos qubit são denotados como uma caixa.</span><span class="sxs-lookup"><span data-stu-id="f780d-116">Gates acting on one or more qubit registers are denoted as a box.</span></span>
<span data-ttu-id="f780d-117">Por exemplo, o símbolo</span><span class="sxs-lookup"><span data-stu-id="f780d-117">For example, the symbol</span></span>

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="f780d-118">![Símbolo para uma operação Hadamard agindo num registo de um único qubit](~/media/2.svg)</span><span class="sxs-lookup"><span data-stu-id="f780d-118">![Symbol for a Hadamard operation acting on a single-qubit register](~/media/2.svg)</span></span>

<span data-ttu-id="f780d-119">é uma operação [Hadamard](xref:microsoft.quantum.intrinsic.h) agindo num registo de um único qubit.</span><span class="sxs-lookup"><span data-stu-id="f780d-119">is a [Hadamard](xref:microsoft.quantum.intrinsic.h) operation acting on a single-qubit register.</span></span>

<span data-ttu-id="f780d-120">Os portões quânticos são ordenados por ordem cronológica com o portão mais à esquerda, como o portão aplicado pela primeira vez aos qubits.</span><span class="sxs-lookup"><span data-stu-id="f780d-120">Quantum gates are ordered in chronological order with the left-most gate as the gate first applied to the qubits.</span></span>
<span data-ttu-id="f780d-121">Por outras palavras, se imaginarmos os fios como segurando o estado quântico, os fios trazem o estado quântico através de cada um dos portões do diagrama da esquerda para a direita.</span><span class="sxs-lookup"><span data-stu-id="f780d-121">In other words, if you picture the wires as holding the quantum state, the wires bring the quantum state through each of the gates in the diagram from left to right.</span></span>
<span data-ttu-id="f780d-122">Ou seja,</span><span class="sxs-lookup"><span data-stu-id="f780d-122">That is to say</span></span> 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="f780d-123">![Diagrama de portões quânticos sendo aplicado da esquerda para a direita](~/media/3.svg)</span><span class="sxs-lookup"><span data-stu-id="f780d-123">![Diagram of quantum gates being applied left-to-right](~/media/3.svg)</span></span>

<span data-ttu-id="f780d-124">é a matriz unitária $CBA $ .</span><span class="sxs-lookup"><span data-stu-id="f780d-124">is the unitary matrix $CBA$.</span></span>
<span data-ttu-id="f780d-125">A multiplicação da matriz obedece à convenção oposta: a matriz mais direita é aplicada primeiro.</span><span class="sxs-lookup"><span data-stu-id="f780d-125">Matrix multiplication obeys the opposite convention: the right-most matrix is applied first.</span></span> <span data-ttu-id="f780d-126">Nos diagramas do circuito quântico, no entanto, o portão mais à esquerda é aplicado primeiro.</span><span class="sxs-lookup"><span data-stu-id="f780d-126">In quantum circuit diagrams, however, the left-most gate is applied first.</span></span>
<span data-ttu-id="f780d-127">Esta diferença pode, por vezes, conduzir à confusão, pelo que é importante notar esta diferença significativa entre a notação algébrica linear e os diagramas do circuito quântico.</span><span class="sxs-lookup"><span data-stu-id="f780d-127">This difference can at times lead to confusion, so it is important to note this significant difference between the linear algebraic notation and quantum circuit diagrams.</span></span>

## <a name="inputs-and-outputs-of-quantum-circuits"></a><span data-ttu-id="f780d-128">Entradas e saídas de circuitos quânticos</span><span class="sxs-lookup"><span data-stu-id="f780d-128">Inputs and outputs of quantum circuits</span></span>
<span data-ttu-id="f780d-129">Todos os exemplos anteriores dados tiveram precisamente o mesmo número de fios (qubits) para um portão quântico que o número de fios fora do portão quântico.</span><span class="sxs-lookup"><span data-stu-id="f780d-129">All previous examples given have had precisely the same number of wires (qubits) input to a quantum gate as the number of wires out from the quantum gate.</span></span>
<span data-ttu-id="f780d-130">Pode parecer razoável que os circuitos quânticos possam ter mais, ou menos, saídas do que as entradas em geral.</span><span class="sxs-lookup"><span data-stu-id="f780d-130">It may at first seem reasonable that quantum circuits could have more, or fewer, outputs than inputs in general.</span></span>
<span data-ttu-id="f780d-131">Isto é impossível, no entanto, porque todas as operações quânticas, exceto a medição, são unitárias e, portanto, reversíveis.</span><span class="sxs-lookup"><span data-stu-id="f780d-131">This is impossible, however, because all quantum operations, save measurement, are unitary and hence reversible.</span></span>
<span data-ttu-id="f780d-132">Se não tivessem o mesmo número de saídas que os inputs, não seriam reversíveis e, portanto, não unitários, o que constitui uma contradição.</span><span class="sxs-lookup"><span data-stu-id="f780d-132">If they did not have the same number of outputs as inputs they would not be reversible and hence not unitary, which is a contradiction.</span></span>
<span data-ttu-id="f780d-133">Por esta razão, qualquer caixa desenhada num diagrama de circuito deve ter precisamente o mesmo número de fios que a entram na saída.</span><span class="sxs-lookup"><span data-stu-id="f780d-133">For this reason any box drawn in a circuit diagram must have precisely the same number of wires entering it as exiting it.</span></span>

<span data-ttu-id="f780d-134">Os diagramas de circuitos multi-qubit seguem convenções semelhantes às de um único qubit.</span><span class="sxs-lookup"><span data-stu-id="f780d-134">Multi-qubit circuit diagrams follow similar conventions to single-qubit ones.</span></span>
<span data-ttu-id="f780d-135">Como exemplo esclarecedor, podemos definir uma operação unitária de dois qubits $B $ ser $(H S \otimes X)$ e expressar o circuito de forma equivalente a</span><span class="sxs-lookup"><span data-stu-id="f780d-135">As a clarifying example, we can define a two-qubit unitary operation $B$ to be $(H S\otimes X)$ and express the circuit equivalently as</span></span>

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="f780d-136">![Diagrama de circuito de uma operação unitária de dois qubits](~/media/4.svg)</span><span class="sxs-lookup"><span data-stu-id="f780d-136">![Circuit diagram of a two-qubit unitary operation](~/media/4.svg)</span></span>

<span data-ttu-id="f780d-137">Também podemos considerar $B $ ter uma ação num único registo de dois qubits em vez de dois registos de um qubit, dependendo do contexto em que o circuito é utilizado.</span><span class="sxs-lookup"><span data-stu-id="f780d-137">We can also view $B$ as having an action on a single two-qubit register rather than two one-qubit registers depending on the context in which the circuit is used.</span></span> <span data-ttu-id="f780d-138">Talvez a propriedade mais útil de tais diagramas de circuito abstrato é que permitem que algoritmos quânticos complicados sejam descritos a um nível elevado sem ter que compilá-los até portões fundamentais.</span><span class="sxs-lookup"><span data-stu-id="f780d-138">Perhaps the most useful property of such abstract circuit diagrams is that they allow complicated quantum algorithms to be described at a high level without having to compile them down to fundamental gates.</span></span>
<span data-ttu-id="f780d-139">Isto significa que você pode obter uma intuição sobre o fluxo de dados para um grande algoritmo quântico sem precisar de entender todos os detalhes de como cada um dos subrotinas dentro do algoritmo funciona.</span><span class="sxs-lookup"><span data-stu-id="f780d-139">This means that you can get an intuition about the data flow for a large quantum algorithm without needing to understand all the details of how each of the subroutines within the algorithm work.</span></span>

## <a name="controlled-gates"></a><span data-ttu-id="f780d-140">Portões controlados</span><span class="sxs-lookup"><span data-stu-id="f780d-140">Controlled gates</span></span>
<span data-ttu-id="f780d-141">A outra construção que é incorporada em diagramas de circuito quântico multi-qubit é o controlo.</span><span class="sxs-lookup"><span data-stu-id="f780d-141">The other construct that is built into multi-qubit quantum circuit diagrams is control.</span></span>
<span data-ttu-id="f780d-142">A ação de um portão quântico controlado, denotados $\Lambda(G)$, onde o valor de um único qubit controla a aplicação de $ $G, pode ser entendido o seguinte exemplo de uma entrada do estado do produto $\Lambda(G) (\alpha \ket{0 } + \beta \ket{1 } ) \ket { \psi = } \alfa \ket{0\ket } { \\ \0\\\ket } \1 } \ket { }</span><span class="sxs-lookup"><span data-stu-id="f780d-142">The action of a quantum singly controlled gate, denoted $\Lambda(G)$, where a single qubit's value controls the application of $G$, can be understood by looking at the following example of a product state input $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket{\psi}$.</span></span>
<span data-ttu-id="f780d-143">Ou seja, o portão controlado aplica-se $G $ ao registo que contém $\psi se e $ somente se o qubit de controlo levar o valor $1 $ .</span><span class="sxs-lookup"><span data-stu-id="f780d-143">That is to say, the controlled gate applies $G$ to the register containing $\psi$ if and only if the control qubit takes the value $1$.</span></span>
<span data-ttu-id="f780d-144">Em geral, descrevemos tais operações controladas em diagramas de circuitos como</span><span class="sxs-lookup"><span data-stu-id="f780d-144">In general, we describe such controlled operations in circuit diagrams as</span></span>

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="f780d-145">![Diagrama de circuito de um portão controlado por singly](~/media/5.svg)</span><span class="sxs-lookup"><span data-stu-id="f780d-145">![Circuit diagram of a singly controlled gate](~/media/5.svg)</span></span>

<span data-ttu-id="f780d-146">Aqui o círculo preto denota a bit quântica sobre a qual o portão é controlado e um fio vertical denota o unitário que é aplicado quando o qubit de controlo leva o valor $1 $ .</span><span class="sxs-lookup"><span data-stu-id="f780d-146">Here the black circle denotes the quantum bit on which the gate is controlled and a vertical wire denotes the unitary that is applied when the control qubit takes the value $1$.</span></span>
<span data-ttu-id="f780d-147">Para os casos especiais em que $G=X $ e $G=Z $ introduzimos a seguinte notação para descrever a versão controlada dos portões (note que o portão controlado-X é o [ $ portão $CNOT):](xref:microsoft.quantum.intrinsic.cnot)</span><span class="sxs-lookup"><span data-stu-id="f780d-147">For the special cases where $G=X$ and $G=Z$ we introduce the following notation to describe the controlled version of the gates (note that the controlled-X gate is the [$CNOT$ gate](xref:microsoft.quantum.intrinsic.cnot)):</span></span>

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="f780d-148">![Diagrama de circuito para casos especiais de portões controlados](~/media/6.svg)</span><span class="sxs-lookup"><span data-stu-id="f780d-148">![Circuit diagram for special cases of controlled gates](~/media/6.svg)</span></span>

<span data-ttu-id="f780d-149">Q# fornece métodos para gerar automaticamente a versão controlada de uma operação, o que evita que o programador tenha de codificar estas operações.</span><span class="sxs-lookup"><span data-stu-id="f780d-149">Q# provides methods to automatically generate the controlled version of an operation, which saves the programmer from having to hand code these operations.</span></span> <span data-ttu-id="f780d-150">Um exemplo disso é mostrado abaixo:</span><span class="sxs-lookup"><span data-stu-id="f780d-150">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a><span data-ttu-id="f780d-151">Operador de medição</span><span class="sxs-lookup"><span data-stu-id="f780d-151">Measurement operator</span></span>
<span data-ttu-id="f780d-152">A restante operação para visualizar em diagramas de circuitos é a medição.</span><span class="sxs-lookup"><span data-stu-id="f780d-152">The remaining operation to visualize in circuit diagrams is measurement.</span></span>
<span data-ttu-id="f780d-153">A medição toma um registo qubit, mede-o e produz o resultado como informação clássica.</span><span class="sxs-lookup"><span data-stu-id="f780d-153">Measurement takes a qubit register, measures it, and outputs the result as classical information.</span></span>
<span data-ttu-id="f780d-154">Uma operação de medição é denotada por um símbolo do medidor e toma sempre como entrada um registo qubit (denotado por uma linha sólida) e produz informações clássicas (denotadas por uma linha dupla).</span><span class="sxs-lookup"><span data-stu-id="f780d-154">A measurement operation is denoted by a meter symbol and always takes as input a qubit register (denoted by a solid line) and outputs classical information (denoted by a double line).</span></span>
<span data-ttu-id="f780d-155">Especificamente, tal subcircito parece:</span><span class="sxs-lookup"><span data-stu-id="f780d-155">Specifically, such a subcircuit looks like:</span></span>

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="f780d-156">![Símbolo que representa uma operação de medição](~/media/7.svg)</span><span class="sxs-lookup"><span data-stu-id="f780d-156">![Symbol representing a measurement operation](~/media/7.svg)</span></span>

<span data-ttu-id="f780d-157">Q# implementa um [operador de medida](xref:microsoft.quantum.intrinsic.measure) para o efeito.</span><span class="sxs-lookup"><span data-stu-id="f780d-157">Q# implements a [Measure operator](xref:microsoft.quantum.intrinsic.measure) for this purpose.</span></span>
<span data-ttu-id="f780d-158">Consulte a [secção de medições](xref:microsoft.quantum.libraries.standard.prelude#measurements) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f780d-158">See the [section on measurements](xref:microsoft.quantum.libraries.standard.prelude#measurements) for more information.</span></span>

<span data-ttu-id="f780d-159">Da mesma forma, o subcircito</span><span class="sxs-lookup"><span data-stu-id="f780d-159">Similarly, the subcircuit</span></span>

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="f780d-160">![Diagrama de circuito que representa uma operação controlada](~/media/8.svg)</span><span class="sxs-lookup"><span data-stu-id="f780d-160">![Circuit diagram representing a controlled operation](~/media/8.svg)</span></span>

<span data-ttu-id="f780d-161">dá um portão controlado clássicamente, onde $G $ é aplicado condicionado na bit de controlo clássica que é de valor $1 $ .</span><span class="sxs-lookup"><span data-stu-id="f780d-161">gives a classically controlled gate, where $G$ is applied conditioned on the classical control bit being value $1$.</span></span>

## <a name="teleportation-circuit-diagram"></a><span data-ttu-id="f780d-162">Diagrama do circuito de teletransporte</span><span class="sxs-lookup"><span data-stu-id="f780d-162">Teleportation circuit diagram</span></span>
<span data-ttu-id="f780d-163">O teletransporte quântico é talvez o melhor algoritmo quântico para ilustrar estes componentes.</span><span class="sxs-lookup"><span data-stu-id="f780d-163">Quantum teleportation is perhaps the best quantum algorithm for illustrating these components.</span></span>
<span data-ttu-id="f780d-164">Pode aprender prática com o teletransporte [Quantum Kata](xref:microsoft.quantum.overview.katas) correspondente é um método para mover dados dentro de um computador quântico (ou mesmo entre computadores quânticos distantes numa rede quântica) através da utilização de emaranhamento e medição.</span><span class="sxs-lookup"><span data-stu-id="f780d-164">You can learn hands-on with the corresponding [Quantum Kata](xref:microsoft.quantum.overview.katas) Quantum teleportation is a method for moving data within a quantum computer (or even between distant quantum computers in a quantum network) through the use of entanglement and measurement.</span></span>
<span data-ttu-id="f780d-165">Curiosamente, é realmente capaz de mover um estado quântico, digamos o valor num dado qubit, de um qubit para outro, sem sequer saber qual é o valor do qubit!</span><span class="sxs-lookup"><span data-stu-id="f780d-165">Interestingly, it is actually capable of moving a quantum state, say the value in a given qubit, from one qubit to another, without even knowing what the qubit's value is!</span></span>
<span data-ttu-id="f780d-166">Isto é necessário para que o protocolo funcione de acordo com as leis da mecânica quântica.</span><span class="sxs-lookup"><span data-stu-id="f780d-166">This is necessary for the protocol to work according to the laws of quantum mechanics.</span></span>
<span data-ttu-id="f780d-167">O circuito de teletransporte quântico é dado abaixo; também fornecemos uma versão anotada do circuito para ilustrar como ler o circuito quântico.</span><span class="sxs-lookup"><span data-stu-id="f780d-167">The quantum teleportation circuit is given below; we also provide an annotated version of the circuit to illustrate how to read the quantum circuit.</span></span>

<!--- ![](.\media\tp2.svg){ width=50% } --->
<span data-ttu-id="f780d-168">![Circuito de teletransporte quântico](~/media/tp2.svg)</span><span class="sxs-lookup"><span data-stu-id="f780d-168">![Quantum teleportation circuit](~/media/tp2.svg)</span></span>
