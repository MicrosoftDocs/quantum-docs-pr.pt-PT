---
title: Circuitos quânticos
description: Aprenda a representar visualmente operações quânticas simples e complexas com diagramas de circuito quântico.
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 80d9df00159090768ea442e519c34043a99b050c
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/10/2020
ms.locfileid: "79022774"
---
# <a name="quantum-circuits"></a><span data-ttu-id="502fe-103">Circuitos Quânticos</span><span class="sxs-lookup"><span data-stu-id="502fe-103">Quantum Circuits</span></span>
<span data-ttu-id="502fe-104">Considere por um momento a transformação unitária $\text{ CNOT}_{01}(H\otimes 1)$.</span><span class="sxs-lookup"><span data-stu-id="502fe-104">Consider for a moment the unitary transformation $\text{ CNOT}_{01}(H\otimes 1)$.</span></span>
<span data-ttu-id="502fe-105">Esta sequência de portão é de importância fundamental para a computação quântica porque cria um estado de dois qubits maximamente emaranhado:</span><span class="sxs-lookup"><span data-stu-id="502fe-105">This gate sequence is of fundamental significance to quantum computing because it creates a maximally entangled two-qubit state:</span></span>

<span data-ttu-id="502fe-106">$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left (\ket{00} + \ket{11} \right),$$$$</span><span class="sxs-lookup"><span data-stu-id="502fe-106">$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right),$$</span></span>

<span data-ttu-id="502fe-107">As operações com esta ou maior complexidade são ubíquas em algoritmos quânticos e correção de erros quânticos, pelo que deve ser um grande alívio que existe um método simples para a sua visualização chamado diagrama de *circuito quântico.*</span><span class="sxs-lookup"><span data-stu-id="502fe-107">Operations with this or greater complexity are ubiquitous in quantum algorithms and quantum error correction, so it should come as a great relief that there is a simple method for their visualization called a *quantum circuit diagram*.</span></span>
<span data-ttu-id="502fe-108">O diagrama do circuito para preparar este estado quântico maximamente emaranhado é:</span><span class="sxs-lookup"><span data-stu-id="502fe-108">The circuit diagram for preparing this maximally entangled quantum state is:</span></span>

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="502fe-109">Diagrama do Circuito ![para um estado de dois qubits maximamente emaranhado](~/media/1.svg)</span><span class="sxs-lookup"><span data-stu-id="502fe-109">![Circuit diagram for a maximally entangled two-qubit state](~/media/1.svg)</span></span>

## <a name="quantum-circuit-diagram-conventions"></a><span data-ttu-id="502fe-110">Convenções de diagramas de circuito quântico</span><span class="sxs-lookup"><span data-stu-id="502fe-110">Quantum circuit diagram conventions</span></span>
<span data-ttu-id="502fe-111">Esta linguagem visual para operações quânticas pode ser mais facilmente digerível do que escrever a sua matriz equivalente uma vez que você entenda as convenções para expressar um circuito quântico.</span><span class="sxs-lookup"><span data-stu-id="502fe-111">This visual language for quantum operations can be more readily digestible than writing down its equivalent matrix once you understand the conventions for expressing a quantum circuit.</span></span>
<span data-ttu-id="502fe-112">Revemos estas convenções abaixo.</span><span class="sxs-lookup"><span data-stu-id="502fe-112">We review these conventions below.</span></span>

<span data-ttu-id="502fe-113">Num diagrama de circuito, cada linha sólida retrata um qubit ou, mais geralmente, um registo qubit.</span><span class="sxs-lookup"><span data-stu-id="502fe-113">In a circuit diagram, each solid line depicts a qubit or more generally a qubit register.</span></span>
<span data-ttu-id="502fe-114">Por convenção, a linha de cima é o registo qubit $0$ e o restante é rotulado sequencialmente.</span><span class="sxs-lookup"><span data-stu-id="502fe-114">By convention, the top line is qubit register $0$ and the remainder are labeled sequentially.</span></span> <span data-ttu-id="502fe-115">O circuito de exemplo acima é descrito como agindo em dois qubits (ou equivalentemente dois registos constituídos por um qubit).</span><span class="sxs-lookup"><span data-stu-id="502fe-115">The above example circuit is depicted as acting on two qubits (or equivalently two registers consisting of one qubit).</span></span>
<span data-ttu-id="502fe-116">Os portões que atuam num ou mais registos qubit são denotados como uma caixa.</span><span class="sxs-lookup"><span data-stu-id="502fe-116">Gates acting on one or more qubit registers are denoted as a box.</span></span>
<span data-ttu-id="502fe-117">Por exemplo, o símbolo</span><span class="sxs-lookup"><span data-stu-id="502fe-117">For example, the symbol</span></span>

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="502fe-118">![Símbolo para uma operação Hadamard agindo num registo de um único qubit](~/media/2.svg)</span><span class="sxs-lookup"><span data-stu-id="502fe-118">![Symbol for a Hadamard operation acting on a single-qubit register](~/media/2.svg)</span></span>

<span data-ttu-id="502fe-119">é uma operação [Hadamard](xref:microsoft.quantum.intrinsic.h) agindo num registo de qubit único.</span><span class="sxs-lookup"><span data-stu-id="502fe-119">is a [Hadamard](xref:microsoft.quantum.intrinsic.h) operation acting on a single-qubit register.</span></span>

<span data-ttu-id="502fe-120">Os portões quânticos são encomendados por ordem cronológica com o portão mais à esquerda, uma vez que o portão se aplicava primeiro aos qubits.</span><span class="sxs-lookup"><span data-stu-id="502fe-120">Quantum gates are ordered in chronological order with the left-most gate as the gate first applied to the qubits.</span></span>
<span data-ttu-id="502fe-121">Por outras palavras, se imaginarmos os fios como segurando o estado quântico, os fios trazem o estado quântico através de cada um dos portões do diagrama da esquerda para a direita.</span><span class="sxs-lookup"><span data-stu-id="502fe-121">In other words, if you picture the wires as holding the quantum state, the wires bring the quantum state through each of the gates in the diagram from left to right.</span></span>
<span data-ttu-id="502fe-122">Isto é,</span><span class="sxs-lookup"><span data-stu-id="502fe-122">That is to say</span></span> 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="502fe-123">![Diagrama de portões quânticos a ser aplicado](~/media/3.svg) da esquerda para a direita</span><span class="sxs-lookup"><span data-stu-id="502fe-123">![Diagram of quantum gates being applied left-to-right](~/media/3.svg)</span></span>

<span data-ttu-id="502fe-124">é a matriz unitária $CBA$.</span><span class="sxs-lookup"><span data-stu-id="502fe-124">is the unitary matrix $CBA$.</span></span>
<span data-ttu-id="502fe-125">A multiplicação da matriz obedece à convenção oposta: a matriz mais correta é aplicada primeiro.</span><span class="sxs-lookup"><span data-stu-id="502fe-125">Matrix multiplication obeys the opposite convention: the right-most matrix is applied first.</span></span> <span data-ttu-id="502fe-126">Nos diagramas de circuitos quânticos, no entanto, o portão mais à esquerda é aplicado primeiro.</span><span class="sxs-lookup"><span data-stu-id="502fe-126">In quantum circuit diagrams, however, the left-most gate is applied first.</span></span>
<span data-ttu-id="502fe-127">Esta diferença pode, por vezes, levar à confusão, pelo que é importante notar esta diferença significativa entre a notação algébrica linear e os diagramas de circuitos quânticos.</span><span class="sxs-lookup"><span data-stu-id="502fe-127">This difference can at times lead to confusion, so it is important to note this significant difference between the linear algebraic notation and quantum circuit diagrams.</span></span>

## <a name="inputs-and-outputs-of-quantum-circuits"></a><span data-ttu-id="502fe-128">Inputs e saídas de circuitos quânticos</span><span class="sxs-lookup"><span data-stu-id="502fe-128">Inputs and outputs of quantum circuits</span></span>
<span data-ttu-id="502fe-129">Todos os exemplos anteriores dados tiveram precisamente o mesmo número de fios (qubits) de entrada para um portão quântico como o número de fios fora do portão quântico.</span><span class="sxs-lookup"><span data-stu-id="502fe-129">All previous examples given have had precisely the same number of wires (qubits) input to a quantum gate as the number of wires out from the quantum gate.</span></span>
<span data-ttu-id="502fe-130">Pode parecer razoável que os circuitos quânticos possam ter mais, ou menos, saídas do que inputs em geral.</span><span class="sxs-lookup"><span data-stu-id="502fe-130">It may at first seem reasonable that quantum circuits could have more, or fewer, outputs than inputs in general.</span></span>
<span data-ttu-id="502fe-131">Isto é impossível, no entanto, porque todas as operações quânticas, exceto a medição, são unitárias e, portanto, reversíveis.</span><span class="sxs-lookup"><span data-stu-id="502fe-131">This is impossible, however, because all quantum operations, save measurement, are unitary and hence reversible.</span></span>
<span data-ttu-id="502fe-132">Se não tivessem o mesmo número de saídas que os inputs, não seriam reversíveis e, portanto, não unitários, o que constitui uma contradição.</span><span class="sxs-lookup"><span data-stu-id="502fe-132">If they did not have the same number of outputs as inputs they would not be reversible and hence not unitary, which is a contradiction.</span></span>
<span data-ttu-id="502fe-133">Por esta razão, qualquer caixa desenhada num diagrama de circuito deve ter precisamente o mesmo número de fios que a entram como saída.</span><span class="sxs-lookup"><span data-stu-id="502fe-133">For this reason any box drawn in a circuit diagram must have precisely the same number of wires entering it as exiting it.</span></span>

<span data-ttu-id="502fe-134">Os diagramas de circuitos multiqubits seguem convenções semelhantes às de um qubit único.</span><span class="sxs-lookup"><span data-stu-id="502fe-134">Multi-qubit circuit diagrams follow similar conventions to single-qubit ones.</span></span>
<span data-ttu-id="502fe-135">Como exemplo esclarecedor, podemos definir uma operação unitária de dois qubits $B$ para ser $(H S\otimes X)$ e expressar o circuito de forma equivalente como</span><span class="sxs-lookup"><span data-stu-id="502fe-135">As a clarifying example, we can define a two-qubit unitary operation $B$ to be $(H S\otimes X)$ and express the circuit equivalently as</span></span>

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="502fe-136">Diagrama do Circuito ![de uma operação unitária de dois qubits](~/media/4.svg)</span><span class="sxs-lookup"><span data-stu-id="502fe-136">![Circuit diagram of a two-qubit unitary operation](~/media/4.svg)</span></span>

<span data-ttu-id="502fe-137">Também podemos ver $B$ como tendo uma ação num único registo de dois qubits em vez de dois registos de um qubit dependendo do contexto em que o circuito é usado.</span><span class="sxs-lookup"><span data-stu-id="502fe-137">We can also view $B$ as having an action on a single two-qubit register rather than two one-qubit registers depending on the context in which the circuit is used.</span></span> <span data-ttu-id="502fe-138">Talvez a propriedade mais útil de tais diagramas de circuitos abstratos é que eles permitem que algoritmos quânticos complicados sejam descritos a um nível elevado sem ter que compilá-los até portões fundamentais.</span><span class="sxs-lookup"><span data-stu-id="502fe-138">Perhaps the most useful property of such abstract circuit diagrams is that they allow complicated quantum algorithms to be described at a high level without having to compile them down to fundamental gates.</span></span>
<span data-ttu-id="502fe-139">Isto significa que você pode obter uma intuição sobre o fluxo de dados para um grande algoritmo quântico sem precisar entender todos os detalhes de como cada uma das subrotinas dentro do algoritmo funciona.</span><span class="sxs-lookup"><span data-stu-id="502fe-139">This means that you can get an intuition about the data flow for a large quantum algorithm without needing to understand all the details of how each of the subroutines within the algorithm work.</span></span>

## <a name="controlled-gates"></a><span data-ttu-id="502fe-140">Portões controlados</span><span class="sxs-lookup"><span data-stu-id="502fe-140">Controlled gates</span></span>
<span data-ttu-id="502fe-141">A outra construção que é incorporada em diagramas de circuito quântico multiqubit é o controlo.</span><span class="sxs-lookup"><span data-stu-id="502fe-141">The other construct that is built into multi-qubit quantum circuit diagrams is control.</span></span>
<span data-ttu-id="502fe-142">A ação de um portão controlado por singly quântico, denotada $\Lambda(G)$, onde um único qubit controla a aplicação de $G$, pode ser entendida olhando para o exemplo seguinte de uma entrada do estado do produto $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket {\psi} = \ket{0} \ket {\psi+{1} \\</span><span class="sxs-lookup"><span data-stu-id="502fe-142">The action of a quantum singly controlled gate, denoted $\Lambda(G)$, where a single qubit's value controls the application of $G$, can be understood by looking at the following example of a product state input $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket{\psi}$.</span></span>
<span data-ttu-id="502fe-143">Ou seja, o portão controlado aplica-se $G$ ao registo que contém $\psi$ se e apenas se o qubit de controlo levar o valor $1$.</span><span class="sxs-lookup"><span data-stu-id="502fe-143">That is to say, the controlled gate applies $G$ to the register containing $\psi$ if and only if the control qubit takes the value $1$.</span></span>
<span data-ttu-id="502fe-144">Em geral, descrevemos tais operações controladas em diagramas de circuitos como</span><span class="sxs-lookup"><span data-stu-id="502fe-144">In general, we describe such controlled operations in circuit diagrams as</span></span>

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="502fe-145">Diagrama do circuito ![de um portão controlado](~/media/5.svg)</span><span class="sxs-lookup"><span data-stu-id="502fe-145">![Circuit diagram of a singly controlled gate](~/media/5.svg)</span></span>

<span data-ttu-id="502fe-146">Aqui o círculo negro denota a bit quântica em que o portão é controlado e um fio vertical denota o unitário que é aplicado quando o qubit de controlo leva o valor $1$.</span><span class="sxs-lookup"><span data-stu-id="502fe-146">Here the black circle denotes the quantum bit on which the gate is controlled and a vertical wire denotes the unitary that is applied when the control qubit takes the value $1$.</span></span>
<span data-ttu-id="502fe-147">Para os casos especiais em que $G=X$ e $G=Z$ introduzimos a seguinte notação para descrever a versão controlada dos portões (note que o portão controlado-X é o [portão $CNOT$](xref:microsoft.quantum.intrinsic.cnot)):</span><span class="sxs-lookup"><span data-stu-id="502fe-147">For the special cases where $G=X$ and $G=Z$ we introduce the following notation to describe the controlled version of the gates (note that the controlled-X gate is the [$CNOT$ gate](xref:microsoft.quantum.intrinsic.cnot)):</span></span>

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="502fe-148">Diagrama do Circuito ![para casos especiais de portões controlados](~/media/6.svg)</span><span class="sxs-lookup"><span data-stu-id="502fe-148">![Circuit diagram for special cases of controlled gates](~/media/6.svg)</span></span>

<span data-ttu-id="502fe-149">Q# fornece métodos para gerar automaticamente a versão controlada de uma operação, que evita que o programador tenha de codificar estas operações manualmente.</span><span class="sxs-lookup"><span data-stu-id="502fe-149">Q# provides methods to automatically generate the controlled version of an operation, which saves the programmer from having to hand code these operations.</span></span> <span data-ttu-id="502fe-150">Um exemplo disto é mostrado abaixo:</span><span class="sxs-lookup"><span data-stu-id="502fe-150">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a><span data-ttu-id="502fe-151">Operador de medição</span><span class="sxs-lookup"><span data-stu-id="502fe-151">Measurement operator</span></span>
<span data-ttu-id="502fe-152">A operação restante para visualizar em diagramas de circuitos é a medição.</span><span class="sxs-lookup"><span data-stu-id="502fe-152">The remaining operation to visualize in circuit diagrams is measurement.</span></span>
<span data-ttu-id="502fe-153">A medição tem um registo qubit, mede-o e produz o resultado como informação clássica.</span><span class="sxs-lookup"><span data-stu-id="502fe-153">Measurement takes a qubit register, measures it, and outputs the result as classical information.</span></span>
<span data-ttu-id="502fe-154">Uma operação de medição é denotada por um símbolo de contador e toma sempre como entrada um registo qubit (denotado por uma linha sólida) e produz informações clássicas (denotadas por uma linha dupla).</span><span class="sxs-lookup"><span data-stu-id="502fe-154">A measurement operation is denoted by a meter symbol and always takes as input a qubit register (denoted by a solid line) and outputs classical information (denoted by a double line).</span></span>
<span data-ttu-id="502fe-155">Especificamente, tal subcircuito parece:</span><span class="sxs-lookup"><span data-stu-id="502fe-155">Specifically, such a subcircuit looks like:</span></span>

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="502fe-156">Símbolo ![que representa uma operação de medição](~/media/7.svg)</span><span class="sxs-lookup"><span data-stu-id="502fe-156">![Symbol representing a measurement operation](~/media/7.svg)</span></span>

<span data-ttu-id="502fe-157">Q# implementa um operador de [medida](xref:microsoft.quantum.intrinsic.measure) para o efeito.</span><span class="sxs-lookup"><span data-stu-id="502fe-157">Q# implements a [Measure operator](xref:microsoft.quantum.intrinsic.measure) for this purpose.</span></span>
<span data-ttu-id="502fe-158">Consulte a [secção sobre medições](xref:microsoft.quantum.libraries.standard.prelude#measurements) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="502fe-158">See the [section on measurements](xref:microsoft.quantum.libraries.standard.prelude#measurements) for more information.</span></span>

<span data-ttu-id="502fe-159">Da mesma forma, o subcircuito</span><span class="sxs-lookup"><span data-stu-id="502fe-159">Similarly, the subcircuit</span></span>

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="502fe-160">Diagrama do Circuito ![que representa uma operação controlada](~/media/8.svg)</span><span class="sxs-lookup"><span data-stu-id="502fe-160">![Circuit diagram representing a controlled operation](~/media/8.svg)</span></span>

<span data-ttu-id="502fe-161">dá um portão controlado clássicamente, onde $G$ é aplicado condicionado na broca de controlo clássico sendo $1$.</span><span class="sxs-lookup"><span data-stu-id="502fe-161">gives a classically controlled gate, where $G$ is applied conditioned on the classical control bit being value $1$.</span></span>

## <a name="teleportation-circuit-diagram"></a><span data-ttu-id="502fe-162">Diagrama do circuito de teletransporte</span><span class="sxs-lookup"><span data-stu-id="502fe-162">Teleportation circuit diagram</span></span>
<span data-ttu-id="502fe-163">[A teleportação quântica](xref:microsoft.quantum.techniques.puttingittogether) é talvez o melhor algoritmo quântico para ilustrar estes componentes.</span><span class="sxs-lookup"><span data-stu-id="502fe-163">[Quantum teleportation](xref:microsoft.quantum.techniques.puttingittogether) is perhaps the best quantum algorithm for illustrating these components.</span></span>
<span data-ttu-id="502fe-164">A teleportação quântica é um método para mover dados dentro de um computador quântico (ou mesmo entre computadores quânticos distantes numa rede quântica) através do uso do emaranhado e da medição.</span><span class="sxs-lookup"><span data-stu-id="502fe-164">Quantum teleportation is a method for moving data within a quantum computer (or even between distant quantum computers in a quantum network) through the use of entanglement and measurement.</span></span>
<span data-ttu-id="502fe-165">Curiosamente, é realmente capaz de mover um estado quântico, digamos, o valor num determinado qubit, de um qubit para outro, sem sequer saber qual é o valor do qubit!</span><span class="sxs-lookup"><span data-stu-id="502fe-165">Interestingly, it is actually capable of moving a quantum state, say the value in a given qubit, from one qubit to another, without even knowing what the qubit's value is!</span></span>
<span data-ttu-id="502fe-166">Isto é necessário para que o protocolo funcione de acordo com as leis da Mecânica Quântica.</span><span class="sxs-lookup"><span data-stu-id="502fe-166">This is necessary for the protocol to work according to the laws of quantum mechanics.</span></span>
<span data-ttu-id="502fe-167">O circuito de teletransporte quântico é dado abaixo; também fornecemos uma versão anotada do circuito para ilustrar como ler o circuito quântico.</span><span class="sxs-lookup"><span data-stu-id="502fe-167">The quantum teleportation circuit is given below; we also provide an annotated version of the circuit to illustrate how to read the quantum circuit.</span></span>

<!--- ![](.\media\tp2.svg){ width=50% } --->
<span data-ttu-id="502fe-168">![circuito de teletransporte quântica](~/media/tp2.svg)</span><span class="sxs-lookup"><span data-stu-id="502fe-168">![Quantum teleportation circuit](~/media/tp2.svg)</span></span>
