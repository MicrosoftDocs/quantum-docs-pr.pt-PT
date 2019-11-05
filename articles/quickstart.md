---
title: Noções básicas dos programas quânticos com Q#
description: Saiba como escrever um programa quântico em Q#. Desenvolver uma aplicação de Estado de Bell com o Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 10/07/2019
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 30135fa8a123e52a92b7187218f9980ba3cdbd2d
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442212"
---
# <a name="quantum-basics-with-q"></a><span data-ttu-id="cc051-104">Noções básicas dos programas quânticos com Q#</span><span class="sxs-lookup"><span data-stu-id="cc051-104">Quantum basics with Q#</span></span>

<span data-ttu-id="cc051-105">Neste Início Rápido, mostramos como escrever um programa em Q# que manipula e mede qubits, além de demonstrar os efeitos da sobreposição e do entrelaçamento.</span><span class="sxs-lookup"><span data-stu-id="cc051-105">In this Quickstart, we show you how to write a Q# program that manipulates and measures qubits and demonstrates the effects of superposition and entanglement.</span></span>  <span data-ttu-id="cc051-106">Este guia vai orientá-lo na instalação do QDK, na compilação do programa e na execução desse programa num simulador quântico.</span><span class="sxs-lookup"><span data-stu-id="cc051-106">This guides you on installing the QDK, building the program and executing that program on a quantum simulator.</span></span>  

<span data-ttu-id="cc051-107">Vai escrever uma aplicação denominada Bell para demonstrar o entrelaçamento quântico.</span><span class="sxs-lookup"><span data-stu-id="cc051-107">You will write an application called Bell to demonstrate quantum entanglement.</span></span>  <span data-ttu-id="cc051-108">O nome Bell refere-se aos estados de Bell, que são estados quânticos específicos de dois qubits, utilizados para representar os exemplos mais simples de sobreposição e de entrelaçamento quântico.</span><span class="sxs-lookup"><span data-stu-id="cc051-108">The name Bell is in reference to Bell states, which are specific quantum states of two qubits that are used to represent the simplest examples of superposition and quantum entanglement.</span></span> 

## <a name="pre-requisites"></a><span data-ttu-id="cc051-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="cc051-109">Pre-requisites</span></span>

<span data-ttu-id="cc051-110">Se estiver preparado para começar a programar, siga estes passos antes de continuar:</span><span class="sxs-lookup"><span data-stu-id="cc051-110">If you are ready to start coding, follow these steps before proceeding:</span></span> 

* <span data-ttu-id="cc051-111">[Instalar](xref:microsoft.quantum.install) o Quantum Development Kit com o ambiente de desenvolvimento e a linguagem da sua preferência</span><span class="sxs-lookup"><span data-stu-id="cc051-111">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your preferred language and development environment</span></span>
* <span data-ttu-id="cc051-112">Se já tiver o QDK instalado, confirme que o [atualizou](xref:microsoft.quantum.update) para a versão mais recente</span><span class="sxs-lookup"><span data-stu-id="cc051-112">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>

<span data-ttu-id="cc051-113">Também pode acompanhar a narrativa sem instalar o QDK e rever as descrições gerais da linguagem de programação Q# e os conceitos iniciais da computação quântica.</span><span class="sxs-lookup"><span data-stu-id="cc051-113">You can also follow along with the narrative without installing the QDK, reviewing the overviews of the Q# programming language and the first concepts of quantum computing.</span></span>

## <a name="demonstrating-qubit-behavior-with-q"></a><span data-ttu-id="cc051-114">Demonstrar o comportamento dos qubits com Q#</span><span class="sxs-lookup"><span data-stu-id="cc051-114">Demonstrating qubit behavior with Q#</span></span>

<span data-ttu-id="cc051-115">Lembre-se da nossa [definição de qubit](xref:microsoft.quantum.overview.what#the-qubit) simples.</span><span class="sxs-lookup"><span data-stu-id="cc051-115">Recall our simple [definition of a qubit](xref:microsoft.quantum.overview.what#the-qubit).</span></span>  <span data-ttu-id="cc051-116">Enquanto os bits clássicos contêm um único valor binário como 0 ou 1, o estado de um qubit pode estar numa **sobreposição** de 0 e 1 simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="cc051-116">Where classical bits hold a single binary value such as a 0 or 1, the state of a qubit can be in a **superposition** of 0 and 1 simultaneously.</span></span>  <span data-ttu-id="cc051-117">Conceitualmente, um qubit pode ser pensado como uma direção no espaço (também conhecido como um vetor).</span><span class="sxs-lookup"><span data-stu-id="cc051-117">Conceptually, a qubit can be thought of as a direction in space (also known as a vector).</span></span>  <span data-ttu-id="cc051-118">Um qubit pode estar em qualquer uma das possíveis direções.</span><span class="sxs-lookup"><span data-stu-id="cc051-118">A qubit can be in any of the possible directions.</span></span> <span data-ttu-id="cc051-119">Os dois **estados clássicos** são as duas direções, que representam 100% de probabilidade de medir 0 e 100% de probabilidade de medir 1.</span><span class="sxs-lookup"><span data-stu-id="cc051-119">The two **classical states** are the two directions; representing 100% chance of measuring 0 and 100% chance of measuring 1.</span></span>  <span data-ttu-id="cc051-120">Esta representação também é visualizada mais formalmente pela [Esfera de Bloch](/quantum/concepts/the-qubit?view=qsharp-preview#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span><span class="sxs-lookup"><span data-stu-id="cc051-120">This representation is also more formally visualized by the [bloch sphere](/quantum/concepts/the-qubit?view=qsharp-preview#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span></span>


<span data-ttu-id="cc051-121">O ato de medição produz um resultado binário e altera o estado de um qubit.</span><span class="sxs-lookup"><span data-stu-id="cc051-121">The act of measurement produces a binary result and changes a qubit state.</span></span> <span data-ttu-id="cc051-122">A medição produz um valor binário de 0 ou 1.</span><span class="sxs-lookup"><span data-stu-id="cc051-122">Measurement produces a binary value, either 0 or 1.</span></span>  <span data-ttu-id="cc051-123">O qubit vai do estado de sobreposição (qualquer direção) até um dos estados clássicos.</span><span class="sxs-lookup"><span data-stu-id="cc051-123">The qubit goes from being in superposition (any direction) to one of the classical states.</span></span>  <span data-ttu-id="cc051-124">Depois disso, repetir a mesma medição sem nenhuma operação intermediária produz o mesmo resultado binário.</span><span class="sxs-lookup"><span data-stu-id="cc051-124">Thereafter, repeating the same measurement without any intervening operations produces the same binary result.</span></span>  

<span data-ttu-id="cc051-125">É possível **entrelaçar** vários qubits.</span><span class="sxs-lookup"><span data-stu-id="cc051-125">Multiple qubits can be **entangled**.</span></span> <span data-ttu-id="cc051-126">Quando fazemos a medição de um qubit entrelaçado, o nosso conhecimento do estado do(s) outro(s) também é atualizado.</span><span class="sxs-lookup"><span data-stu-id="cc051-126">When we make a measurement of one entangled qubit, our knowledge of the state of the other(s) is updated as well.</span></span>

<span data-ttu-id="cc051-127">Agora, estamos prontos para demonstrar de que forma o Q# expressa este comportamento.</span><span class="sxs-lookup"><span data-stu-id="cc051-127">Now, we're ready to demonstrate how Q# expresses this behavior.</span></span>  <span data-ttu-id="cc051-128">Vai começar com o programa mais simples possível e compilá-lo para demonstrar a sobreposição quântica e o entrelaçamento quântico.</span><span class="sxs-lookup"><span data-stu-id="cc051-128">You start with the simplest program possible and build it up to demonstrate quantum superposition and quantum entanglement.</span></span>

## <a name="setup"></a><span data-ttu-id="cc051-129">Configurar</span><span class="sxs-lookup"><span data-stu-id="cc051-129">Setup</span></span>

<span data-ttu-id="cc051-130">As aplicações desenvolvidas com o Microsoft Quantum Development Kit consiste em duas partes:</span><span class="sxs-lookup"><span data-stu-id="cc051-130">Applications developed with Microsoft's Quantum Development Kit consist of two parts:</span></span>

1. <span data-ttu-id="cc051-131">Um ou mais algoritmos quânticos, implementados com a linguagem de programação quântica Q#.</span><span class="sxs-lookup"><span data-stu-id="cc051-131">One or more quantum algorithms, implemented using the Q# quantum programming language.</span></span>
1. <span data-ttu-id="cc051-132">Um programa anfitrião, implementado numa linguagem de programação como Python ou C# e que serve como ponto de entrada principal e invoca operações Q# para executar um algoritmo quântico.</span><span class="sxs-lookup"><span data-stu-id="cc051-132">A host program, implemented in a programming language like Python or C# that serves as the main entry point and invokes Q# operations to execute a quantum algorithm.</span></span>

#### <a name="pythontabtabid-python"></a>[<span data-ttu-id="cc051-133">Python</span><span class="sxs-lookup"><span data-stu-id="cc051-133">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="cc051-134">Escolha uma localização para a aplicação</span><span class="sxs-lookup"><span data-stu-id="cc051-134">Choose a location for your application</span></span>

1. <span data-ttu-id="cc051-135">Crie um ficheiro denominado `Bell.qs`.</span><span class="sxs-lookup"><span data-stu-id="cc051-135">Create a file called `Bell.qs`.</span></span> <span data-ttu-id="cc051-136">Este ficheiro conterá o código Q#.</span><span class="sxs-lookup"><span data-stu-id="cc051-136">This file will contain your Q# code.</span></span>

1. <span data-ttu-id="cc051-137">Crie um ficheiro denominado `host.py`.</span><span class="sxs-lookup"><span data-stu-id="cc051-137">Create a file called `host.py`.</span></span> <span data-ttu-id="cc051-138">Este ficheiro conterá o código anfitrião Python.</span><span class="sxs-lookup"><span data-stu-id="cc051-138">This file will contain your Python host code.</span></span>

#### <a name="c-command-linetabtabid-csharp"></a>[<span data-ttu-id="cc051-139">Linha de Comandos C#</span><span class="sxs-lookup"><span data-stu-id="cc051-139">C# Command Line</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="cc051-140">Crie um novo projeto Q#:</span><span class="sxs-lookup"><span data-stu-id="cc051-140">Create a new Q# project:</span></span>

    ```bash
    dotnet new console -lang Q# --output Bell
    cd Bell
    ```

    <span data-ttu-id="cc051-141">Deve ver um ficheiro `.csproj`, um ficheiro Q# denominado `Operations.qs` e um ficheiro de programa anfitrião denominado `Driver.cs`</span><span class="sxs-lookup"><span data-stu-id="cc051-141">You should see a `.csproj` file, a Q# file called `Operations.qs`, and a host program file called `Driver.cs`</span></span>

1. <span data-ttu-id="cc051-142">Mude o nome do ficheiro Q#</span><span class="sxs-lookup"><span data-stu-id="cc051-142">Rename the Q# file</span></span>

    ```bash
    mv Operation.qs Bell.qs
    ```

#### <a name="visual-studiotabtabid-vs2019"></a>[<span data-ttu-id="cc051-143">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cc051-143">Visual Studio</span></span>](#tab/tabid-vs2019)

1. <span data-ttu-id="cc051-144">Criar um novo projeto</span><span class="sxs-lookup"><span data-stu-id="cc051-144">Create a new project</span></span>

   * <span data-ttu-id="cc051-145">Abrir o Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cc051-145">Open Visual Studio</span></span>
   * <span data-ttu-id="cc051-146">Aceda ao menu **Ficheiro** e selecione **Novo** -> **Projeto...**</span><span class="sxs-lookup"><span data-stu-id="cc051-146">Go to the **File** menu and select **New** -> **Project...**</span></span>
   * <span data-ttu-id="cc051-147">No explorador de modelos do projeto, escreva `Q#` no campo de pesquisa e selecione o modelo `Q# Application`</span><span class="sxs-lookup"><span data-stu-id="cc051-147">In the project template explorer, type `Q#` into the search field and select the `Q# Application` template</span></span>
   * <span data-ttu-id="cc051-148">Atribua o nome `Bell` ao projeto</span><span class="sxs-lookup"><span data-stu-id="cc051-148">Give your project the name `Bell`</span></span>

1. <span data-ttu-id="cc051-149">Mude o nome do ficheiro Q#</span><span class="sxs-lookup"><span data-stu-id="cc051-149">Rename the Q# file</span></span>

   * <span data-ttu-id="cc051-150">Navegue até ao **Explorador de Soluções**</span><span class="sxs-lookup"><span data-stu-id="cc051-150">Navigate to the **Solution Explorer**</span></span>
   * <span data-ttu-id="cc051-151">Clique com o botão direito do rato no ficheiro `Operations.qs`</span><span class="sxs-lookup"><span data-stu-id="cc051-151">Right click on the `Operations.qs` file</span></span>
   * <span data-ttu-id="cc051-152">Mude o nome para `Bell.qs`</span><span class="sxs-lookup"><span data-stu-id="cc051-152">Rename it to `Bell.qs`</span></span>

* * *

## <a name="write-a-q-operation"></a><span data-ttu-id="cc051-153">Escrever uma operação Q#</span><span class="sxs-lookup"><span data-stu-id="cc051-153">Write a Q# operation</span></span>

<span data-ttu-id="cc051-154">O nosso objetivo é preparar dois qubits num estado quântico específico, ao demonstrar como trabalhar nos qubits com Q# para alterar o estado deles e demonstrar os efeitos da sobreposição e do entrelaçamento.</span><span class="sxs-lookup"><span data-stu-id="cc051-154">Our goal is to prepare two qubits in a specific quantum state, demonstrating how to operate on qubits with Q# to change their state and demonstrate the effects of superposition and entanglement.</span></span> <span data-ttu-id="cc051-155">Vamos criar isto peça a peça para demonstrar as medições, as operações e os estados dos qubits.</span><span class="sxs-lookup"><span data-stu-id="cc051-155">We will build this up piece by piece to demonstrate qubit states, operations, and measurement.</span></span>

<span data-ttu-id="cc051-156">**Descrição geral:**  no primeiro código abaixo, mostramos como utilizar os qubits em Q#.</span><span class="sxs-lookup"><span data-stu-id="cc051-156">**Overview:**  In the first code below, we show you how to work with qubits in Q#.</span></span>  <span data-ttu-id="cc051-157">Vamos apresentar duas operações, `M` e `X`, as quais transformam o estado de um qubit.</span><span class="sxs-lookup"><span data-stu-id="cc051-157">We’ll introduce two operations, `M` and `X` that transform the state of a qubit.</span></span> 

<span data-ttu-id="cc051-158">Neste fragmento de código, é definida uma operação `Set`, que utiliza um qubit como parâmetro e outro parâmetro, `desired`, que representa o estado em que queremos que o qubit esteja.</span><span class="sxs-lookup"><span data-stu-id="cc051-158">In this code snippet, an operation `Set` is defined that takes as a parameter a qubit and another parameter, `desired`, representing the state that we would like the qubit to be in.</span></span>  <span data-ttu-id="cc051-159">A operação `Set` executa uma medição no qubit através da operação `M`.</span><span class="sxs-lookup"><span data-stu-id="cc051-159">The operation `Set` performs a measurement on the qubit using the operation `M`.</span></span>  <span data-ttu-id="cc051-160">Em Q#, a medição de um qubit devolve sempre `Zero` ou `One`.</span><span class="sxs-lookup"><span data-stu-id="cc051-160">In Q#, a qubit measurement always returns either  `Zero` or `One`.</span></span>  <span data-ttu-id="cc051-161">Se a medição devolver um valor diferente do valor pretendido, a operação Set “inverte” o qubit, ou seja, executa uma operação `X` que altera o estado do qubit para um novo estado no qual as probabilidades de uma medição devolver `Zero` e `One` são invertidas.</span><span class="sxs-lookup"><span data-stu-id="cc051-161">If the measurement returns a value not equal to a desired value, Set “flips” the qubit; that is, it executes an `X` operation, which changes the qubit state to a new state in which the probabilities of a measurement returning `Zero` and `One` are reversed.</span></span>  <span data-ttu-id="cc051-162">Para demonstrar o efeito da operação `Set`, é adicionada uma operação `TestBellState`.</span><span class="sxs-lookup"><span data-stu-id="cc051-162">To demonstrate the effect of the `Set` operation, a `TestBellState` operation is then added.</span></span>  <span data-ttu-id="cc051-163">Esta operação utiliza como entrada `Zero` ou `One`, chama a operação `Set` várias vezes com essa entrada e contabiliza o número de vezes que `Zero` foi devolvido pela medição do qubit e o número de vezes que `One` foi devolvido.</span><span class="sxs-lookup"><span data-stu-id="cc051-163">This operation takes as input a `Zero` or `One`, and calls the `Set` operation some number of times with that input, and counts the number of times that `Zero` was returned from the measurement of the qubit and the number of times that `One` was returned.</span></span> <span data-ttu-id="cc051-164">Como é óbvio, nesta primeira simulação da operação `TestBellState`, esperamos que o resultado mostre que todas as medições do conjunto de qubits com `Zero` como entrada de parâmetro devolva `Zero` e todas as medições de um conjunto de qubits com `One` como entrada de parâmetro devolva `One`.</span><span class="sxs-lookup"><span data-stu-id="cc051-164">Of course, in this first simulation of the `TestBellState` operation, we expect that the output will show that all measurements of the qubit set with `Zero` as the parameter input will return `Zero`, and all measurements of a qubit set with `One` as the parameter input will return `One`.</span></span>  <span data-ttu-id="cc051-165">Além disso, vamos adicionar código a `TestBellState` para demonstrar a sobreposição e o entrelaçamento.</span><span class="sxs-lookup"><span data-stu-id="cc051-165">Further on, we’ll add code to `TestBellState` to demonstrating superposition and entanglement.</span></span>


### <a name="q-operation-code"></a><span data-ttu-id="cc051-166">Código de operação Q#</span><span class="sxs-lookup"><span data-stu-id="cc051-166">Q# operation code</span></span>

1. <span data-ttu-id="cc051-167">Substitua o conteúdo do ficheiro Bell.qs pelo seguinte código:</span><span class="sxs-lookup"><span data-stu-id="cc051-167">Replace the contents of the Bell.qs file with the following code:</span></span>

    ```qsharp
    namespace Quantum.Bell {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation Set(desired : Result, q1 : Qubit) : Unit {
            if (desired != M(q1)) {
                X(q1);
            }
        }
    }
    ```

    <span data-ttu-id="cc051-168">Esta operação agora pode ser chamada para definir um qubit para um estado clássico, ao devolver `Zero` ou `One` 100% do tempo.</span><span class="sxs-lookup"><span data-stu-id="cc051-168">This operation may now be called to set a qubit to a classical state, either returning `Zero` 100% of the time or returning `One` 100% of the time.</span></span>  <span data-ttu-id="cc051-169">`Zero` e `One` são constantes que representam os dois únicos resultados possíveis da medição de um qubit.</span><span class="sxs-lookup"><span data-stu-id="cc051-169">`Zero` and `One` are constants that represent the only two possible results of a measurement of a qubit.</span></span>

    <span data-ttu-id="cc051-170">A operação `Set` mede o qubit.</span><span class="sxs-lookup"><span data-stu-id="cc051-170">The operation `Set` measures the qubit.</span></span>
    <span data-ttu-id="cc051-171">Se o qubit estiver no estado pretendido, `Set` não fará nada. Caso contrário, ao executar a operação `X`, alteramos o estado do qubit para o estado pretendido.</span><span class="sxs-lookup"><span data-stu-id="cc051-171">If the qubit is in the state we want, `Set` leaves it alone; otherwise, by executing the `X` operation, we change the qubit state to the desired state.</span></span>

### <a name="about-q-operations"></a><span data-ttu-id="cc051-172">Acerca das operações Q#</span><span class="sxs-lookup"><span data-stu-id="cc051-172">About Q# operations</span></span>

<span data-ttu-id="cc051-173">Uma operação Q# é uma sub-rotina quântica.</span><span class="sxs-lookup"><span data-stu-id="cc051-173">A Q# operation is a quantum subroutine.</span></span> <span data-ttu-id="cc051-174">Ou seja, é uma rotina que pode ser chamada que contém operações quânticas.</span><span class="sxs-lookup"><span data-stu-id="cc051-174">That is, it is a callable routine that contains quantum operations.</span></span>

<span data-ttu-id="cc051-175">Os argumentos para uma operação são especificados como uma cadeia de identificação, entre parênteses.</span><span class="sxs-lookup"><span data-stu-id="cc051-175">The arguments to an operation are specified as a tuple, within parentheses.</span></span>

<span data-ttu-id="cc051-176">O tipo de retorno da operação é especificado após os dois pontos.</span><span class="sxs-lookup"><span data-stu-id="cc051-176">The return type of the operation is specified after a colon.</span></span> <span data-ttu-id="cc051-177">Neste caso, a operação `Set` não tem retorno, pelo qual é marcada como `Unit` de retorno.</span><span class="sxs-lookup"><span data-stu-id="cc051-177">In this case, the `Set` operation has no return, so it is marked as returning `Unit`.</span></span> <span data-ttu-id="cc051-178">É o equivalente Q# de `unit` em F#, o que é aproximadamente análogo a `void` em C# e uma cadeia de identificação vazia (`Tuple[()]`) em Python.</span><span class="sxs-lookup"><span data-stu-id="cc051-178">This is the Q# equivalent of `unit` in F#, which is roughly analogous to `void` in C#, and an empty tuple (`Tuple[()]`) in Python.</span></span>

<span data-ttu-id="cc051-179">Utilizou duas operações quânticas na primeira operação Q#:</span><span class="sxs-lookup"><span data-stu-id="cc051-179">You have used two quantum operations in your first Q# operation:</span></span>

* <span data-ttu-id="cc051-180">A operação [M](xref:microsoft.quantum.intrinsic.m), que mede o estado do qubit</span><span class="sxs-lookup"><span data-stu-id="cc051-180">The [M](xref:microsoft.quantum.intrinsic.m) operation, which measures the state of the qubit</span></span>
* <span data-ttu-id="cc051-181">A operação [X](xref:microsoft.quantum.intrinsic.x), que inverte o estado do qubit</span><span class="sxs-lookup"><span data-stu-id="cc051-181">The [X](xref:microsoft.quantum.intrinsic.x) operation, which flips the state of a qubit</span></span>

<span data-ttu-id="cc051-182">Uma operação quântica transforma o estado de um qubit.</span><span class="sxs-lookup"><span data-stu-id="cc051-182">A quantum operation transforms the state of a qubit.</span></span> <span data-ttu-id="cc051-183">Por vezes, as pessoas falam sobre portas quânticas em vez de operações, em analogia às portas de lógica clássicas e</span><span class="sxs-lookup"><span data-stu-id="cc051-183">Sometime people talk about quantum gates instead of operations, in analogy to classical logic gates.</span></span> <span data-ttu-id="cc051-184">que tem origem nos primórdios da computação quântica quando os algoritmos eram meramente uma construção teórica e visualizados como diagramas da mesma forma que os diagramas de circuito na computação clássica.</span><span class="sxs-lookup"><span data-stu-id="cc051-184">This is rooted in the early days of quantum computing when algorithms were merely a theoretical construct and visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>

### <a name="add-q-test-code"></a><span data-ttu-id="cc051-185">Adicionar o código de teste de Q#</span><span class="sxs-lookup"><span data-stu-id="cc051-185">Add Q# test code</span></span>

1. <span data-ttu-id="cc051-186">Adicione a seguinte operação ao ficheiro `Bell.qs`, dentro do espaço de nomes, após o fim da operação `Set`:</span><span class="sxs-lookup"><span data-stu-id="cc051-186">Add the following operation to the `Bell.qs` file, inside the namespace, after the end of the `Set` operation:</span></span>

    ```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                Set(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            Set(Zero, qubit);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
    ```

    <span data-ttu-id="cc051-187">Esta operação (`TestBellState`) vai gerar um ciclo de `count` iterações, definir um valor `initial` especificado num qubit e, em seguida, medir (`M`) o resultado.</span><span class="sxs-lookup"><span data-stu-id="cc051-187">This operation (`TestBellState`) will loop for `count` iterations, set a specified `initial` value on a qubit and then measure (`M`) the result.</span></span> <span data-ttu-id="cc051-188">Vai recolher estatísticas sobre quantos zeros e uns foram medidos e devolvê-los ao autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="cc051-188">It will gather statistics on how many zeros and ones we've measured and return them to the caller.</span></span> <span data-ttu-id="cc051-189">E, executa ainda outra operação necessária.</span><span class="sxs-lookup"><span data-stu-id="cc051-189">It performs one other necessary operation.</span></span> <span data-ttu-id="cc051-190">Redefine o qubit para um estado conhecido (`Zero`) antes de o devolver, o que permitirá que outros aloquem este qubit num estado conhecido.</span><span class="sxs-lookup"><span data-stu-id="cc051-190">It resets the qubit to a known state (`Zero`) before returning it allowing others to allocate this qubit in a known state.</span></span> <span data-ttu-id="cc051-191">Esta operação é exigida pela instrução `using`.</span><span class="sxs-lookup"><span data-stu-id="cc051-191">This is required by the `using` statement.</span></span>

### <a name="about-variables-in-q"></a><span data-ttu-id="cc051-192">Acerca das variáveis em Q#</span><span class="sxs-lookup"><span data-stu-id="cc051-192">About variables in Q#</span></span>

<span data-ttu-id="cc051-193">Por predefinição, as variáveis Q# são imutáveis; o valor dessas variáveis não pode ser alterado após serem vinculadas.</span><span class="sxs-lookup"><span data-stu-id="cc051-193">By default, variables in Q# are immutable; their value may not be changed after they are bound.</span></span> <span data-ttu-id="cc051-194">A palavra-chave `let` é utilizada para indicar a vinculação de uma variável imutável.</span><span class="sxs-lookup"><span data-stu-id="cc051-194">The `let` keyword is used to indicate the binding of an immutable variable.</span></span> <span data-ttu-id="cc051-195">Os argumentos da operação são sempre imutáveis.</span><span class="sxs-lookup"><span data-stu-id="cc051-195">Operation arguments are always immutable.</span></span>

<span data-ttu-id="cc051-196">Se precisar de uma variável cujo valor pode ser alterado, como `numOnes`, poderá declarar a variável com a palavra-chave `mutable`.</span><span class="sxs-lookup"><span data-stu-id="cc051-196">If you need a variable whose value can change, such as `numOnes` in the example, you can declare the variable with the `mutable` keyword.</span></span> <span data-ttu-id="cc051-197">Um valor de variável mutável pode ser alterado com uma instrução `set`.</span><span class="sxs-lookup"><span data-stu-id="cc051-197">A mutable variable's value may be changed using a `set` statement.</span></span>

<span data-ttu-id="cc051-198">Em ambos os casos, o tipo de variável é inferido pelo compilador.</span><span class="sxs-lookup"><span data-stu-id="cc051-198">In both cases, the type of a variable is inferred by the compiler.</span></span> <span data-ttu-id="cc051-199">A Q# não requer nenhum tipo de anotação para as variáveis.</span><span class="sxs-lookup"><span data-stu-id="cc051-199">Q# doesn't require any type annotations for variables.</span></span>

### <a name="about-using-statements-in-q"></a><span data-ttu-id="cc051-200">Acerca das instruções `using` em Q#</span><span class="sxs-lookup"><span data-stu-id="cc051-200">About `using` statements in Q#</span></span>

<span data-ttu-id="cc051-201">A instrução `using` também é especial para Q#.</span><span class="sxs-lookup"><span data-stu-id="cc051-201">The `using` statement is also special to Q#.</span></span> <span data-ttu-id="cc051-202">É utilizada para alocar qubits para utilização num bloco de código.</span><span class="sxs-lookup"><span data-stu-id="cc051-202">It is used to allocate qubits for use in a block of code.</span></span> <span data-ttu-id="cc051-203">Em Q#, todos os qubits são alocados e libertados dinamicamente, em vez de serem recursos fixos presente durante toda a duração de um algoritmo complexo.</span><span class="sxs-lookup"><span data-stu-id="cc051-203">In Q#, all qubits are dynamically allocated and released, rather than being fixed resources that are there for the entire lifetime of a complex algorithm.</span></span> <span data-ttu-id="cc051-204">Uma instrução `using` aloca um conjunto de qubits no início e liberta esses qubits no final do bloco.</span><span class="sxs-lookup"><span data-stu-id="cc051-204">A `using` statement allocates a set of qubits at the start, and releases those qubits at the end of the block.</span></span>

## <a name="create-the-host-application-code"></a><span data-ttu-id="cc051-205">Criar o código da aplicação anfitriã</span><span class="sxs-lookup"><span data-stu-id="cc051-205">Create the host application code</span></span>

#### <a name="pythontabtabid-python"></a>[<span data-ttu-id="cc051-206">Python</span><span class="sxs-lookup"><span data-stu-id="cc051-206">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="cc051-207">Abra o ficheiro `host.py` e adicione-o ao seguinte código:</span><span class="sxs-lookup"><span data-stu-id="cc051-207">Open the `host.py` file and add the following code:</span></span>

    ```python
    import qsharp

    from qsharp import Result
    from Quantum.Bell import TestBellState

    initials = (Result.Zero, Result.One)

    for i in initials:
      res = TestBellState.simulate(count=1000, initial=i)
      (num_zeros, num_ones) = res
      print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4}')
    ```

#### <a name="ctabtabid-csharp"></a>[<span data-ttu-id="cc051-208">C#</span><span class="sxs-lookup"><span data-stu-id="cc051-208">C#</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="cc051-209">Substitua o conteúdo do ficheiro `Driver.cs` pelo código seguinte:</span><span class="sxs-lookup"><span data-stu-id="cc051-209">Replace the contents of the `Driver.cs` file with the following code:</span></span>

    ```csharp
    using System;

    using Microsoft.Quantum.Simulation.Core;
    using Microsoft.Quantum.Simulation.Simulators;

    namespace Quantum.Bell
    {
        class Driver
        {
            static void Main(string[] args)
            {
                using (var qsim = new QuantumSimulator())
                {
                    // Try initial values
                    Result[] initials = new Result[] { Result.Zero, Result.One };
                    foreach (Result initial in initials)
                    {
                        var res = TestBellState.Run(qsim, 1000, initial).Result;
                        var (numZeros, numOnes) = res;
                        System.Console.WriteLine(
                            $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4}");
                    }
                }

                System.Console.WriteLine("Press any key to continue...");
                Console.ReadKey();
            }
        }
    }
    ```

#### [](#tab/tabid-vs2019)

* * *

### <a name="about-the-host-application-code"></a><span data-ttu-id="cc051-210">Acerca do código da aplicação anfitriã</span><span class="sxs-lookup"><span data-stu-id="cc051-210">About the host application code</span></span>

#### <a name="pythontabtabid-python"></a>[<span data-ttu-id="cc051-211">Python</span><span class="sxs-lookup"><span data-stu-id="cc051-211">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="cc051-212">A aplicação anfitriã do Python possui três partes:</span><span class="sxs-lookup"><span data-stu-id="cc051-212">The Python host application has three parts:</span></span>

* <span data-ttu-id="cc051-213">Calcule todos os argumentos necessários do algoritmo quântico.</span><span class="sxs-lookup"><span data-stu-id="cc051-213">Compute any arguments required for the quantum algorithm.</span></span> <span data-ttu-id="cc051-214">No exemplo, o argumento `count` foi fixado em 1000 e `initial` é o valor inicial do qubit.</span><span class="sxs-lookup"><span data-stu-id="cc051-214">In the example, `count` is fixed at a 1000 and `initial` is the initial value of the qubit.</span></span>
* <span data-ttu-id="cc051-215">Execute o algoritmo quântico ao chamar o método `simulate()` da operação Q# importada.</span><span class="sxs-lookup"><span data-stu-id="cc051-215">Run the quantum algorithm by calling the `simulate()` method of the imported Q# operation.</span></span>
* <span data-ttu-id="cc051-216">Processe o resultado da operação.</span><span class="sxs-lookup"><span data-stu-id="cc051-216">Process the result of the operation.</span></span> <span data-ttu-id="cc051-217">No exemplo, `res` recebe o resultado da operação.</span><span class="sxs-lookup"><span data-stu-id="cc051-217">In the example, `res` receives the result of the operation.</span></span> <span data-ttu-id="cc051-218">Aqui, o resultado é uma cadeia de identificação do número de zeros (`num_zeros`) e do número de uns (`num_ones`) medidos pelo simulador.</span><span class="sxs-lookup"><span data-stu-id="cc051-218">Here the result is a tuple of the number of zeros (`num_zeros`) and number of ones (`num_ones`) measured by the simulator.</span></span> <span data-ttu-id="cc051-219">Vamos desconstruir a cadeia de identificação para obter dois campos e imprimir os resultados.</span><span class="sxs-lookup"><span data-stu-id="cc051-219">We deconstruct the tuple to get the two fields, and print the results.</span></span>

#### <a name="ctabtabid-csharp"></a>[<span data-ttu-id="cc051-220">C#</span><span class="sxs-lookup"><span data-stu-id="cc051-220">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="cc051-221">A aplicação anfitriã C# possui quatro partes:</span><span class="sxs-lookup"><span data-stu-id="cc051-221">The C# host application has four parts:</span></span>

* <span data-ttu-id="cc051-222">Construa um simulador quântico.</span><span class="sxs-lookup"><span data-stu-id="cc051-222">Construct a quantum simulator.</span></span> <span data-ttu-id="cc051-223">No exemplo, `qsim` é o simulador.</span><span class="sxs-lookup"><span data-stu-id="cc051-223">In the example, `qsim` is the simulator.</span></span>
* <span data-ttu-id="cc051-224">Calcule todos os argumentos necessários do algoritmo quântico.</span><span class="sxs-lookup"><span data-stu-id="cc051-224">Compute any arguments required for the quantum algorithm.</span></span> <span data-ttu-id="cc051-225">No exemplo, o argumento `count` foi fixado em 1000 e `initial` é o valor inicial do qubit.</span><span class="sxs-lookup"><span data-stu-id="cc051-225">In the example, `count` is fixed at a 1000 and `initial` is the initial value of the qubit.</span></span>
* <span data-ttu-id="cc051-226">Execute o algoritmo quântico.</span><span class="sxs-lookup"><span data-stu-id="cc051-226">Run the quantum algorithm.</span></span> <span data-ttu-id="cc051-227">Cada operação Q# gera uma classe C# com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="cc051-227">Each Q# operation generates a C# class with the same name.</span></span> <span data-ttu-id="cc051-228">Esta classe possui um método `Run` que de forma **assíncrona** executa a operação.</span><span class="sxs-lookup"><span data-stu-id="cc051-228">This class has a `Run` method that **asynchronously** executes the operation.</span></span> <span data-ttu-id="cc051-229">A execução é assíncrona porque a execução no hardware real será assíncrona.</span><span class="sxs-lookup"><span data-stu-id="cc051-229">The execution is asynchronous because execution on actual hardware will be asynchronous.</span></span> <span data-ttu-id="cc051-230">Como o método `Run` é assíncrono, vamos obter a propriedade `Result`, que bloqueia a execução até que a tarefa seja concluída e devolva o resultado de forma síncrona.</span><span class="sxs-lookup"><span data-stu-id="cc051-230">Because the `Run` method is asynchronous, we fetch the `Result` property; this blocks execution until the task completes and returns the result synchronously.</span></span>
* <span data-ttu-id="cc051-231">Processe o resultado da operação.</span><span class="sxs-lookup"><span data-stu-id="cc051-231">Process the result of the operation.</span></span> <span data-ttu-id="cc051-232">No exemplo, `res` recebe o resultado da operação.</span><span class="sxs-lookup"><span data-stu-id="cc051-232">In the example, `res` receives the result of the operation.</span></span> <span data-ttu-id="cc051-233">Aqui, o resultado é uma cadeia de identificação do número de zeros (`numZeros`) e do número de uns (`numOnes`) medidos pelo simulador.</span><span class="sxs-lookup"><span data-stu-id="cc051-233">Here the result is a tuple of the number of zeros (`numZeros`) and number of ones (`numOnes`) measured by the simulator.</span></span> <span data-ttu-id="cc051-234">E, é devolvido como um ValueTuple em C#.</span><span class="sxs-lookup"><span data-stu-id="cc051-234">This is returned as a ValueTuple in C#.</span></span> <span data-ttu-id="cc051-235">Vamos desconstruir a cadeia de identificação para obter dois campos, imprimir os resultados e aguardar que uma tecla seja premida.</span><span class="sxs-lookup"><span data-stu-id="cc051-235">We deconstruct the tuple to get the two fields, print the results, and wait for a keypress.</span></span>

#### [](#tab/tabid-vs2019)

* * *

## <a name="build-and-run"></a><span data-ttu-id="cc051-236">Compilar e executar</span><span class="sxs-lookup"><span data-stu-id="cc051-236">Build and run</span></span>

#### <a name="pythontabtabid-python"></a>[<span data-ttu-id="cc051-237">Python</span><span class="sxs-lookup"><span data-stu-id="cc051-237">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="cc051-238">Execute o seguinte comando no terminal:</span><span class="sxs-lookup"><span data-stu-id="cc051-238">Run the following command at your terminal:</span></span>

    ```
    python host.py
    ```

    <span data-ttu-id="cc051-239">Este comando executa a aplicação anfitriã, que simula a operação Q#.</span><span class="sxs-lookup"><span data-stu-id="cc051-239">This command runs the host application, which simulates the Q# operation.</span></span>

<span data-ttu-id="cc051-240">Os resultados devem ser:</span><span class="sxs-lookup"><span data-stu-id="cc051-240">The results should be:</span></span>

```Output
Init:0    0s=1000 1s=0   
Init:1    0s=0    1s=1000
```

#### <a name="command-line--visual-studio-codetabtabid-csharp"></a>[<span data-ttu-id="cc051-241">Linha de Comandos/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="cc051-241">Command Line / Visual Studio Code</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="cc051-242">Execute o seguinte no terminal:</span><span class="sxs-lookup"><span data-stu-id="cc051-242">Run the following at your terminal:</span></span>

    ```bash
    dotnet run
    ```

    <span data-ttu-id="cc051-243">Este comando vai transferir automaticamente todos os pacotes necessários, compilar a aplicação e, em seguida, executar a linha de comandos.</span><span class="sxs-lookup"><span data-stu-id="cc051-243">This command will automatically download all required packages, build the application, then run it at the command line.</span></span>

1. <span data-ttu-id="cc051-244">Em alternativa, prima **F1** para abrir a Paleta de Comandos e selecione **Depurar: Iniciar sem Depuração**.</span><span class="sxs-lookup"><span data-stu-id="cc051-244">Alternatively, press **F1** to open the Command Palette and select **Debug: Start Without Debugging.**</span></span>
<span data-ttu-id="cc051-245">Pode ser-lhe pedido que crie um novo ficheiro ``launch.json``, onde descreve como iniciar o programa.</span><span class="sxs-lookup"><span data-stu-id="cc051-245">You may be prompted to create a new ``launch.json`` file describing how to start the program.</span></span>
<span data-ttu-id="cc051-246">A predefinição ``launch.json`` deve funcionar bem para a maioria das aplicações.</span><span class="sxs-lookup"><span data-stu-id="cc051-246">The default ``launch.json`` should work well for most applications.</span></span>

<span data-ttu-id="cc051-247">Os resultados devem ser:</span><span class="sxs-lookup"><span data-stu-id="cc051-247">The results should be:</span></span>

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

#### <a name="visual-studiotabtabid-vs2019"></a>[<span data-ttu-id="cc051-248">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cc051-248">Visual Studio</span></span>](#tab/tabid-vs2019)

1. <span data-ttu-id="cc051-249">Basta premir `F5` para o programa ser compilado e executado!</span><span class="sxs-lookup"><span data-stu-id="cc051-249">Just hit `F5`, and your program should build and run!</span></span>

<span data-ttu-id="cc051-250">Os resultados devem ser:</span><span class="sxs-lookup"><span data-stu-id="cc051-250">The results should be:</span></span>

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

<span data-ttu-id="cc051-251">O programa será encerrado após premir uma tecla.</span><span class="sxs-lookup"><span data-stu-id="cc051-251">The program will exit after you press a key.</span></span>

* * *

## <a name="prepare-superposition"></a><span data-ttu-id="cc051-252">Preparar a sobreposição</span><span class="sxs-lookup"><span data-stu-id="cc051-252">Prepare superposition</span></span>

<span data-ttu-id="cc051-253">**Descrição geral**: agora, vamos ver como o Q# expressa formas de colocar os qubits em sobreposição.</span><span class="sxs-lookup"><span data-stu-id="cc051-253">**Overview** Now let’s look at how Q# expresses ways to put qubits in superposition.</span></span>  <span data-ttu-id="cc051-254">Lembre-se de que o estado de um qubit pode estar numa sobreposição de 0 e 1.</span><span class="sxs-lookup"><span data-stu-id="cc051-254">Recall that the state of a qubit can be in a superposition of 0 and 1.</span></span>  <span data-ttu-id="cc051-255">Vamos utilizar a operação `Hadamard` para esta ação.</span><span class="sxs-lookup"><span data-stu-id="cc051-255">We’ll use the `Hadamard` operation to accomplish this.</span></span> <span data-ttu-id="cc051-256">Se o qubit estiver num dos estados clássicos (em que uma medição devolve sempre `Zero` ou `One`), a operação `Hadamard` ou `H` colocará o qubit num estado em que uma medição do qubit devolverá `Zero` e `One` 50% do tempo.</span><span class="sxs-lookup"><span data-stu-id="cc051-256">If the qubit is in either of the classical states (where a measurement returns `Zero` always or `One` always), then the `Hadamard` or `H` operation will put the qubit in a state where a measurement of the qubit will return `Zero` 50% of the time and return `One` 50% of the time.</span></span>  <span data-ttu-id="cc051-257">Conceitualmente, o qubit pode ser pensado como estando entre `Zero` e `One`.</span><span class="sxs-lookup"><span data-stu-id="cc051-257">Conceputually, the qubit can be thought of as halfway between the `Zero` and `One`.</span></span>  <span data-ttu-id="cc051-258">Agora, quando simularmos a operação `TestBellState`, veremos que os resultados vão devolver aproximadamente um número igual de `Zero` e `One` após a medição.</span><span class="sxs-lookup"><span data-stu-id="cc051-258">Now, when we simulate the `TestBellState` operation, we will see the results will return roughly an equal number of `Zero` and `One` after measurement.</span></span>  

<span data-ttu-id="cc051-259">Primeiro, vamos tentar inverter o qubit (se este estiver num estado `Zero`, será invertido para `One` e vice-versa).</span><span class="sxs-lookup"><span data-stu-id="cc051-259">First we'll just try to flip the qubit (if the qubit is in `Zero` state will flip to `One` and vice versa).</span></span> <span data-ttu-id="cc051-260">Esta inversão pode ser feita ao realizar uma operação `X` antes de o medir em `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="cc051-260">This is accomplished by performing an `X` operation before we measure it in `TestBellState`:</span></span>

```qsharp
X(qubit);
let res = M(qubit);
```

<span data-ttu-id="cc051-261">Os resultados (após premir `F5`) são invertidos:</span><span class="sxs-lookup"><span data-stu-id="cc051-261">Now the results (after pressing `F5`) are reversed:</span></span>

```Output
Init:Zero 0s=0    1s=1000
Init:One  0s=1000 1s=0
```

<span data-ttu-id="cc051-262">No entanto, tudo o que vimos até agora é clássico.</span><span class="sxs-lookup"><span data-stu-id="cc051-262">However, everything we've seen so far is classical.</span></span> <span data-ttu-id="cc051-263">Vamos, então, obter um resultado quântico.</span><span class="sxs-lookup"><span data-stu-id="cc051-263">Let's get a quantum result.</span></span> <span data-ttu-id="cc051-264">Para tal, só precisamos de substituir a operação `X` na execução anterior por uma operação `H` ou Hadamard.</span><span class="sxs-lookup"><span data-stu-id="cc051-264">All we need to do is replace the `X` operation in the previous run with an `H` or Hadamard operation.</span></span> <span data-ttu-id="cc051-265">Em vez de inverter totalmente o qubit de 0 para 1, vamos invertê-lo apenas metade.</span><span class="sxs-lookup"><span data-stu-id="cc051-265">Instead of flipping the qubit all the way from 0 to 1, we will only flip it halfway.</span></span> <span data-ttu-id="cc051-266">As linhas substituídas em `TestBellState` agora são semelhantes ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="cc051-266">The replaced lines in `TestBellState` now look like:</span></span>

```qsharp
H(qubit);
let res = M(qubit);
```

<span data-ttu-id="cc051-267">Os resultados começam a ficar mais interessantes:</span><span class="sxs-lookup"><span data-stu-id="cc051-267">Now the results get more interesting:</span></span>

```Output
Init:Zero 0s=484  1s=516
Init:One  0s=522  1s=478
```

<span data-ttu-id="cc051-268">Sempre que medimos, pedimos um valor clássico, mas o qubit encontra-se a meio entre 0 e 1 e assim obtemos (estatisticamente) 0 metade das vezes e 1 metade das vezes,</span><span class="sxs-lookup"><span data-stu-id="cc051-268">Every time we measure, we ask for a classical value, but the qubit is halfway between 0 and 1, so we get (statistically) 0 half the time and 1 half the time.</span></span> <span data-ttu-id="cc051-269">o quer é conhecido como __sobreposição__ e dá-nos a nossa primeira vista real de um estado quântico.</span><span class="sxs-lookup"><span data-stu-id="cc051-269">This is known as __superposition__ and gives us our first real view into a quantum state.</span></span>

## <a name="prepare-entanglement"></a><span data-ttu-id="cc051-270">Preparar o entrelaçamento</span><span class="sxs-lookup"><span data-stu-id="cc051-270">Prepare entanglement</span></span>

<span data-ttu-id="cc051-271">**Descrição geral:**  agora, vamos ver como o Q# expressa formas de entrelaçar os qubits.</span><span class="sxs-lookup"><span data-stu-id="cc051-271">**Overview:**  Now let’s look at how Q# expresses ways to entangle qubits.</span></span>  <span data-ttu-id="cc051-272">Primeiro, definimos o primeiro qubit para o estado inicial e utilizamos a operação `H` para colocá-lo em sobreposição.</span><span class="sxs-lookup"><span data-stu-id="cc051-272">First, we set the first qubit to the initial state and then use the `H` operation to put it into superposition.</span></span>  <span data-ttu-id="cc051-273">Em seguida, antes de medirmos o primeiro qubit, utilizamos uma nova operação (`CNOT`), que significa Controlled-Not (Não Controlado).</span><span class="sxs-lookup"><span data-stu-id="cc051-273">Then, before we measure the first qubit, we use a new operation (`CNOT`), which stands for Controlled-Not.</span></span>  <span data-ttu-id="cc051-274">O resultado da execução desta operação em dois qubits é inverter o segundo qubit se o primeiro qubit for `One`.</span><span class="sxs-lookup"><span data-stu-id="cc051-274">The result of executing this operation on two qubits is to flip the second qubit if the first qubit is `One`.</span></span>  <span data-ttu-id="cc051-275">Agora, os dois qubits estão entrelaçados.</span><span class="sxs-lookup"><span data-stu-id="cc051-275">Now, the two qubits are entangled.</span></span>  <span data-ttu-id="cc051-276">As nossas estatísticas para o primeiro qubit não foram alteradas (uma probabilidade de 50-50 de um `Zero` ou de um `One` após a medição), mas quando medirmos o segundo qubit, este será __sempre__ igual ao que medimos para o primeiro qubit.</span><span class="sxs-lookup"><span data-stu-id="cc051-276">Our statistics for the first qubit haven't changed (50-50 chance of a `Zero` or a `One` after measurement), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit.</span></span> <span data-ttu-id="cc051-277">O nosso `CNOT` entrelaçou os dois qubits, de modo a que aquilo que acontecer a um deles, aconteça também ao outro.</span><span class="sxs-lookup"><span data-stu-id="cc051-277">Our `CNOT` has entangled the two qubits, so that whatever happens to one of them, happens to the other.</span></span> <span data-ttu-id="cc051-278">Se as medições fossem invertidas (a medição do segundo qubit antes do primeiro), aconteceria a mesma coisa.</span><span class="sxs-lookup"><span data-stu-id="cc051-278">If you reversed the measurements (did the second qubit before the first), the same thing would happen.</span></span> <span data-ttu-id="cc051-279">A primeira medida seria aleatória e a segunda estaria num passo bloqueado para a medição que tivesse sido detetada primeiro.</span><span class="sxs-lookup"><span data-stu-id="cc051-279">The first measurement would be random and the second would be in lock step with whatever was discovered for the first.</span></span>

<span data-ttu-id="cc051-280">A primeira coisa que vamos precisar de fazer é alocar dois qubits em vez de um em `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="cc051-280">The first thing we'll need to do is allocate 2 qubits instead of one in `TestBellState`:</span></span>

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

<span data-ttu-id="cc051-281">Este procedimento vai permitir adicionar uma nova operação (`CNOT`) antes de medir (`M`) em `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="cc051-281">This will allow us to add a new operation (`CNOT`) before we measure  (`M`) in `TestBellState`:</span></span>

```qsharp
Set(initial, q0);
Set(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

<span data-ttu-id="cc051-282">Adicionámos outra operação `Set` para inicializar o primeiro qubit para confirmar que está sempre no estado `Zero` quando começamos.</span><span class="sxs-lookup"><span data-stu-id="cc051-282">We've added another `Set` operation to initialize the first qubit to make sure that it's always in the `Zero` state when we start.</span></span>

<span data-ttu-id="cc051-283">Precisamos também de redefinir o segundo qubit antes de o libertar.</span><span class="sxs-lookup"><span data-stu-id="cc051-283">We also need to reset the second qubit before releasing it.</span></span>

```qsharp
Set(Zero, q0);
Set(Zero, q1);
```

<span data-ttu-id="cc051-284">A rotina completa é agora semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="cc051-284">The full routine now looks like this:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set (initial, q0);
                Set (Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

<span data-ttu-id="cc051-285">Se a executarmos, vamos obter exatamente o mesmo resultado de 50-50 que obtivemos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="cc051-285">If we run this, we'll get exactly the same 50-50 result we got before.</span></span> <span data-ttu-id="cc051-286">No entanto, o que nos interessa é a forma como o segundo qubit reage à primeira medição.</span><span class="sxs-lookup"><span data-stu-id="cc051-286">However, what we're interested in is how the second qubit reacts to the first being measured.</span></span> <span data-ttu-id="cc051-287">Vamos adicionar esta estatística com a nova versão da operação `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="cc051-287">We'll add this statistic with a new version of the `TestBellState` operation:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set(initial, q0);
                Set(Zero, q1);

                H(q0);
                CNOT(q0, q1);
                let res = M(q0);

                if (M(q1) == res) {
                    set agree += 1;
                }

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes, agree);
    }
```

<span data-ttu-id="cc051-288">O novo valor de retorno (`agree`) controla cada vez que a medição do primeiro qubit corresponde à medição do segundo qubit.</span><span class="sxs-lookup"><span data-stu-id="cc051-288">The new return value (`agree`) keeps track of every time the measurement from the first qubit matches the measurement of the second qubit.</span></span> <span data-ttu-id="cc051-289">É também necessário atualizar a aplicação anfitriã em conformidade:</span><span class="sxs-lookup"><span data-stu-id="cc051-289">We also have to update the host application accordingly:</span></span>

#### <a name="pythontabtabid-python"></a>[<span data-ttu-id="cc051-290">Python</span><span class="sxs-lookup"><span data-stu-id="cc051-290">Python</span></span>](#tab/tabid-python)

```python
import qsharp

from qsharp import Result
from Quantum.Bell import TestBellState

initials = {Result.Zero, Result.One} 

for i in initials:
    res = TestBellState.simulate(count=1000, initial=i)
    (num_zeros, num_ones, agree) = res
    print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4} agree={agree: <4}')
```

#### <a name="ctabtabid-csharp"></a>[<span data-ttu-id="cc051-291">C#</span><span class="sxs-lookup"><span data-stu-id="cc051-291">C#</span></span>](#tab/tabid-csharp)

```csharp
            using (var qsim = new QuantumSimulator())
            {
                // Try initial values
                Result[] initials = new Result[] { Result.Zero, Result.One };
                foreach (Result initial in initials)
                {
                    var res = TestBellState.Run(qsim, 1000, initial).Result;
                    var (numZeros, numOnes, agree) = res;
                    System.Console.WriteLine(
                        $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4} agree={agree,-4}");
                }
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
```

#### [](#tab/tabid-vs2019)

* * *

<span data-ttu-id="cc051-292">Agora, quando executarmos, vamos obter um resultado incrível:</span><span class="sxs-lookup"><span data-stu-id="cc051-292">Now when we run, we get something pretty amazing:</span></span>

```Output
Init:Zero 0s=499  1s=501  agree=1000
Init:One  0s=490  1s=510  agree=1000
```

<span data-ttu-id="cc051-293">Conforme mencionado na descrição geral, as nossas estatísticas para o primeiro qubit não foram alteradas (uma probabilidade de 50-50 de um 0 ou de um 1), mas quando medirmos o segundo qubit, este será __sempre__ igual ao que medimos para o primeiro qubit, uma vez que estão entrelaçados!</span><span class="sxs-lookup"><span data-stu-id="cc051-293">As stated in the overview, our statistics for the first qubit haven't changed (50-50 chance of a 0 or a 1), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit, because they are entangled!</span></span>

<span data-ttu-id="cc051-294">Parabéns! Acabou de escrever o primeiro programa quântico.</span><span class="sxs-lookup"><span data-stu-id="cc051-294">Congratulations, you've written your first quantum program!</span></span>

## <a name="whats-next"></a><span data-ttu-id="cc051-295">Passos seguintes?</span><span class="sxs-lookup"><span data-stu-id="cc051-295">What's next?</span></span>

<span data-ttu-id="cc051-296">O Início Rápido [Pesquisa de Grover](xref:microsoft.quantum.quickstarts.search) mostra como compilar e executar a pesquisa de Grover, um dos algoritmos de computação quântica mais populares e dá um ótimo exemplo de um programa Q# que pode ser utilizado para resolver problemas reais através de computação quântica.</span><span class="sxs-lookup"><span data-stu-id="cc051-296">The QuickStart [Grover’s search](xref:microsoft.quantum.quickstarts.search) shows you how to build and run Grover search, one of the most popular quantum computing algorithms and offers a nice example of a Q# program that can be used to solve real problems with quantum computing.</span></span>  

<span data-ttu-id="cc051-297">A [Introdução ao Quantum Development Kit](xref:microsoft.quantum.welcome) recomenda mais formas de aprender a linguagem Q# e a programação quântica.</span><span class="sxs-lookup"><span data-stu-id="cc051-297">[Get Started with the Quantum Development Kit](xref:microsoft.quantum.welcome) recommends more ways to learn Q# and quantum programming.</span></span>

