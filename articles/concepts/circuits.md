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
# <a name="quantum-circuits"></a><span data-ttu-id="2ace0-103">Circuitos Quantum</span><span class="sxs-lookup"><span data-stu-id="2ace0-103">Quantum Circuits</span></span>
<span data-ttu-id="2ace0-104">Considere por um momento a transformação unitário $ \Text{CNOT} _{01}(H\otimes 1) $.</span><span class="sxs-lookup"><span data-stu-id="2ace0-104">Consider for a moment the unitary transformation $\text{ CNOT}_{01}(H\otimes 1)$.</span></span>
<span data-ttu-id="2ace0-105">Essa sequência de portão é de importância fundamental para a computação Quantum porque ela cria um estado confusas de duas qubit de maneira máxima:</span><span class="sxs-lookup"><span data-stu-id="2ace0-105">This gate sequence is of fundamental significance to quantum computing because it creates a maximally entangled two-qubit state:</span></span>

<span data-ttu-id="2ace0-106">$ $ \mathrm{CNOT}_{01}(H\otimes 1) \ket{00} = \frac{1}{\sqrt{2}} \left (\ket{00} + \ket{11} \right), $ $</span><span class="sxs-lookup"><span data-stu-id="2ace0-106">$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right),$$</span></span>

<span data-ttu-id="2ace0-107">As operações com essa ou mais complexidade são onipresentes em algoritmos Quantum e correção de erro Quantum, portanto, deve ser um grande alívio de que há um método simples para sua visualização chamada de *diagrama de circuito Quantum*.</span><span class="sxs-lookup"><span data-stu-id="2ace0-107">Operations with this or greater complexity are ubiquitous in quantum algorithms and quantum error correction, so it should come as a great relief that there is a simple method for their visualization called a *quantum circuit diagram*.</span></span>
<span data-ttu-id="2ace0-108">O diagrama de circuito para preparar esse estado de Quantum de confusas máximo é:</span><span class="sxs-lookup"><span data-stu-id="2ace0-108">The circuit diagram for preparing this maximally entangled quantum state is:</span></span>

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/Concepts1.png)

## <a name="quantum-circuit-diagram-conventions"></a><span data-ttu-id="2ace0-109">Convenções de diagrama de circuito Quantum</span><span class="sxs-lookup"><span data-stu-id="2ace0-109">Quantum circuit diagram conventions</span></span>
<span data-ttu-id="2ace0-110">Essa linguagem visual para operações Quantum pode ser mais prontamente fácil do que escrever sua matriz equivalente quando você entende as convenções para expressar um circuito Quantum.</span><span class="sxs-lookup"><span data-stu-id="2ace0-110">This visual language for quantum operations can be more readily digestible than writing down its equivalent matrix once you understand the conventions for expressing a quantum circuit.</span></span>
<span data-ttu-id="2ace0-111">Analisamos essas convenções abaixo.</span><span class="sxs-lookup"><span data-stu-id="2ace0-111">We review these conventions below.</span></span>

<span data-ttu-id="2ace0-112">Em um diagrama de circuito, cada linha sólida representa um qubit ou mais geralmente um registro de qubit.</span><span class="sxs-lookup"><span data-stu-id="2ace0-112">In a circuit diagram, each solid line depicts a qubit or more generally a qubit register.</span></span>
<span data-ttu-id="2ace0-113">Por convenção, a linha superior é o registro de qubit $0 $ e o resto é rotulado em sequência.</span><span class="sxs-lookup"><span data-stu-id="2ace0-113">By convention, the top line is qubit register $0$ and the remainder are labeled sequentially.</span></span> <span data-ttu-id="2ace0-114">O circuito de exemplo acima é representado como agindo em dois qubits (ou dois registros equivalentes que consistem em um qubit).</span><span class="sxs-lookup"><span data-stu-id="2ace0-114">The above example circuit is depicted as acting on two qubits (or equivalently two registers consisting of one qubit).</span></span>
<span data-ttu-id="2ace0-115">As Gates que atuam em um ou mais registros de qubit são indicadas como uma caixa.</span><span class="sxs-lookup"><span data-stu-id="2ace0-115">Gates acting on one or more qubit registers are denoted as a box.</span></span>
<span data-ttu-id="2ace0-116">Por exemplo, o símbolo</span><span class="sxs-lookup"><span data-stu-id="2ace0-116">For example, the symbol</span></span>

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_2.png)

<span data-ttu-id="2ace0-117">é o portão [Hadamard](xref:microsoft.quantum.primitive.h) que atua em um registro de qubit único.</span><span class="sxs-lookup"><span data-stu-id="2ace0-117">is the [Hadamard](xref:microsoft.quantum.primitive.h) gate acting on a single-qubit register.</span></span>

<span data-ttu-id="2ace0-118">As Gates da Quantum são ordenadas em ordem cronológica com a porta mais à esquerda como a portão aplicada pela primeira vez ao qubits.</span><span class="sxs-lookup"><span data-stu-id="2ace0-118">Quantum gates are ordered in chronological order with the left-most gate as the gate first applied to the qubits.</span></span>
<span data-ttu-id="2ace0-119">Em outras palavras, se você modelar os fios como tendo o estado Quantum, os fios trazem o estado da Quantum por meio de cada um dos Gates no diagrama da esquerda para a direita.</span><span class="sxs-lookup"><span data-stu-id="2ace0-119">In other words, if you picture the wires as holding the quantum state, the wires bring the quantum state through each of the gates in the diagram from left to right.</span></span>
<span data-ttu-id="2ace0-120">Isso é para dizer</span><span class="sxs-lookup"><span data-stu-id="2ace0-120">That is to say</span></span> 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_3.png)

<span data-ttu-id="2ace0-121">é a matriz unitário $CBA $.</span><span class="sxs-lookup"><span data-stu-id="2ace0-121">is the unitary matrix $CBA$.</span></span>
<span data-ttu-id="2ace0-122">A multiplicação de matriz obedece à Convenção oposta: a matriz mais à direita é aplicada primeiro.</span><span class="sxs-lookup"><span data-stu-id="2ace0-122">Matrix multiplication obeys the opposite convention: the right-most matrix is applied first.</span></span> <span data-ttu-id="2ace0-123">Em diagramas de circuito Quantum, no entanto, o portão mais à esquerda é aplicado primeiro.</span><span class="sxs-lookup"><span data-stu-id="2ace0-123">In quantum circuit diagrams, however, the left-most gate is applied first.</span></span>
<span data-ttu-id="2ace0-124">Essa diferença pode, às vezes, levar à confusão. portanto, é importante observar essa diferença significativa entre a notação linear algébricas e os diagramas de circuito Quantum.</span><span class="sxs-lookup"><span data-stu-id="2ace0-124">This difference can at times lead to confusion, so it is important to note this significant difference between the linear algebraic notation and quantum circuit diagrams.</span></span>

## <a name="inputs-and-outputs-of-quantum-circuits"></a><span data-ttu-id="2ace0-125">Entradas e saídas de circuitos Quantum</span><span class="sxs-lookup"><span data-stu-id="2ace0-125">Inputs and outputs of quantum circuits</span></span>
<span data-ttu-id="2ace0-126">Todos os exemplos anteriores que tinham tido exatamente o mesmo número de fios (qubits) de entrada para uma porta Quantum como o número de cabos do portão Quantum.</span><span class="sxs-lookup"><span data-stu-id="2ace0-126">All previous examples given have had precisely the same number of wires (qubits) input to a quantum gate as the number of wires out from the quantum gate.</span></span>
<span data-ttu-id="2ace0-127">A princípio, pode parecer razoável que os circuitos Quantum pudessem ter mais, ou menos, saídas do que as entradas em geral.</span><span class="sxs-lookup"><span data-stu-id="2ace0-127">It may at first seem reasonable that quantum circuits could have more, or fewer, outputs than inputs in general.</span></span>
<span data-ttu-id="2ace0-128">No entanto, isso é impossível, pois todas as operações de Quantum, salvar medida, são unitários e, portanto, reversível.</span><span class="sxs-lookup"><span data-stu-id="2ace0-128">This is impossible, however, because all quantum operations, save measurement, are unitary and hence reversible.</span></span>
<span data-ttu-id="2ace0-129">Se eles não tiverem o mesmo número de saídas que não seriam reversível e, portanto, não são unitários, o que é uma contradição.</span><span class="sxs-lookup"><span data-stu-id="2ace0-129">If they did not have the same number of outputs as inputs they would not be reversible and hence not unitary, which is a contradiction.</span></span>
<span data-ttu-id="2ace0-130">Por esse motivo, qualquer caixa desenhada em um diagrama de circuito deve ter precisamente o mesmo número de fios inserindo-o como sendo encerrado.</span><span class="sxs-lookup"><span data-stu-id="2ace0-130">For this reason any box drawn in a circuit diagram must have precisely the same number of wires entering it as exiting it.</span></span>

<span data-ttu-id="2ace0-131">Os diagramas de circuito qubit seguem convenções semelhantes para os qubit únicos.</span><span class="sxs-lookup"><span data-stu-id="2ace0-131">Multi-qubit circuit diagrams follow similar conventions to single-qubit ones.</span></span>
<span data-ttu-id="2ace0-132">Como um exemplo de esclarecimento, podemos definir uma operação qubit de dois unitários $B $ para ser $ (H S\otimes X) $ e expressar o circuito equivalentemente como</span><span class="sxs-lookup"><span data-stu-id="2ace0-132">As a clarifying example, we can define a two-qubit unitary operation $B$ to be $(H S\otimes X)$ and express the circuit equivalently as</span></span>

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_4.png)

<span data-ttu-id="2ace0-133">Também podemos exibir $B $ como tendo uma ação em um único registro de duas qubit em vez de registros de 2 1-qubit, dependendo do contexto no qual o circuito é usado.</span><span class="sxs-lookup"><span data-stu-id="2ace0-133">We can also view $B$ as having an action on a single two-qubit register rather than two one-qubit registers depending on the context in which the circuit is used.</span></span> <span data-ttu-id="2ace0-134">Talvez a propriedade mais útil desses diagramas de circuito abstrato seja que eles permitam que algoritmos de Quantum complicados sejam descritos em um alto nível sem precisar compilá-los em Gates fundamentais.</span><span class="sxs-lookup"><span data-stu-id="2ace0-134">Perhaps the most useful property of such abstract circuit diagrams is that they allow complicated quantum algorithms to be described at a high level without having to compile them down to fundamental gates.</span></span>
<span data-ttu-id="2ace0-135">Isso significa que você pode obter uma intuição sobre o fluxo de dados para um grande algoritmo Quantum sem a necessidade de entender todos os detalhes de como cada uma das sub-rotinas dentro do algoritmo funciona.</span><span class="sxs-lookup"><span data-stu-id="2ace0-135">This means that you can get an intuition about the data flow for a large quantum algorithm without needing to understand all the details of how each of the subroutines within the algorithm work.</span></span>

## <a name="controlled-gates"></a><span data-ttu-id="2ace0-136">Gates controlados</span><span class="sxs-lookup"><span data-stu-id="2ace0-136">Controlled gates</span></span>
<span data-ttu-id="2ace0-137">O outro constructo criado em diagramas de circuito Quantum qubit é Control.</span><span class="sxs-lookup"><span data-stu-id="2ace0-137">The other construct that is built into multi-qubit quantum circuit diagrams is control.</span></span>
<span data-ttu-id="2ace0-138">A ação de um portão controlado de Quantum singular, denotado $ \Lambda (G) $, em que um único valor de qubit controla o aplicativo de $G $, pode ser compreendido examinando o exemplo a seguir de uma entrada de estado do produto $ \Lambda (G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket {\ psi} $.</span><span class="sxs-lookup"><span data-stu-id="2ace0-138">The action of a quantum singly controlled gate, denoted $\Lambda(G)$, where a single qubit's value controls the application of $G$, can be understood by looking at the following example of a product state input $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket{\psi}$.</span></span>
<span data-ttu-id="2ace0-139">Ou seja, a porta controlada se aplica $G $ ao registro que contém $ \psi $ If e somente se o qubit de controle usa o valor $1 $.</span><span class="sxs-lookup"><span data-stu-id="2ace0-139">That is to say, the controlled gate applies $G$ to the register containing $\psi$ if and only if the control qubit takes the value $1$.</span></span>
<span data-ttu-id="2ace0-140">Em geral, descrevemos essas operações controladas em diagramas de circuito como</span><span class="sxs-lookup"><span data-stu-id="2ace0-140">In general, we describe such controlled operations in circuit diagrams as</span></span>

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_5.png)

<span data-ttu-id="2ace0-141">Aqui, o círculo preto denota o bit quântico no qual o portão é controlado e uma transmissão vertical denota o unitário que é aplicado quando o qubit de controle usa o valor $1 $.</span><span class="sxs-lookup"><span data-stu-id="2ace0-141">Here the black circle denotes the quantum bit on which the gate is controlled and a vertical wire denotes the unitary that is applied when the control qubit takes the value $1$.</span></span>
<span data-ttu-id="2ace0-142">Para os casos especiais em que $G = X $ e $G = Z $ apresentamos a notação a seguir para descrever a versão controlada das Gates (Observe que a porta X controlada é a [porta do $CNOT $](xref:microsoft.quantum.primitive.cnot)):</span><span class="sxs-lookup"><span data-stu-id="2ace0-142">For the special cases where $G=X$ and $G=Z$ we introduce the following notation to describe the controlled version of the gates (note that the controlled-X gate is the [$CNOT$ gate](xref:microsoft.quantum.primitive.cnot)):</span></span>

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_6.png)

<span data-ttu-id="2ace0-143">O Q # fornece métodos para gerar automaticamente a versão controlada de uma operação, o que evita que o programador tenha que codificar essas operações manualmente.</span><span class="sxs-lookup"><span data-stu-id="2ace0-143">Q# provides methods to automatically generate the controlled version of an operation, which saves the programmer from having to hand code these operations.</span></span> <span data-ttu-id="2ace0-144">Um exemplo disso é mostrado abaixo:</span><span class="sxs-lookup"><span data-stu-id="2ace0-144">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a><span data-ttu-id="2ace0-145">Operador de medida</span><span class="sxs-lookup"><span data-stu-id="2ace0-145">Measurement operator</span></span>
<span data-ttu-id="2ace0-146">A operação restante a ser visualizada em diagramas de circuito é medida.</span><span class="sxs-lookup"><span data-stu-id="2ace0-146">The remaining operation to visualize in circuit diagrams is measurement.</span></span>
<span data-ttu-id="2ace0-147">A medição usa um registro qubit, mede-o e gera o resultado como informações clássicas.</span><span class="sxs-lookup"><span data-stu-id="2ace0-147">Measurement takes a qubit register, measures it, and outputs the result as classical information.</span></span>
<span data-ttu-id="2ace0-148">Uma operação de medição é denotada por um símbolo de medidor e sempre usa como entrada um registro de qubit (indicado por uma linha sólida) e gera informações clássicas (indicadas por uma linha dupla).</span><span class="sxs-lookup"><span data-stu-id="2ace0-148">A measurement operation is denoted by a meter symbol and always takes as input a qubit register (denoted by a solid line) and outputs classical information (denoted by a double line).</span></span>
<span data-ttu-id="2ace0-149">Especificamente, esse subcircuito é semelhante a:</span><span class="sxs-lookup"><span data-stu-id="2ace0-149">Specifically, such a subcircuit looks like:</span></span>

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="2ace0-150">![circuito de medição](~/media/concepts_7.png)</span><span class="sxs-lookup"><span data-stu-id="2ace0-150">![Measurement circuit](~/media/concepts_7.png)</span></span>

<span data-ttu-id="2ace0-151">Q # implementa um [operador de medida](xref:microsoft.quantum.primitive.measure) para essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="2ace0-151">Q# implements a [Measure operator](xref:microsoft.quantum.primitive.measure) for this purpose.</span></span>
<span data-ttu-id="2ace0-152">Consulte a [seção sobre medições](xref:microsoft.quantum.libraries.standard.prelude#measurements) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="2ace0-152">See the [section on measurements](xref:microsoft.quantum.libraries.standard.prelude#measurements) for more information.</span></span>

<span data-ttu-id="2ace0-153">Da mesma forma, o subcircuito</span><span class="sxs-lookup"><span data-stu-id="2ace0-153">Similarly, the subcircuit</span></span>

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_8.png)

<span data-ttu-id="2ace0-154">fornece um portão controlado de forma clássica, em que $G $ é aplicado condicionalmente no bit de controle clássico sendo o valor de $1 $.</span><span class="sxs-lookup"><span data-stu-id="2ace0-154">gives a classically controlled gate, where $G$ is applied conditioned on the classical control bit being value $1$.</span></span>

## <a name="teleportation-circuit-diagram"></a><span data-ttu-id="2ace0-155">Diagrama de circuito de teleportação</span><span class="sxs-lookup"><span data-stu-id="2ace0-155">Teleportation circuit diagram</span></span>
<span data-ttu-id="2ace0-156">A [porta de transporte Quantum](xref:microsoft.quantum.techniques.puttingittogether) talvez seja o melhor algoritmo Quantum para ilustrar esses componentes.</span><span class="sxs-lookup"><span data-stu-id="2ace0-156">[Quantum teleportation](xref:microsoft.quantum.techniques.puttingittogether) is perhaps the best quantum algorithm for illustrating these components.</span></span>
<span data-ttu-id="2ace0-157">A teleportabilidade Quantum é um método para mover dados dentro de um computador Quantum (ou até mesmo entre computadores Quantum distantes em uma rede Quantum) por meio do uso de Entanglement e medição.</span><span class="sxs-lookup"><span data-stu-id="2ace0-157">Quantum teleportation is a method for moving data within a quantum computer (or even between distant quantum computers in a quantum network) through the use of entanglement and measurement.</span></span>
<span data-ttu-id="2ace0-158">Curiosamente, é realmente capaz de mover um estado Quantum, digamos o valor em um determinado qubit, de um qubit para outro, sem nem mesmo saber qual é o valor da qubit!</span><span class="sxs-lookup"><span data-stu-id="2ace0-158">Interestingly, it is actually capable of moving a quantum state, say the value in a given qubit, from one qubit to another, without even knowing what the qubit's value is!</span></span>
<span data-ttu-id="2ace0-159">Isso é necessário para que o protocolo funcione de acordo com as leis da mecânica quantum.</span><span class="sxs-lookup"><span data-stu-id="2ace0-159">This is necessary for the protocol to work according to the laws of quantum mechanics.</span></span>
<span data-ttu-id="2ace0-160">O circuito de teleportabilidade Quantum é fornecido abaixo; também fornecemos uma versão anotada do circuito para ilustrar como ler o circuito Quantum.</span><span class="sxs-lookup"><span data-stu-id="2ace0-160">The quantum teleportation circuit is given below; we also provide an annotated version of the circuit to illustrate how to read the quantum circuit.</span></span>

<!--- ![](.\media\tp2.svg){ width=50% } --->
![](~/media/concepts_tp2.png)
