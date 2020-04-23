---
title: Técnicas Q# - Juntar tudo
description: Caminhe por um programa básico de Q# que demonstre teletransporte quântico.
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4bd91699017e4c1acd9f4449b8a65e39bd07878e
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030570"
---
# <a name="putting-it-all-together-teleportation"></a><span data-ttu-id="64c03-103">Colocando tudo junto: Teleportation</span><span class="sxs-lookup"><span data-stu-id="64c03-103">Putting It All Together: Teleportation</span></span> #
<span data-ttu-id="64c03-104">Voltemos ao exemplo do circuito de teletransporte definido em [Circuitos Quânticos.](xref:microsoft.quantum.concepts.circuits)</span><span class="sxs-lookup"><span data-stu-id="64c03-104">Let's return to the example of the teleportation circuit defined in [Quantum Circuits](xref:microsoft.quantum.concepts.circuits).</span></span> <span data-ttu-id="64c03-105">Vamos usar isto para ilustrar os conceitos que aprendemos até agora.</span><span class="sxs-lookup"><span data-stu-id="64c03-105">We're going to use this to illustrate the concepts we've learned so far.</span></span> <span data-ttu-id="64c03-106">Uma explicação da teleportação quântica é fornecida abaixo para aqueles que não estão familiarizados com a teoria, seguido de uma passagem pela implementação do código em Q#.</span><span class="sxs-lookup"><span data-stu-id="64c03-106">An explanation of quantum teleportation is provided below for those who are unfamiliar with the theory, followed by a walkthrough of the code implementation in Q#.</span></span> 

## <a name="quantum-teleportation-theory"></a><span data-ttu-id="64c03-107">Teleportação Quântica: Teoria</span><span class="sxs-lookup"><span data-stu-id="64c03-107">Quantum Teleportation: Theory</span></span>
<span data-ttu-id="64c03-108">A teleportação quântica é uma técnica para o envio de um estado quântico desconhecido (a que nos referiremos como a '__mensagem__') de um qubit em um local para um qubit em outro local (vamos referir-nos a estes qubits como '__aqui__' e '__lá__', respectivamente).</span><span class="sxs-lookup"><span data-stu-id="64c03-108">Quantum teleportation is a technique for sending an unknown quantum state (which we'll refer to as the '__message__') from a qubit in one location to a qubit in another location (we'll refer to these qubits as '__here__' and '__there__', respectively).</span></span> <span data-ttu-id="64c03-109">Podemos representar a nossa __mensagem__ como um vetor usando a notação de Dirac:</span><span class="sxs-lookup"><span data-stu-id="64c03-109">We can represent our __message__ as a vector using Dirac notation:</span></span> 

<span data-ttu-id="64c03-110">$$ \ket{\psi} = \alpha\ket{0} +{1} \beta\ket $$</span><span class="sxs-lookup"><span data-stu-id="64c03-110">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="64c03-111">O estado do qubit da __mensagem__ é desconhecido para nós, uma vez que não sabemos os valores de $\alpha$ e $\beta$.</span><span class="sxs-lookup"><span data-stu-id="64c03-111">The __message__ qubit's state is unknown to us as we do not know the values of $\alpha$ and $\beta$.</span></span>

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="64c03-112">Passo 1: Criar um estado emaranhado</span><span class="sxs-lookup"><span data-stu-id="64c03-112">Step 1: Create an entangled state</span></span>
<span data-ttu-id="64c03-113">Para enviar a __mensagem,__ precisamos que o qubit __aqui__ seja enredado com o qubit __lá__.</span><span class="sxs-lookup"><span data-stu-id="64c03-113">In order to send the __message__ we need for the qubit __here__ to be entangled with the qubit __there__.</span></span> <span data-ttu-id="64c03-114">Isto é conseguido aplicando um portão Hadamard, seguido por um portão CNOT.</span><span class="sxs-lookup"><span data-stu-id="64c03-114">This is achieved by applying a Hadamard gate, followed by a CNOT gate.</span></span> <span data-ttu-id="64c03-115">Vamos ver as contas por detrás destas operações do portal.</span><span class="sxs-lookup"><span data-stu-id="64c03-115">Let's look at the math behind these gate operations.</span></span>

<span data-ttu-id="64c03-116">Começaremos com os qubits __aqui__ e __ali,__ ambos no estado de $\ket$.{0}</span><span class="sxs-lookup"><span data-stu-id="64c03-116">We will begin with the qubits __here__ and __there__ both in the $\ket{0}$ state.</span></span> <span data-ttu-id="64c03-117">Depois de envolver estes qubits, estão no estado:</span><span class="sxs-lookup"><span data-stu-id="64c03-117">After entangling these qubits, they are in the state:</span></span>

<span data-ttu-id="64c03-118">$$ \ket{\phi^+} ={1}\frac{2}{\sqrt{00} }(\ket + \ket{11}) $$</span><span class="sxs-lookup"><span data-stu-id="64c03-118">$$ \ket{\phi^+} = \frac{1}{\sqrt{2}}(\ket{00} + \ket{11}) $$</span></span>

### <a name="step-2-send-the-message"></a><span data-ttu-id="64c03-119">Passo 2: Enviar a mensagem</span><span class="sxs-lookup"><span data-stu-id="64c03-119">Step 2: Send the message</span></span>
<span data-ttu-id="64c03-120">Para enviar a __mensagem__ aplicamos primeiro um portão CNOT com o qubit da __mensagem__ e __aqui__ qubit como entradas (sendo o qubit da __mensagem__ o controlo e o qubit __aqui__ sendo o qubit alvo, neste caso).</span><span class="sxs-lookup"><span data-stu-id="64c03-120">To send the __message__ we first apply a CNOT gate with the __message__ qubit and __here__ qubit as inputs (the __message__ qubit being the control and the __here__ qubit being the target qubit, in this instance).</span></span> <span data-ttu-id="64c03-121">Este estado de entrada pode ser escrito:</span><span class="sxs-lookup"><span data-stu-id="64c03-121">This input state can be written:</span></span>

<span data-ttu-id="64c03-122">$$ \ket{\psi}\ket{\phi^+}{0} = (\alpha\ket +{1}\beta\ket )(\frac{1}{\sqrt{11}{2}}(\ket{00} + \ket)) $$</span><span class="sxs-lookup"><span data-stu-id="64c03-122">$$ \ket{\psi}\ket{\phi^+} = (\alpha\ket{0} + \beta\ket{1})(\frac{1}{\sqrt{2}}(\ket{00} + \ket{11})) $$</span></span>

<span data-ttu-id="64c03-123">Isto expande-se para:</span><span class="sxs-lookup"><span data-stu-id="64c03-123">This expands to:</span></span>

<span data-ttu-id="64c03-124">$${2}\ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{000} }\ket + \frac{\alpha}{{sqrt{2}}\ket \ \cet{2}{100} {2}{111} {011} {{\beta}{\sqrt }\ket + \frac{\beta}{{{{\sqrt</span><span class="sxs-lookup"><span data-stu-id="64c03-124">$$ \ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} + \frac{\beta}{\sqrt{2}}\ket{111} $$</span></span>

<span data-ttu-id="64c03-125">Como lembrete, o portão CNOT inverte o qubit do alvo quando o qubit de controlo é 1.</span><span class="sxs-lookup"><span data-stu-id="64c03-125">As a reminder, the CNOT gate flips the target qubit when the control qubit is 1.</span></span> <span data-ttu-id="64c03-126">Assim, por exemplo, uma entrada{000}de $\ket $ não resultará em nenhuma alteração, uma vez que o primeiro qubit (o controlo) é 0.</span><span class="sxs-lookup"><span data-stu-id="64c03-126">So for example, an input of $\ket{000}$ will result in no change as the first qubit (the control) is 0.</span></span> <span data-ttu-id="64c03-127">No entanto, tome um caso em que o primeiro qubit é 1 - por exemplo, uma entrada de $\ket{100}$.</span><span class="sxs-lookup"><span data-stu-id="64c03-127">However, take a case where the first qubit is 1 - for example an input of $\ket{100}$.</span></span> <span data-ttu-id="64c03-128">Neste caso, a saída é{110}$\ket $ como o segundo qubit (o alvo) é virado pelo portão CNOT.</span><span class="sxs-lookup"><span data-stu-id="64c03-128">In this instance, the output is $\ket{110}$ as the second qubit (the target) is flipped by the CNOT gate.</span></span>

<span data-ttu-id="64c03-129">Vamos agora considerar a nossa saída uma vez que o portão CNOT tenha agido na nossa entrada acima.</span><span class="sxs-lookup"><span data-stu-id="64c03-129">Let's now consider our output once the CNOT gate has acted on our input above.</span></span> <span data-ttu-id="64c03-130">O resultado é:</span><span class="sxs-lookup"><span data-stu-id="64c03-130">The result is:</span></span>

<span data-ttu-id="64c03-131">{2}$$ \frac{\alpha}{\sqrt }\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{{{{{{{\sqrt{2}}\ket{101} $$</span><span class="sxs-lookup"><span data-stu-id="64c03-131">$$ \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{\beta}{\sqrt{2}}\ket{101} $$</span></span>

<span data-ttu-id="64c03-132">O próximo passo para enviar a __mensagem__ é aplicar um portão Hadamard ao qubit da __mensagem__ (que é o primeiro qubit de cada termo).</span><span class="sxs-lookup"><span data-stu-id="64c03-132">The next step to send the __message__ is to apply a Hadamard gate to the __message__ qubit (that's the first qubit of each term).</span></span> 

<span data-ttu-id="64c03-133">Como lembrete, o portão hadamard faz o seguinte:</span><span class="sxs-lookup"><span data-stu-id="64c03-133">As a reminder, the Hadamard gate does the following:</span></span>

<span data-ttu-id="64c03-134">Input</span><span class="sxs-lookup"><span data-stu-id="64c03-134">Input</span></span> | <span data-ttu-id="64c03-135">Saída</span><span class="sxs-lookup"><span data-stu-id="64c03-135">Output</span></span>
---------------------------| ---------------------------------------------------------------
<span data-ttu-id="64c03-136">$\ket{0}$</span><span class="sxs-lookup"><span data-stu-id="64c03-136">$\ket{0}$</span></span>  | <span data-ttu-id="64c03-137">$\frac{1}{\sqrt{2}}(\ket{0} {1}+ \ket )$</span><span class="sxs-lookup"><span data-stu-id="64c03-137">$\frac{1}{\sqrt{2}}(\ket{0} + \ket{1})$</span></span>
<span data-ttu-id="64c03-138">$\ket{1}$</span><span class="sxs-lookup"><span data-stu-id="64c03-138">$\ket{1}$</span></span>  | <span data-ttu-id="64c03-139">$\frac{1}{\sqrt{2}}(\ket{0} {1}- \ket )$</span><span class="sxs-lookup"><span data-stu-id="64c03-139">$\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})$</span></span>

<span data-ttu-id="64c03-140">Se aplicarmos o portão Hadamard ao primeiro qubit de cada termo da nossa saída acima, obtemos o seguinte resultado:</span><span class="sxs-lookup"><span data-stu-id="64c03-140">If we apply the Hadamard gate to the first qubit of each term of our output above, we get the following result:</span></span>

<span data-ttu-id="64c03-141">{2}$$ \frac{\alfa}{\sqrt }(\frac{1}{\sqrt{2}{0} }(\ket +{00} \ket))\ket{2}{1}{2}{0} {1}{11} {2}{1}{2}{0} {1}{10} {2}{1}{1}+ \frac{\alpha}{\sqrt (\frac {\sqrt }(\ket + \ket)\ket + \frac{\beta}{\sqrt }(\frac {\sqrt }(\ket - \ket))\ket + \frac{\beta}{\sqrt }(\frac {\sqrt{2}}(\ket{0} - \ket)\ket{1}{01} $$</span><span class="sxs-lookup"><span data-stu-id="64c03-141">$$ \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{00} + \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{11} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{10} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{01} $$</span></span>

<span data-ttu-id="64c03-142">Note que cada termo tem{1}dois fatores{2}$\frac {\sqrt }$ .</span><span class="sxs-lookup"><span data-stu-id="64c03-142">Note that each term has two $\frac{1}{\sqrt{2}}$ factors.</span></span> <span data-ttu-id="64c03-143">Podemos multiplicá-los dando o seguinte resultado:</span><span class="sxs-lookup"><span data-stu-id="64c03-143">We can multiply these out giving the following result:</span></span>

<span data-ttu-id="64c03-144">$${2}\frac{\alpha}{0} (\ket{1}+ \ket )\ket{00} +{2}\frac{\alpha} (\ket{0} + \ket{1}\ket{11} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{10} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{01} $$</span><span class="sxs-lookup"><span data-stu-id="64c03-144">$$ \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{11} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{10} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{01} $$</span></span>

<span data-ttu-id="64c03-145">O fator{1}{2}$\frac $ é comum a cada termo para que possamos agora levá-lo para fora dos suportes:</span><span class="sxs-lookup"><span data-stu-id="64c03-145">The  $\frac{1}{2}$ factor is common to each term so we can now take it outside the brackets:</span></span>

<span data-ttu-id="64c03-146">$${1}{2}\frac{0} \big[\alpha(\ket{1}+ \ket )\ket{00} {0} + \alpha(\ket + \ket{1})\ket{11} + \beta(\ket{0} -{1}\ket )\ket{10} + \beta(\ket{0} - \ket{1})\ket \ket{01}\big] $$</span><span class="sxs-lookup"><span data-stu-id="64c03-146">$$ \frac{1}{2}\big[\alpha(\ket{0} + \ket{1})\ket{00} + \alpha(\ket{0} + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket{01}\big] $$</span></span>

<span data-ttu-id="64c03-147">Podemos então multiplicar os suportes para cada termo que dá:</span><span class="sxs-lookup"><span data-stu-id="64c03-147">We can then multiply out the brackets for each term giving:</span></span>

<span data-ttu-id="64c03-148">$${1}{2}\frac \big[\alfa\ket{000} +{100} \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} -{110} \beta\ket{001} + \beta\ket + \beta\ket - \beta\ket - \beta\ket{101}\big] $$</span><span class="sxs-lookup"><span data-stu-id="64c03-148">$$ \frac{1}{2}\big[\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} - \beta\ket{110} + \beta\ket{001} - \beta\ket{101}\big] $$</span></span>

### <a name="step-3-measure-the-result"></a><span data-ttu-id="64c03-149">Passo 3: Medir o resultado</span><span class="sxs-lookup"><span data-stu-id="64c03-149">Step 3: Measure the result</span></span>

<span data-ttu-id="64c03-150">Devido a __aqui__ e __ali__ estarem emaranhados, qualquer medição __aqui__ afetará o estado de __lá.__</span><span class="sxs-lookup"><span data-stu-id="64c03-150">Due to __here__ and __there__ being entangled, any measurement on __here__ will affect the state of __there__.</span></span> <span data-ttu-id="64c03-151">Se medirmos o primeiro e o segundo qubit __(mensagem__ e __aqui)__ podemos saber em que estado __existe,__ devido a esta propriedade de emaranhado.</span><span class="sxs-lookup"><span data-stu-id="64c03-151">If we measure the first and second qubit (__message__ and __here__) we can learn what state __there__ is in, due to this property of entanglement.</span></span> 

* <span data-ttu-id="64c03-152">Se medirmos e conseguirmos um resultado 00, a superposição entra em colapso, deixando apenas termos consistentes com este resultado.</span><span class="sxs-lookup"><span data-stu-id="64c03-152">If we measure and get a result 00, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="64c03-153">São $\alpha\ket{000} +\beta\ket{001}$.</span><span class="sxs-lookup"><span data-stu-id="64c03-153">That's $\alpha\ket{000} +\beta\ket{001}$.</span></span> <span data-ttu-id="64c03-154">Isto pode ser refactored{00}para $\ket{0} (\alpha\ket +\beta\ket{1})$.</span><span class="sxs-lookup"><span data-stu-id="64c03-154">This can be refactored to $\ket{00}(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="64c03-155">Portanto, se medirmos o primeiro e o segundo qubit para ser 00, sabemos que o terceiro{0} qubit,{1} __lá,__ está no estado $(\alpha\ket +\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="64c03-155">Therefore if we measure the first and second qubit to be 00, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="64c03-156">Se medirmos e conseguirmos um resultado 01, a superposição entra em colapso, deixando apenas termos consistentes com este resultado.</span><span class="sxs-lookup"><span data-stu-id="64c03-156">If we measure and get a result 01, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="64c03-157">São $\alpha\ket{011} +\beta\ket{010}$.</span><span class="sxs-lookup"><span data-stu-id="64c03-157">That's $\alpha\ket{011} +\beta\ket{010}$.</span></span> <span data-ttu-id="64c03-158">Isto pode ser refactored{01}para $\ket{1} (\alpha\ket +\beta\ket{0})$.</span><span class="sxs-lookup"><span data-stu-id="64c03-158">This can be refactored to $\ket{01}(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="64c03-159">Portanto, se medirmos o primeiro e o segundo qubit para ser 01, sabemos que o terceiro{1} qubit,{0} __lá,__ está no estado $(\alpha\ket +\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="64c03-159">Therefore if we measure the first and second qubit to be 01, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span>
* <span data-ttu-id="64c03-160">Se medirmos e conseguirmos um resultado 10, a superposição entra em colapso, deixando apenas termos consistentes com este resultado.</span><span class="sxs-lookup"><span data-stu-id="64c03-160">If we measure and get a result 10, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="64c03-161">São $\alfa\ket{100} -\beta\ket{101}$.</span><span class="sxs-lookup"><span data-stu-id="64c03-161">That's $\alpha\ket{100} -\beta\ket{101}$.</span></span> <span data-ttu-id="64c03-162">Isto pode ser refactored{10}para $\ket{0} (\alpha\ket -\beta\ket{1})$.</span><span class="sxs-lookup"><span data-stu-id="64c03-162">This can be refactored to $\ket{10}(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="64c03-163">Portanto, se medirmos o primeiro e o segundo qubit para ser 10, sabemos que o terceiro{0} qubit,{1} __lá,__ está no estado $(\alpha\ket -\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="64c03-163">Therefore if we measure the first and second qubit to be 10, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span>
* <span data-ttu-id="64c03-164">Se medirmos e conseguirmos um resultado 11, a superposição entra em colapso, deixando apenas termos consistentes com este resultado.</span><span class="sxs-lookup"><span data-stu-id="64c03-164">If we measure and get a result 11, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="64c03-165">São $\alfa\ket{111} -\beta\ket{110}$.</span><span class="sxs-lookup"><span data-stu-id="64c03-165">That's $\alpha\ket{111} -\beta\ket{110}$.</span></span> <span data-ttu-id="64c03-166">Isto pode ser refactored{11}para $\ket{1} (\alpha\ket -\beta\ket{0})$.</span><span class="sxs-lookup"><span data-stu-id="64c03-166">This can be refactored to $\ket{11}(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="64c03-167">Portanto, se medirmos o primeiro e o segundo qubit para ser 11, sabemos que o terceiro{1} qubit,{0} __lá,__ está no estado $(\alpha\ket -\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="64c03-167">Therefore if we measure the first and second qubit to be 11, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span>

### <a name="step-4-interpret-the-result"></a><span data-ttu-id="64c03-168">Passo 4: Interpretar o resultado</span><span class="sxs-lookup"><span data-stu-id="64c03-168">Step 4: Interpret the result</span></span>

<span data-ttu-id="64c03-169">Como lembrete, a __mensagem__ original que queríamos enviar era:</span><span class="sxs-lookup"><span data-stu-id="64c03-169">As a reminder, the original __message__ we wished to send was:</span></span>

<span data-ttu-id="64c03-170">$$ \ket{\psi} = \alpha\ket{0} +{1} \beta\ket $$</span><span class="sxs-lookup"><span data-stu-id="64c03-170">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="64c03-171">Precisamos de colocar o qubit __lá__ neste estado, para que o estado recebido seja o pretendido.</span><span class="sxs-lookup"><span data-stu-id="64c03-171">We need to get the __there__ qubit into this state, so that the received state is the one that was intended.</span></span> 

* <span data-ttu-id="64c03-172">Se medimos e obtivemos um resultado de 00, então o terceiro qubit, __lá, está__no estado $(\alfa\ket{0} +\beta\ket{1})$.</span><span class="sxs-lookup"><span data-stu-id="64c03-172">If we measured and got a result of 00, then the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="64c03-173">Como esta é a __mensagem__pretendida, não é necessária qualquer alteração.</span><span class="sxs-lookup"><span data-stu-id="64c03-173">As this is the intended __message__, no alteration is required.</span></span>
* <span data-ttu-id="64c03-174">Se medimos e obtivemos um resultado de 01, então o terceiro qubit, __lá, está__no estado $(\alfa\ket{1} +\beta\ket{0})$.</span><span class="sxs-lookup"><span data-stu-id="64c03-174">If we measured and got a result of 01, then the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="64c03-175">Isto difere da __mensagem__pretendida, no entanto, aplicar um portão NOT{0} dá-nos{1}o estado desejado $(\alpha\ket +\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="64c03-175">This differs from the intended __message__, however applying a NOT gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="64c03-176">Se medimos e obtivemos um resultado de 10, então o terceiro qubit, __lá, está__no estado $(\alpha\ket{0} -\beta\ket{1})$.</span><span class="sxs-lookup"><span data-stu-id="64c03-176">If we measured and got a result of 10, then the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="64c03-177">Isto difere da __mensagem__pretendida, no entanto, aplicar um portão Z{0} dá-nos{1}o estado desejado $(\alpha\ket +\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="64c03-177">This differs from the intended __message__, however applying a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="64c03-178">Se medimos e obtivemos um resultado de 11, então o terceiro qubit, __lá, está__no estado $(\alpha\ket{1} -\beta\ket{0})$.</span><span class="sxs-lookup"><span data-stu-id="64c03-178">If we measured and got a result of 11, then the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="64c03-179">Isto difere da __mensagem__pretendida, no entanto, aplicar um portão NOT seguido por{0} um portão Z{1}dá-nos o estado desejado $(\alpha\ket +\beta\ket )$.</span><span class="sxs-lookup"><span data-stu-id="64c03-179">This differs from the intended __message__, however applying a NOT gate followed by a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>

<span data-ttu-id="64c03-180">Resumindo, se medirmos e o primeiro qubit for 1, é aplicado um portão Z.</span><span class="sxs-lookup"><span data-stu-id="64c03-180">To summarize, if we measure and the first qubit is 1, a Z gate is applied.</span></span> <span data-ttu-id="64c03-181">Se medirmos e o segundo qubit for 1, aplica-se um portão NOT.</span><span class="sxs-lookup"><span data-stu-id="64c03-181">If we measure and the second qubit is 1, a NOT gate is applied.</span></span>

### <a name="summary"></a><span data-ttu-id="64c03-182">Resumo</span><span class="sxs-lookup"><span data-stu-id="64c03-182">Summary</span></span>
<span data-ttu-id="64c03-183">Abaixo é apresentado um circuito quântico de livro de texto que implementa a teleportação.</span><span class="sxs-lookup"><span data-stu-id="64c03-183">Shown below is a text-book quantum circuit that implements the teleportation.</span></span> <span data-ttu-id="64c03-184">Movendo-se da esquerda para a direita, pode ver:</span><span class="sxs-lookup"><span data-stu-id="64c03-184">Moving from left to right you can see:</span></span>
- <span data-ttu-id="64c03-185">Passo 1: Entrelaçar __aqui__ e __ali__ aplicando um portão Hadamard e portão CNOT.</span><span class="sxs-lookup"><span data-stu-id="64c03-185">Step 1: Entangling __here__ and __there__ by applying a Hadamard gate and CNOT gate.</span></span>
- <span data-ttu-id="64c03-186">Passo 2: Envio da __mensagem__ utilizando um portão CNOT e um portão Hadamard.</span><span class="sxs-lookup"><span data-stu-id="64c03-186">Step 2: Sending the __message__ using a CNOT gate and a Hadamard gate.</span></span>
- <span data-ttu-id="64c03-187">Passo 3: Medição do primeiro e segundo qubits, __mensagem__ e __aqui__.</span><span class="sxs-lookup"><span data-stu-id="64c03-187">Step 3: Taking a measurement of the first and second qubits, __message__ and __here__.</span></span>
- <span data-ttu-id="64c03-188">Passo 4: Aplicação de um portão NOT ou de um portão Z, dependendo do resultado da medição no passo 3.</span><span class="sxs-lookup"><span data-stu-id="64c03-188">Step 4: Applying a NOT gate or a Z gate, depending on the result of the measurement in step 3.</span></span>

![«Teleport (msg: Qubit, ali: Qubit) : Unidade»](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a><span data-ttu-id="64c03-190">Teletransporte Quântico: Código</span><span class="sxs-lookup"><span data-stu-id="64c03-190">Quantum Teleportation: Code</span></span>

<span data-ttu-id="64c03-191">Temos o nosso circuito de teletransporte quântico:</span><span class="sxs-lookup"><span data-stu-id="64c03-191">We have our circuit for quantum teleportation:</span></span>

![«Teleport (msg: Qubit, ali: Qubit) : Unidade»](~/media/teleportation.svg)

<span data-ttu-id="64c03-193">Podemos agora traduzir cada um dos passos deste circuito quântico em Q#.</span><span class="sxs-lookup"><span data-stu-id="64c03-193">We can now translate each of the steps in this quantum circuit into Q#.</span></span>

### <a name="step-0-definition"></a><span data-ttu-id="64c03-194">Passo 0: Definição</span><span class="sxs-lookup"><span data-stu-id="64c03-194">Step 0: Definition</span></span>
<span data-ttu-id="64c03-195">Quando executamos teletransporte, temos de saber a __mensagem__ que queremos enviar, e para onde queremos enviá-la __(lá).__</span><span class="sxs-lookup"><span data-stu-id="64c03-195">When we perform teleportation, we must know the __message__ we wish to send, and where we wish to send it (__there__).</span></span> <span data-ttu-id="64c03-196">Por esta razão, começamos por definir uma nova operação teleport que `msg` `there`é dada a dois qubits como argumentos, e:</span><span class="sxs-lookup"><span data-stu-id="64c03-196">For this reason, we begin by defining a new Teleport operation that is given two qubits as arguments, `msg` and `there`:</span></span>

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

<span data-ttu-id="64c03-197">Precisamos também de atribuir `here` um qubit `using` que conseguimos com um bloco:</span><span class="sxs-lookup"><span data-stu-id="64c03-197">We also need to allocate a qubit `here` which we achieve with a `using` block:</span></span>

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="64c03-198">Passo 1: Criar um estado emaranhado</span><span class="sxs-lookup"><span data-stu-id="64c03-198">Step 1: Create an entangled state</span></span>
<span data-ttu-id="64c03-199">Podemos então criar o `here` `there` par emaranhado @"microsoft.quantum.intrinsic.h" @"microsoft.quantum.intrinsic.cnot" entre e usando as e operações:</span><span class="sxs-lookup"><span data-stu-id="64c03-199">We can then create the entangled pair between `here` and `there` by using the @"microsoft.quantum.intrinsic.h" and @"microsoft.quantum.intrinsic.cnot" operations:</span></span>

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a><span data-ttu-id="64c03-200">Passo 2: Enviar a mensagem</span><span class="sxs-lookup"><span data-stu-id="64c03-200">Step 2: Send the message</span></span>
<span data-ttu-id="64c03-201">Em seguida, usamos o próximo nome de $\operador{CNOT}$ e $H$ portões para mover o qubit da nossa mensagem:</span><span class="sxs-lookup"><span data-stu-id="64c03-201">We then use the next $\operatorname{CNOT}$ and $H$ gates to move our message qubit:</span></span>

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a><span data-ttu-id="64c03-202">Passo 3 & 4: Medir e interpretar o resultado</span><span class="sxs-lookup"><span data-stu-id="64c03-202">Step 3 & 4: Measuring and interpreting the result</span></span>
<span data-ttu-id="64c03-203">Finalmente, usamos @"microsoft.quantum.intrinsic.m" para realizar as medições e realizar as operações necessárias para `if` obter o estado desejado, conforme denotado por declarações:</span><span class="sxs-lookup"><span data-stu-id="64c03-203">Finally, we use @"microsoft.quantum.intrinsic.m" to perform the measurements and perform the necessary gate operations to get the desired state, as denoted by `if` statements:</span></span>

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

### <a name="step-5-restarting-the-qubit-register"></a><span data-ttu-id="64c03-204">Passo 5: Reiniciar o registo qubit</span><span class="sxs-lookup"><span data-stu-id="64c03-204">Step 5: Restarting the qubit register</span></span>

<span data-ttu-id="64c03-205">No final de cada operação q# precisamos deixar os qubits no estado $\ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="64c03-205">At the end of every Q# operation we need to let the qubits in the state $\ket{0}$.</span></span> <span data-ttu-id="64c03-206">Podemos @"microsoft.quantum.intrinsic.reset" usar para reiniciar todos os qubits para o estado zero e isso terminará a nossa operação.</span><span class="sxs-lookup"><span data-stu-id="64c03-206">We can use @"microsoft.quantum.intrinsic.reset" to restart all the qubits to the zero state and this will finish our operation.</span></span>

```qsharp
        Reset(msg);
        Reset(here);
        Reset(there);
    }
}
```


