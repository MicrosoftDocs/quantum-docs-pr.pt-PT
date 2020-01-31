---
title: Circuitos quânticos Microsoft Docs
description: Circuitos quânticos
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: fe845aa0dde7c780ea6721dfe2559119e90b4aa5
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820798"
---
# <a name="quantum-circuits"></a><span data-ttu-id="a9d62-103">Circuitos Quânticos</span><span class="sxs-lookup"><span data-stu-id="a9d62-103">Quantum Circuits</span></span>
<span data-ttu-id="a9d62-104">Considere por um momento a transformação unitária $\text{ CNOT}_{01}(H\otimes 1)$.</span><span class="sxs-lookup"><span data-stu-id="a9d62-104">Consider for a moment the unitary transformation $\text{ CNOT}_{01}(H\otimes 1)$.</span></span>
<span data-ttu-id="a9d62-105">Esta sequência de portão é de importância fundamental para a computação quântica porque cria um estado de dois qubits maximamente emaranhado:</span><span class="sxs-lookup"><span data-stu-id="a9d62-105">This gate sequence is of fundamental significance to quantum computing because it creates a maximally entangled two-qubit state:</span></span>

<span data-ttu-id="a9d62-106">$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left (\ket{00} + \ket{11} \right),$$$$</span><span class="sxs-lookup"><span data-stu-id="a9d62-106">$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right),$$</span></span>

<span data-ttu-id="a9d62-107">As operações com esta ou maior complexidade são ubíquas em algoritmos quânticos e correção de erros quânticos, pelo que deve ser um grande alívio que existe um método simples para a sua visualização chamado diagrama de *circuito quântico.*</span><span class="sxs-lookup"><span data-stu-id="a9d62-107">Operations with this or greater complexity are ubiquitous in quantum algorithms and quantum error correction, so it should come as a great relief that there is a simple method for their visualization called a *quantum circuit diagram*.</span></span>
<span data-ttu-id="a9d62-108">O diagrama do circuito para preparar este estado quântico maximamente emaranhado é:</span><span class="sxs-lookup"><span data-stu-id="a9d62-108">The circuit diagram for preparing this maximally entangled quantum state is:</span></span>

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/Concepts1.png)

## <a name="quantum-circuit-diagram-conventions"></a><span data-ttu-id="a9d62-109">Convenções de diagramas de circuito quântico</span><span class="sxs-lookup"><span data-stu-id="a9d62-109">Quantum circuit diagram conventions</span></span>
<span data-ttu-id="a9d62-110">Esta linguagem visual para operações quânticas pode ser mais facilmente digerível do que escrever a sua matriz equivalente uma vez que você entenda as convenções para expressar um circuito quântico.</span><span class="sxs-lookup"><span data-stu-id="a9d62-110">This visual language for quantum operations can be more readily digestible than writing down its equivalent matrix once you understand the conventions for expressing a quantum circuit.</span></span>
<span data-ttu-id="a9d62-111">Revemos estas convenções abaixo.</span><span class="sxs-lookup"><span data-stu-id="a9d62-111">We review these conventions below.</span></span>

<span data-ttu-id="a9d62-112">Num diagrama de circuito, cada linha sólida retrata um qubit ou, mais geralmente, um registo qubit.</span><span class="sxs-lookup"><span data-stu-id="a9d62-112">In a circuit diagram, each solid line depicts a qubit or more generally a qubit register.</span></span>
<span data-ttu-id="a9d62-113">Por convenção, a linha de cima é o registo qubit $0$ e o restante é rotulado sequencialmente.</span><span class="sxs-lookup"><span data-stu-id="a9d62-113">By convention, the top line is qubit register $0$ and the remainder are labeled sequentially.</span></span> <span data-ttu-id="a9d62-114">O circuito de exemplo acima é descrito como agindo em dois qubits (ou equivalentemente dois registos constituídos por um qubit).</span><span class="sxs-lookup"><span data-stu-id="a9d62-114">The above example circuit is depicted as acting on two qubits (or equivalently two registers consisting of one qubit).</span></span>
<span data-ttu-id="a9d62-115">Os portões que atuam num ou mais registos qubit são denotados como uma caixa.</span><span class="sxs-lookup"><span data-stu-id="a9d62-115">Gates acting on one or more qubit registers are denoted as a box.</span></span>
<span data-ttu-id="a9d62-116">Por exemplo, o símbolo</span><span class="sxs-lookup"><span data-stu-id="a9d62-116">For example, the symbol</span></span>

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_2.png)

<span data-ttu-id="a9d62-117">é o portão [Hadamard](xref:microsoft.quantum.intrinsic.h) agindo num registo de qubit único.</span><span class="sxs-lookup"><span data-stu-id="a9d62-117">is the [Hadamard](xref:microsoft.quantum.intrinsic.h) gate acting on a single-qubit register.</span></span>

<span data-ttu-id="a9d62-118">Os portões quânticos são encomendados por ordem cronológica com o portão mais à esquerda, uma vez que o portão se aplicava primeiro aos qubits.</span><span class="sxs-lookup"><span data-stu-id="a9d62-118">Quantum gates are ordered in chronological order with the left-most gate as the gate first applied to the qubits.</span></span>
<span data-ttu-id="a9d62-119">Por outras palavras, se imaginarmos os fios como segurando o estado quântico, os fios trazem o estado quântico através de cada um dos portões do diagrama da esquerda para a direita.</span><span class="sxs-lookup"><span data-stu-id="a9d62-119">In other words, if you picture the wires as holding the quantum state, the wires bring the quantum state through each of the gates in the diagram from left to right.</span></span>
<span data-ttu-id="a9d62-120">Isto é,</span><span class="sxs-lookup"><span data-stu-id="a9d62-120">That is to say</span></span> 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_3.png)

<span data-ttu-id="a9d62-121">é a matriz unitária $CBA$.</span><span class="sxs-lookup"><span data-stu-id="a9d62-121">is the unitary matrix $CBA$.</span></span>
<span data-ttu-id="a9d62-122">A multiplicação da matriz obedece à convenção oposta: a matriz mais correta é aplicada primeiro.</span><span class="sxs-lookup"><span data-stu-id="a9d62-122">Matrix multiplication obeys the opposite convention: the right-most matrix is applied first.</span></span> <span data-ttu-id="a9d62-123">Nos diagramas de circuitos quânticos, no entanto, o portão mais à esquerda é aplicado primeiro.</span><span class="sxs-lookup"><span data-stu-id="a9d62-123">In quantum circuit diagrams, however, the left-most gate is applied first.</span></span>
<span data-ttu-id="a9d62-124">Esta diferença pode, por vezes, levar à confusão, pelo que é importante notar esta diferença significativa entre a notação algébrica linear e os diagramas de circuitos quânticos.</span><span class="sxs-lookup"><span data-stu-id="a9d62-124">This difference can at times lead to confusion, so it is important to note this significant difference between the linear algebraic notation and quantum circuit diagrams.</span></span>

## <a name="inputs-and-outputs-of-quantum-circuits"></a><span data-ttu-id="a9d62-125">Inputs e saídas de circuitos quânticos</span><span class="sxs-lookup"><span data-stu-id="a9d62-125">Inputs and outputs of quantum circuits</span></span>
<span data-ttu-id="a9d62-126">Todos os exemplos anteriores dados tiveram precisamente o mesmo número de fios (qubits) de entrada para um portão quântico como o número de fios fora do portão quântico.</span><span class="sxs-lookup"><span data-stu-id="a9d62-126">All previous examples given have had precisely the same number of wires (qubits) input to a quantum gate as the number of wires out from the quantum gate.</span></span>
<span data-ttu-id="a9d62-127">Pode parecer razoável que os circuitos quânticos possam ter mais, ou menos, saídas do que inputs em geral.</span><span class="sxs-lookup"><span data-stu-id="a9d62-127">It may at first seem reasonable that quantum circuits could have more, or fewer, outputs than inputs in general.</span></span>
<span data-ttu-id="a9d62-128">Isto é impossível, no entanto, porque todas as operações quânticas, exceto a medição, são unitárias e, portanto, reversíveis.</span><span class="sxs-lookup"><span data-stu-id="a9d62-128">This is impossible, however, because all quantum operations, save measurement, are unitary and hence reversible.</span></span>
<span data-ttu-id="a9d62-129">Se não tivessem o mesmo número de saídas que os inputs, não seriam reversíveis e, portanto, não unitários, o que constitui uma contradição.</span><span class="sxs-lookup"><span data-stu-id="a9d62-129">If they did not have the same number of outputs as inputs they would not be reversible and hence not unitary, which is a contradiction.</span></span>
<span data-ttu-id="a9d62-130">Por esta razão, qualquer caixa desenhada num diagrama de circuito deve ter precisamente o mesmo número de fios que a entram como saída.</span><span class="sxs-lookup"><span data-stu-id="a9d62-130">For this reason any box drawn in a circuit diagram must have precisely the same number of wires entering it as exiting it.</span></span>

<span data-ttu-id="a9d62-131">Os diagramas de circuitos multiqubits seguem convenções semelhantes às de um qubit único.</span><span class="sxs-lookup"><span data-stu-id="a9d62-131">Multi-qubit circuit diagrams follow similar conventions to single-qubit ones.</span></span>
<span data-ttu-id="a9d62-132">Como exemplo esclarecedor, podemos definir uma operação unitária de dois qubits $B$ para ser $(H S\otimes X)$ e expressar o circuito de forma equivalente como</span><span class="sxs-lookup"><span data-stu-id="a9d62-132">As a clarifying example, we can define a two-qubit unitary operation $B$ to be $(H S\otimes X)$ and express the circuit equivalently as</span></span>

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_4.png)

<span data-ttu-id="a9d62-133">Também podemos ver $B$ como tendo uma ação num único registo de dois qubits em vez de dois registos de um qubit dependendo do contexto em que o circuito é usado.</span><span class="sxs-lookup"><span data-stu-id="a9d62-133">We can also view $B$ as having an action on a single two-qubit register rather than two one-qubit registers depending on the context in which the circuit is used.</span></span> <span data-ttu-id="a9d62-134">Talvez a propriedade mais útil de tais diagramas de circuitos abstratos é que eles permitem que algoritmos quânticos complicados sejam descritos a um nível elevado sem ter que compilá-los até portões fundamentais.</span><span class="sxs-lookup"><span data-stu-id="a9d62-134">Perhaps the most useful property of such abstract circuit diagrams is that they allow complicated quantum algorithms to be described at a high level without having to compile them down to fundamental gates.</span></span>
<span data-ttu-id="a9d62-135">Isto significa que você pode obter uma intuição sobre o fluxo de dados para um grande algoritmo quântico sem precisar entender todos os detalhes de como cada uma das subrotinas dentro do algoritmo funciona.</span><span class="sxs-lookup"><span data-stu-id="a9d62-135">This means that you can get an intuition about the data flow for a large quantum algorithm without needing to understand all the details of how each of the subroutines within the algorithm work.</span></span>

## <a name="controlled-gates"></a><span data-ttu-id="a9d62-136">Portões controlados</span><span class="sxs-lookup"><span data-stu-id="a9d62-136">Controlled gates</span></span>
<span data-ttu-id="a9d62-137">A outra construção que é incorporada em diagramas de circuito quântico multiqubit é o controlo.</span><span class="sxs-lookup"><span data-stu-id="a9d62-137">The other construct that is built into multi-qubit quantum circuit diagrams is control.</span></span>
<span data-ttu-id="a9d62-138">A ação de um portão controlado por singly quântico, denotada $\Lambda(G)$, onde um único qubit controla a aplicação de $G$, pode ser entendida olhando para o exemplo seguinte de uma entrada do estado do produto $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket {\psi} = \ket{0} \ket {\psi+{1} \\</span><span class="sxs-lookup"><span data-stu-id="a9d62-138">The action of a quantum singly controlled gate, denoted $\Lambda(G)$, where a single qubit's value controls the application of $G$, can be understood by looking at the following example of a product state input $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket{\psi}$.</span></span>
<span data-ttu-id="a9d62-139">Ou seja, o portão controlado aplica-se $G$ ao registo que contém $\psi$ se e apenas se o qubit de controlo levar o valor $1$.</span><span class="sxs-lookup"><span data-stu-id="a9d62-139">That is to say, the controlled gate applies $G$ to the register containing $\psi$ if and only if the control qubit takes the value $1$.</span></span>
<span data-ttu-id="a9d62-140">Em geral, descrevemos tais operações controladas em diagramas de circuitos como</span><span class="sxs-lookup"><span data-stu-id="a9d62-140">In general, we describe such controlled operations in circuit diagrams as</span></span>

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_5.png)

<span data-ttu-id="a9d62-141">Aqui o círculo negro denota a bit quântica em que o portão é controlado e um fio vertical denota o unitário que é aplicado quando o qubit de controlo leva o valor $1$.</span><span class="sxs-lookup"><span data-stu-id="a9d62-141">Here the black circle denotes the quantum bit on which the gate is controlled and a vertical wire denotes the unitary that is applied when the control qubit takes the value $1$.</span></span>
<span data-ttu-id="a9d62-142">Para os casos especiais em que $G=X$ e $G=Z$ introduzimos a seguinte notação para descrever a versão controlada dos portões (note que o portão controlado-X é o [portão $CNOT$](xref:microsoft.quantum.intrinsic.cnot)):</span><span class="sxs-lookup"><span data-stu-id="a9d62-142">For the special cases where $G=X$ and $G=Z$ we introduce the following notation to describe the controlled version of the gates (note that the controlled-X gate is the [$CNOT$ gate](xref:microsoft.quantum.intrinsic.cnot)):</span></span>

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_6.png)

<span data-ttu-id="a9d62-143">Q# fornece métodos para gerar automaticamente a versão controlada de uma operação, que evita que o programador tenha de codificar estas operações manualmente.</span><span class="sxs-lookup"><span data-stu-id="a9d62-143">Q# provides methods to automatically generate the controlled version of an operation, which saves the programmer from having to hand code these operations.</span></span> <span data-ttu-id="a9d62-144">Um exemplo disto é mostrado abaixo:</span><span class="sxs-lookup"><span data-stu-id="a9d62-144">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a><span data-ttu-id="a9d62-145">Operador de medição</span><span class="sxs-lookup"><span data-stu-id="a9d62-145">Measurement operator</span></span>
<span data-ttu-id="a9d62-146">A operação restante para visualizar em diagramas de circuitos é a medição.</span><span class="sxs-lookup"><span data-stu-id="a9d62-146">The remaining operation to visualize in circuit diagrams is measurement.</span></span>
<span data-ttu-id="a9d62-147">A medição tem um registo qubit, mede-o e produz o resultado como informação clássica.</span><span class="sxs-lookup"><span data-stu-id="a9d62-147">Measurement takes a qubit register, measures it, and outputs the result as classical information.</span></span>
<span data-ttu-id="a9d62-148">Uma operação de medição é denotada por um símbolo de contador e toma sempre como entrada um registo qubit (denotado por uma linha sólida) e produz informações clássicas (denotadas por uma linha dupla).</span><span class="sxs-lookup"><span data-stu-id="a9d62-148">A measurement operation is denoted by a meter symbol and always takes as input a qubit register (denoted by a solid line) and outputs classical information (denoted by a double line).</span></span>
<span data-ttu-id="a9d62-149">Especificamente, tal subcircuito parece:</span><span class="sxs-lookup"><span data-stu-id="a9d62-149">Specifically, such a subcircuit looks like:</span></span>

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="a9d62-150">](~/media/concepts_7.png) do circuito de medição de ![</span><span class="sxs-lookup"><span data-stu-id="a9d62-150">![Measurement circuit](~/media/concepts_7.png)</span></span>

<span data-ttu-id="a9d62-151">Q# implementa um operador de [medida](xref:microsoft.quantum.intrinsic.measure) para o efeito.</span><span class="sxs-lookup"><span data-stu-id="a9d62-151">Q# implements a [Measure operator](xref:microsoft.quantum.intrinsic.measure) for this purpose.</span></span>
<span data-ttu-id="a9d62-152">Consulte a [secção sobre medições](xref:microsoft.quantum.libraries.standard.prelude#measurements) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a9d62-152">See the [section on measurements](xref:microsoft.quantum.libraries.standard.prelude#measurements) for more information.</span></span>

<span data-ttu-id="a9d62-153">Da mesma forma, o subcircuito</span><span class="sxs-lookup"><span data-stu-id="a9d62-153">Similarly, the subcircuit</span></span>

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_8.png)

<span data-ttu-id="a9d62-154">dá um portão controlado clássicamente, onde $G$ é aplicado condicionado na broca de controlo clássico sendo $1$.</span><span class="sxs-lookup"><span data-stu-id="a9d62-154">gives a classically controlled gate, where $G$ is applied conditioned on the classical control bit being value $1$.</span></span>

## <a name="teleportation-circuit-diagram"></a><span data-ttu-id="a9d62-155">Diagrama do circuito de teletransporte</span><span class="sxs-lookup"><span data-stu-id="a9d62-155">Teleportation circuit diagram</span></span>
<span data-ttu-id="a9d62-156">[A teleportação quântica](xref:microsoft.quantum.techniques.puttingittogether) é talvez o melhor algoritmo quântico para ilustrar estes componentes.</span><span class="sxs-lookup"><span data-stu-id="a9d62-156">[Quantum teleportation](xref:microsoft.quantum.techniques.puttingittogether) is perhaps the best quantum algorithm for illustrating these components.</span></span>
<span data-ttu-id="a9d62-157">A teleportação quântica é um método para mover dados dentro de um computador quântico (ou mesmo entre computadores quânticos distantes numa rede quântica) através do uso do emaranhado e da medição.</span><span class="sxs-lookup"><span data-stu-id="a9d62-157">Quantum teleportation is a method for moving data within a quantum computer (or even between distant quantum computers in a quantum network) through the use of entanglement and measurement.</span></span>
<span data-ttu-id="a9d62-158">Curiosamente, é realmente capaz de mover um estado quântico, digamos, o valor num determinado qubit, de um qubit para outro, sem sequer saber qual é o valor do qubit!</span><span class="sxs-lookup"><span data-stu-id="a9d62-158">Interestingly, it is actually capable of moving a quantum state, say the value in a given qubit, from one qubit to another, without even knowing what the qubit's value is!</span></span>
<span data-ttu-id="a9d62-159">Isto é necessário para que o protocolo funcione de acordo com as leis da Mecânica Quântica.</span><span class="sxs-lookup"><span data-stu-id="a9d62-159">This is necessary for the protocol to work according to the laws of quantum mechanics.</span></span>
<span data-ttu-id="a9d62-160">O circuito de teletransporte quântico é dado abaixo; também fornecemos uma versão anotada do circuito para ilustrar como ler o circuito quântico.</span><span class="sxs-lookup"><span data-stu-id="a9d62-160">The quantum teleportation circuit is given below; we also provide an annotated version of the circuit to illustrate how to read the quantum circuit.</span></span>

<!--- ![](.\media\tp2.svg){ width=50% } --->
![](~/media/concepts_tp2.png)
