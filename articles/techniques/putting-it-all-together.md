---
title: 'Técnicas de Q # – reunindo todas elas | Microsoft Docs'
description: 'Técnicas de Q #-reunindo tudo'
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: f65b3e260f98a7a90da13b62edd6cc63d200f5af
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183272"
---
# <a name="putting-it-all-together-teleportation"></a><span data-ttu-id="3be60-103">Juntando tudo: Teleportation</span><span class="sxs-lookup"><span data-stu-id="3be60-103">Putting it All Together: Teleportation</span></span> #
<span data-ttu-id="3be60-104">Vamos retornar ao exemplo do circuito de Teleportation definido em [circuitos Quantum](xref:microsoft.quantum.concepts.circuits).</span><span class="sxs-lookup"><span data-stu-id="3be60-104">Let's return to the example of the teleportation circuit defined in [Quantum Circuits](xref:microsoft.quantum.concepts.circuits).</span></span> <span data-ttu-id="3be60-105">Vamos usar isso para ilustrar os conceitos que aprendemos até agora.</span><span class="sxs-lookup"><span data-stu-id="3be60-105">We're going to use this to illustrate the concepts we've learned so far.</span></span> <span data-ttu-id="3be60-106">Uma explicação sobre a teleportação Quantum é fornecida abaixo para aqueles que não estão familiarizados com a teoria, seguidos por uma explicação da implementação do código em Q #.</span><span class="sxs-lookup"><span data-stu-id="3be60-106">An explanation of quantum teleportation is provided below for those who are unfamiliar with the theory, followed by a walkthrough of the code implementation in Q#.</span></span> 

## <a name="quantum-teleportation-theory"></a><span data-ttu-id="3be60-107">Portabilidade Quantum: teoria</span><span class="sxs-lookup"><span data-stu-id="3be60-107">Quantum Teleportation: Theory</span></span>
<span data-ttu-id="3be60-108">A teleportabilidade Quantum é uma técnica para enviar um estado de Quantum desconhecido (que iremos nos referir como "__Message__") de um qubit em um local para um qubit em outro local (vamos nos referir a esses qubits como "__aqui__" e "__lá__", respectivamente).</span><span class="sxs-lookup"><span data-stu-id="3be60-108">Quantum teleportation is a technique for sending an unknown quantum state (which we'll refer to as the '__message__') from a qubit in one location to a qubit in another location (we'll refer to these qubits as '__here__' and '__there__', respectively).</span></span> <span data-ttu-id="3be60-109">Podemos representar nossa __mensagem__ como um vetor usando a notação Dirac:</span><span class="sxs-lookup"><span data-stu-id="3be60-109">We can represent our __message__ as a vector using Dirac notation:</span></span> 

<span data-ttu-id="3be60-110">$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $</span><span class="sxs-lookup"><span data-stu-id="3be60-110">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="3be60-111">O estado da __mensagem__ qubit é desconhecido para nós, pois não sabemos os valores de $ \alpha $ e $ \beta $.</span><span class="sxs-lookup"><span data-stu-id="3be60-111">The __message__ qubit's state is unknown to us as we do not know the values of $\alpha$ and $\beta$.</span></span>

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="3be60-112">Etapa 1: criar um estado de confusas</span><span class="sxs-lookup"><span data-stu-id="3be60-112">Step 1: Create an entangled state</span></span>
<span data-ttu-id="3be60-113">Para enviar a __mensagem__ , precisamos que o qubit __aqui__ seja confusas com o qubit __lá__.</span><span class="sxs-lookup"><span data-stu-id="3be60-113">In order to send the __message__ we need for the qubit __here__ to be entangled with the qubit __there__.</span></span> <span data-ttu-id="3be60-114">Isso é obtido com a aplicação de um portão Hadamard, seguido por um portão CNOT.</span><span class="sxs-lookup"><span data-stu-id="3be60-114">This is achieved by applying a Hadamard gate, followed by a CNOT gate.</span></span> <span data-ttu-id="3be60-115">Vamos examinar a matemática por trás dessas operações de portão.</span><span class="sxs-lookup"><span data-stu-id="3be60-115">Let's look at the math behind these gate operations.</span></span>

<span data-ttu-id="3be60-116">Começaremos com o qubits __aqui__ e __lá__ no estado $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="3be60-116">We will begin with the qubits __here__ and __there__ both in the $\ket{0}$ state.</span></span> <span data-ttu-id="3be60-117">Depois de Entangling esses qubits, eles estão no estado:</span><span class="sxs-lookup"><span data-stu-id="3be60-117">After entangling these qubits, they are in the state:</span></span>

<span data-ttu-id="3be60-118">$ $ \ket{\phi ^ +} = \frac{1}{\sqrt{2}} (\ket{00} + \ket{11}) $ $</span><span class="sxs-lookup"><span data-stu-id="3be60-118">$$ \ket{\phi^+} = \frac{1}{\sqrt{2}}(\ket{00} + \ket{11}) $$</span></span>

### <a name="step-2-send-the-message"></a><span data-ttu-id="3be60-119">Etapa 2: enviar a mensagem</span><span class="sxs-lookup"><span data-stu-id="3be60-119">Step 2: Send the message</span></span>
<span data-ttu-id="3be60-120">Para enviar a __mensagem__ , primeiro aplicamos um portão CNOT com a __mensagem__ qubit e __aqui__ qubit como entradas (a __mensagem__ qubit sendo o controle e __aqui__ qubit sendo a qubit de destino, nesta instância).</span><span class="sxs-lookup"><span data-stu-id="3be60-120">To send the __message__ we first apply a CNOT gate with the __message__ qubit and __here__ qubit as inputs (the __message__ qubit being the control and the __here__ qubit being the target qubit, in this instance).</span></span> <span data-ttu-id="3be60-121">Esse estado de entrada pode ser escrito:</span><span class="sxs-lookup"><span data-stu-id="3be60-121">This input state can be written:</span></span>

<span data-ttu-id="3be60-122">$ $ \ket{\psi}\ket{\phi ^ +} = (\alpha\ket{0} + \beta\ket{1}) (\frac{1}{\sqrt{2}} (\ket{00} + \ket{11})) $ $</span><span class="sxs-lookup"><span data-stu-id="3be60-122">$$ \ket{\psi}\ket{\phi^+} = (\alpha\ket{0} + \beta\ket{1})(\frac{1}{\sqrt{2}}(\ket{00} + \ket{11})) $$</span></span>

<span data-ttu-id="3be60-123">Isso expande para:</span><span class="sxs-lookup"><span data-stu-id="3be60-123">This expands to:</span></span>

<span data-ttu-id="3be60-124">$ $ \ket{\psi}\ket{\phi ^ +} = \frac{\alpha}{\sqrt{2}} \ket{000} + \frac{\alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{100} + \frac{\beta}{\sqrt{2}} \ket{111} $ $</span><span class="sxs-lookup"><span data-stu-id="3be60-124">$$ \ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} + \frac{\beta}{\sqrt{2}}\ket{111} $$</span></span>

<span data-ttu-id="3be60-125">Como lembrete, a porta CNOT inverte o qubit de destino quando o qubit de controle é 1.</span><span class="sxs-lookup"><span data-stu-id="3be60-125">As a reminder, the CNOT gate flips the target qubit when the control qubit is 1.</span></span> <span data-ttu-id="3be60-126">Por exemplo, uma entrada de $ \ket{000}$ não resultará em nenhuma alteração, pois o primeiro qubit (o controle) é 0.</span><span class="sxs-lookup"><span data-stu-id="3be60-126">So for example, an input of $\ket{000}$ will result in no change as the first qubit (the control) is 0.</span></span> <span data-ttu-id="3be60-127">No entanto, faça um caso em que a primeira qubit é 1, por exemplo, uma entrada de $ \ket{100}$.</span><span class="sxs-lookup"><span data-stu-id="3be60-127">However, take a case where the first qubit is 1 - for example an input of $\ket{100}$.</span></span> <span data-ttu-id="3be60-128">Nessa instância, a saída é $ \ket{110}$, pois o segundo qubit (o destino) é invertido pelo portão CNOT.</span><span class="sxs-lookup"><span data-stu-id="3be60-128">In this instance, the output is $\ket{110}$ as the second qubit (the target) is flipped by the CNOT gate.</span></span>

<span data-ttu-id="3be60-129">Agora, vamos considerar nossa saída depois que a porta CNOT tiver atuado em nossa entrada acima.</span><span class="sxs-lookup"><span data-stu-id="3be60-129">Let's now consider our output once the CNOT gate has acted on our input above.</span></span> <span data-ttu-id="3be60-130">O resultado é:</span><span class="sxs-lookup"><span data-stu-id="3be60-130">The result is:</span></span>

<span data-ttu-id="3be60-131">$ $ \frac{\alpha}{\sqrt{2}} \ket{000} + \frac{\alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{110} + \frac{\beta}{\sqrt{2}} \ket{101} $ $</span><span class="sxs-lookup"><span data-stu-id="3be60-131">$$ \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{\beta}{\sqrt{2}}\ket{101} $$</span></span>

<span data-ttu-id="3be60-132">A próxima etapa para enviar a __mensagem__ é aplicar um portão Hadamard à __mensagem__ qubit (que é a primeira qubit de cada termo).</span><span class="sxs-lookup"><span data-stu-id="3be60-132">The next step to send the __message__ is to apply a Hadamard gate to the __message__ qubit (that's the first qubit of each term).</span></span> 

<span data-ttu-id="3be60-133">Como lembrete, o portão Hadamard faz o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3be60-133">As a reminder, the Hadamard gate does the following:</span></span>

<span data-ttu-id="3be60-134">Input</span><span class="sxs-lookup"><span data-stu-id="3be60-134">Input</span></span> | <span data-ttu-id="3be60-135">Saída</span><span class="sxs-lookup"><span data-stu-id="3be60-135">Output</span></span>
---------------------------| ---------------------------------------------------------------
<span data-ttu-id="3be60-136">$ \ket{0}$</span><span class="sxs-lookup"><span data-stu-id="3be60-136">$\ket{0}$</span></span>  | <span data-ttu-id="3be60-137">$ \frac{1}{\sqrt{2}} (\ket{0} + \ket{1}) $</span><span class="sxs-lookup"><span data-stu-id="3be60-137">$\frac{1}{\sqrt{2}}(\ket{0} + \ket{1})$</span></span>
<span data-ttu-id="3be60-138">$ \ket{1}$</span><span class="sxs-lookup"><span data-stu-id="3be60-138">$\ket{1}$</span></span>  | <span data-ttu-id="3be60-139">$ \frac{1}{\sqrt{2}} (\ket{0}-\ket{1}) $</span><span class="sxs-lookup"><span data-stu-id="3be60-139">$\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})$</span></span>

<span data-ttu-id="3be60-140">Se aplicarmos o portão Hadamard à primeira qubit de cada termo de nossa saída acima, obteremos o seguinte resultado:</span><span class="sxs-lookup"><span data-stu-id="3be60-140">If we apply the Hadamard gate to the first qubit of each term of our output above, we get the following result:</span></span>

<span data-ttu-id="3be60-141">$ $ \frac{\alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{00} + \frac{\alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{11} + \frac{\beta}{ \sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{10} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{01} $ $</span><span class="sxs-lookup"><span data-stu-id="3be60-141">$$ \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{00} + \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{11} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{10} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{01} $$</span></span>

<span data-ttu-id="3be60-142">Observe que cada termo tem $2 \frac{1}{\sqrt{2}} $ fatores.</span><span class="sxs-lookup"><span data-stu-id="3be60-142">Note that each term has two $\frac{1}{\sqrt{2}}$ factors.</span></span> <span data-ttu-id="3be60-143">Podemos multiplicar esses resultados dando o seguinte resultado:</span><span class="sxs-lookup"><span data-stu-id="3be60-143">We can multiply these out giving the following result:</span></span>

<span data-ttu-id="3be60-144">$ $ \frac{\alpha}{2}(\ket{0} + \ket{1}) \ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1}) \ket{11} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{10} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{01} $ $</span><span class="sxs-lookup"><span data-stu-id="3be60-144">$$ \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{11} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{10} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{01} $$</span></span>

<span data-ttu-id="3be60-145">A{1}$ \frac {2}$ factor é comum a cada termo, portanto, agora podemos levá-lo para fora dos colchetes:</span><span class="sxs-lookup"><span data-stu-id="3be60-145">The  $\frac{1}{2}$ factor is common to each term so we can now take it outside the brackets:</span></span>

<span data-ttu-id="3be60-146">$ $ \frac{1}{2}\big [\alpha (\ket{0} + \ket{1}) \ket{00} + \alpha (\ket{0} + \ket{1}) \ket{11} + \beta (\ket{0}-\ket{1}) \ket{10} + \beta (\ket{0}-\ket{1}) \ket{01}\big] $ $</span><span class="sxs-lookup"><span data-stu-id="3be60-146">$$ \frac{1}{2}\big[\alpha(\ket{0} + \ket{1})\ket{00} + \alpha(\ket{0} + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket{01}\big] $$</span></span>

<span data-ttu-id="3be60-147">Em seguida, podemos multiplicar os colchetes para cada termo, fornecendo:</span><span class="sxs-lookup"><span data-stu-id="3be60-147">We can then multiply out the brackets for each term giving:</span></span>

<span data-ttu-id="3be60-148">$ $ \frac{1}{2}\big [\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010}-\beta\ket{110} + \beta\ket{001}-\beta\ket{101}\big] $ $</span><span class="sxs-lookup"><span data-stu-id="3be60-148">$$ \frac{1}{2}\big[\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} - \beta\ket{110} + \beta\ket{001} - \beta\ket{101}\big] $$</span></span>

### <a name="step-3-measure-the-result"></a><span data-ttu-id="3be60-149">Etapa 3: medir o resultado</span><span class="sxs-lookup"><span data-stu-id="3be60-149">Step 3: Measure the result</span></span>

<span data-ttu-id="3be60-150">Devido a __aqui__ e __confusas__ , qualquer medida __aqui__ afetará o estado de __lá__.</span><span class="sxs-lookup"><span data-stu-id="3be60-150">Due to __here__ and __there__ being entangled, any measurement on __here__ will affect the state of __there__.</span></span> <span data-ttu-id="3be60-151">Se medirmos a primeira e a segunda qubit (__mensagem__ e __aqui__), podemos saber em que estado __há__ , devido a essa propriedade de Entanglement.</span><span class="sxs-lookup"><span data-stu-id="3be60-151">If we measure the first and second qubit (__message__ and __here__) we can learn what state __there__ is in, due to this property of entanglement.</span></span> 

* <span data-ttu-id="3be60-152">Se medirmos e obtivermos um resultado 00, a superposição recolherá, deixando apenas os termos consistentes com esse resultado.</span><span class="sxs-lookup"><span data-stu-id="3be60-152">If we measure and get a result 00, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="3be60-153">Isso é $ \alpha\ket{000} + \beta\ket{001}$.</span><span class="sxs-lookup"><span data-stu-id="3be60-153">That's $\alpha\ket{000} +\beta\ket{001}$.</span></span> <span data-ttu-id="3be60-154">Isso pode ser refatorado para $ \ket{00}(\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="3be60-154">This can be refactored to $\ket{00}(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="3be60-155">Portanto, se medirmos o primeiro e o segundo qubit como 00, sabemos que o terceiro qubit, __lá__, está no estado $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="3be60-155">Therefore if we measure the first and second qubit to be 00, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="3be60-156">Se medirmos e obtivermos um resultado 01, a superposição recolherá, deixando apenas os termos consistentes com esse resultado.</span><span class="sxs-lookup"><span data-stu-id="3be60-156">If we measure and get a result 01, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="3be60-157">Isso é $ \alpha\ket{011} + \beta\ket{010}$.</span><span class="sxs-lookup"><span data-stu-id="3be60-157">That's $\alpha\ket{011} +\beta\ket{010}$.</span></span> <span data-ttu-id="3be60-158">Isso pode ser refatorado para $ \ket{01}(\alpha\ket{1} + \beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="3be60-158">This can be refactored to $\ket{01}(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="3be60-159">Portanto, se medirmos o primeiro e o segundo qubit como 01, sabemos que o terceiro qubit, __lá__, está no estado $ (\alpha\ket{1} + \beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="3be60-159">Therefore if we measure the first and second qubit to be 01, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span>
* <span data-ttu-id="3be60-160">Se medirmos e obtivermos um resultado 10, a superposição recolherá, deixando apenas os termos consistentes com esse resultado.</span><span class="sxs-lookup"><span data-stu-id="3be60-160">If we measure and get a result 10, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="3be60-161">Isso é $ \alpha\ket{100}-\beta\ket{101}$.</span><span class="sxs-lookup"><span data-stu-id="3be60-161">That's $\alpha\ket{100} -\beta\ket{101}$.</span></span> <span data-ttu-id="3be60-162">Isso pode ser refatorado para $ \ket{10}(\alpha\ket{0}-\beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="3be60-162">This can be refactored to $\ket{10}(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="3be60-163">Portanto, se medirmos o primeiro e o segundo qubit como 10, sabemos que o terceiro qubit, __lá__, está no estado $ (\alpha\ket{0}-\beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="3be60-163">Therefore if we measure the first and second qubit to be 10, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span>
* <span data-ttu-id="3be60-164">Se medirmos e obtivermos um resultado 11, a superposição recolherá, deixando apenas os termos consistentes com esse resultado.</span><span class="sxs-lookup"><span data-stu-id="3be60-164">If we measure and get a result 11, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="3be60-165">Isso é $ \alpha\ket{111}-\beta\ket{110}$.</span><span class="sxs-lookup"><span data-stu-id="3be60-165">That's $\alpha\ket{111} -\beta\ket{110}$.</span></span> <span data-ttu-id="3be60-166">Isso pode ser refatorado para $ \ket{11}(\alpha\ket{1}-\beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="3be60-166">This can be refactored to $\ket{11}(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="3be60-167">Portanto, se medirmos o primeiro e o segundo qubit como 11, sabemos que o terceiro qubit, __lá__, está no estado $ (\alpha\ket{1}-\beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="3be60-167">Therefore if we measure the first and second qubit to be 11, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span>

### <a name="step-4-interpret-the-result"></a><span data-ttu-id="3be60-168">Etapa 4: interpretar o resultado</span><span class="sxs-lookup"><span data-stu-id="3be60-168">Step 4: Interpret the result</span></span>

<span data-ttu-id="3be60-169">Como lembrete, a __mensagem__ original que queríamos enviar foi:</span><span class="sxs-lookup"><span data-stu-id="3be60-169">As a reminder, the original __message__ we wished to send was:</span></span>

<span data-ttu-id="3be60-170">$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $</span><span class="sxs-lookup"><span data-stu-id="3be60-170">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="3be60-171">Precisamos colocar o qubit nesse estado para __que o estado__ recebido seja aquele que foi pretendido.</span><span class="sxs-lookup"><span data-stu-id="3be60-171">We need to get the __there__ qubit into this state, so that the received state is the one that was intended.</span></span> 

* <span data-ttu-id="3be60-172">Se medimos e obtivemos um resultado de 00, o terceiro qubit, __lá__, está no estado $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="3be60-172">If we measured and got a result of 00, then the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="3be60-173">Como essa é a __mensagem__pretendida, nenhuma alteração é necessária.</span><span class="sxs-lookup"><span data-stu-id="3be60-173">As this is the intended __message__, no alteration is required.</span></span>
* <span data-ttu-id="3be60-174">Se medimos e obtivemos um resultado de 01, o terceiro qubit, __lá__, está no estado $ (\alpha\ket{1} + \beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="3be60-174">If we measured and got a result of 01, then the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="3be60-175">Isso difere da __mensagem__pretendida. no entanto, aplicar uma porta not nos oferece o estado desejado $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="3be60-175">This differs from the intended __message__, however applying a NOT gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="3be60-176">Se medimos e obtivemos um resultado de 10, o terceiro qubit, __lá__, está no estado $ (\alpha\ket{0}-\beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="3be60-176">If we measured and got a result of 10, then the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="3be60-177">Isso difere da __mensagem__pretendida. no entanto, aplicar uma porta Z nos dá o estado desejado $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="3be60-177">This differs from the intended __message__, however applying a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="3be60-178">Se medimos e obtivemos um resultado de 11, o terceiro qubit, __lá__, está no estado $ (\alpha\ket{1}-\beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="3be60-178">If we measured and got a result of 11, then the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="3be60-179">Isso difere da __mensagem__pretendida, no entanto, aplicar uma porta not seguida por um portão Z nos dá o estado desejado $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="3be60-179">This differs from the intended __message__, however applying a NOT gate followed by a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>

<span data-ttu-id="3be60-180">Para resumir, se medirmos e o primeiro qubit for 1, um portão Z será aplicado.</span><span class="sxs-lookup"><span data-stu-id="3be60-180">To summarize, if we measure and the first qubit is 1, a Z gate is applied.</span></span> <span data-ttu-id="3be60-181">Se medirmos e o segundo qubit for 1, uma porta NOT será aplicada.</span><span class="sxs-lookup"><span data-stu-id="3be60-181">If we measure and the second qubit is 1, a NOT gate is applied.</span></span>

### <a name="summary"></a><span data-ttu-id="3be60-182">Resumo</span><span class="sxs-lookup"><span data-stu-id="3be60-182">Summary</span></span>
<span data-ttu-id="3be60-183">Mostrado abaixo está um circuito do quantum de livro de texto que implementa a teleportação.</span><span class="sxs-lookup"><span data-stu-id="3be60-183">Shown below is a text-book quantum circuit that implements the teleportation.</span></span> <span data-ttu-id="3be60-184">Mudando da esquerda para a direita você pode ver:</span><span class="sxs-lookup"><span data-stu-id="3be60-184">Moving from left to right you can see:</span></span>
- <span data-ttu-id="3be60-185">Etapa 1: Entangling __aqui__ e __lá__ aplicando um portão Hadamard e CNOT Gate.</span><span class="sxs-lookup"><span data-stu-id="3be60-185">Step 1: Entangling __here__ and __there__ by applying a Hadamard gate and CNOT gate.</span></span>
- <span data-ttu-id="3be60-186">Etapa 2: enviando a __mensagem__ usando um portão CNOT e um portão Hadamard.</span><span class="sxs-lookup"><span data-stu-id="3be60-186">Step 2: Sending the __message__ using a CNOT gate and a Hadamard gate.</span></span>
- <span data-ttu-id="3be60-187">Etapa 3: fazendo uma medida do primeiro e segundo qubits, __mensagem__ e __aqui__.</span><span class="sxs-lookup"><span data-stu-id="3be60-187">Step 3: Taking a measurement of the first and second qubits, __message__ and __here__.</span></span>
- <span data-ttu-id="3be60-188">Etapa 4: aplicando uma portão NOT ou Z, dependendo do resultado da medida na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="3be60-188">Step 4: Applying a NOT gate or a Z gate, depending on the result of the measurement in step 3.</span></span>

![' Teleport (msg: qubit, ali: qubit): Unit '](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a><span data-ttu-id="3be60-190">Portabilidade Quantum: código</span><span class="sxs-lookup"><span data-stu-id="3be60-190">Quantum Teleportation: Code</span></span>

<span data-ttu-id="3be60-191">Temos nosso circuito para a portadora Quantum:</span><span class="sxs-lookup"><span data-stu-id="3be60-191">We have our circuit for quantum teleportation:</span></span>

![' Teleport (msg: qubit, ali: qubit): Unit '](~/media/teleportation.svg)

<span data-ttu-id="3be60-193">Agora podemos converter cada uma das etapas neste circuito Quantum em Q #.</span><span class="sxs-lookup"><span data-stu-id="3be60-193">We can now translate each of the steps in this quantum circuit into Q#.</span></span>

### <a name="step-0-definition"></a><span data-ttu-id="3be60-194">Etapa 0: definição</span><span class="sxs-lookup"><span data-stu-id="3be60-194">Step 0: Definition</span></span>
<span data-ttu-id="3be60-195">Quando executamos a teleportação, devemos saber a __mensagem__ que desejamos enviar e onde desejamos enviá-la (__lá__).</span><span class="sxs-lookup"><span data-stu-id="3be60-195">When we perform teleportation, we must know the __message__ we wish to send, and where we wish to send it (__there__).</span></span> <span data-ttu-id="3be60-196">Por esse motivo, começamos definindo uma nova operação teleport que recebe dois qubits como argumentos, `msg` e `there`:</span><span class="sxs-lookup"><span data-stu-id="3be60-196">For this reason, we begin by defining a new Teleport operation that is given two qubits as arguments, `msg` and `there`:</span></span>

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

<span data-ttu-id="3be60-197">Também precisamos alocar um `here` qubit que realizamos com um bloco de `using`:</span><span class="sxs-lookup"><span data-stu-id="3be60-197">We also need to allocate a qubit `here` which we achieve with a `using` block:</span></span>

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="3be60-198">Etapa 1: criar um estado de confusas</span><span class="sxs-lookup"><span data-stu-id="3be60-198">Step 1: Create an entangled state</span></span>
<span data-ttu-id="3be60-199">Em seguida, podemos criar o par confusas entre `here` e `there` usando as operações @"microsoft.quantum.primitive.h" e @"microsoft.quantum.primitive.cnot":</span><span class="sxs-lookup"><span data-stu-id="3be60-199">We can then create the entangled pair between `here` and `there` by using the @"microsoft.quantum.primitive.h" and @"microsoft.quantum.primitive.cnot" operations:</span></span>

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a><span data-ttu-id="3be60-200">Etapa 2: enviar a mensagem</span><span class="sxs-lookup"><span data-stu-id="3be60-200">Step 2: Send the message</span></span>
<span data-ttu-id="3be60-201">Em seguida, usamos as próximas $ \operatorname{CNOT} $ e $H $ Gates para mover nossa qubit de mensagem:</span><span class="sxs-lookup"><span data-stu-id="3be60-201">We then use the next $\operatorname{CNOT}$ and $H$ gates to move our message qubit:</span></span>

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a><span data-ttu-id="3be60-202">Etapa 3 & 4: medindo e interpretando o resultado</span><span class="sxs-lookup"><span data-stu-id="3be60-202">Step 3 & 4: Measuring and interpreting the result</span></span>
<span data-ttu-id="3be60-203">Por fim, usamos @"microsoft.quantum.primitive.m" para executar as medidas e executar as operações de portão necessárias para obter o estado desejado, conforme indicado pelas instruções `if`:</span><span class="sxs-lookup"><span data-stu-id="3be60-203">Finally, we use @"microsoft.quantum.primitive.m" to perform the measurements and perform the necessary gate operations to get the desired state, as denoted by `if` statements:</span></span>

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

<span data-ttu-id="3be60-204">Isso conclui a definição do nosso operador de Teleportation, para que possamos desalocar `here`, terminar o corpo e terminar a operação.</span><span class="sxs-lookup"><span data-stu-id="3be60-204">This finishes the definition of our teleportation operator, so we can deallocate `here`, end the body, and end the operation.</span></span>

```qsharp
    }
}
```
