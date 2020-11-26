---
title: Explore o emaranhado com Q#
description: Aprenda a escrever um programa quântico em Q# . Desenvolver uma aplicação de Estado de Bell com o Quantum Development Kit (QDK)
author: geduardo
ms.author: v-edsanc
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4c73a070fea2ce69a0bce9bf293a4679727e27bc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192032"
---
# <a name="tutorial-explore-entanglement-with-q"></a><span data-ttu-id="a8333-104">Tutorial: Explorar o entrelaçamento com Q\#</span><span class="sxs-lookup"><span data-stu-id="a8333-104">Tutorial: Explore entanglement with Q\#</span></span>

<span data-ttu-id="a8333-105">Neste tutorial, mostramos-lhe como escrever um Q# programa que manipula e mede qubits e demonstra os efeitos da superposição e do emaranhado.</span><span class="sxs-lookup"><span data-stu-id="a8333-105">In this tutorial, we show you how to write a Q# program that manipulates and measures qubits and demonstrates the effects of superposition and entanglement.</span></span> 

<span data-ttu-id="a8333-106">Vai escrever uma aplicação denominada Bell para demonstrar o entrelaçamento quântico.</span><span class="sxs-lookup"><span data-stu-id="a8333-106">You will write an application called Bell to demonstrate quantum entanglement.</span></span>
<span data-ttu-id="a8333-107">O nome Bell refere-se aos estados de Bell, que são estados quânticos específicos de dois qubits, utilizados para representar os exemplos mais simples de sobreposição e de entrelaçamento quântico.</span><span class="sxs-lookup"><span data-stu-id="a8333-107">The name Bell is in reference to Bell states, which are specific quantum states of two qubits that are used to represent the simplest examples of superposition and quantum entanglement.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="a8333-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="a8333-108">Pre-requisites</span></span>

<span data-ttu-id="a8333-109">Se estiver preparado para começar a programar, siga estes passos antes de continuar:</span><span class="sxs-lookup"><span data-stu-id="a8333-109">If you are ready to start coding, follow these steps before proceeding:</span></span>

* <span data-ttu-id="a8333-110">[Instale](xref:microsoft.quantum.install) o Kit de Desenvolvimento Quântico utilizando o seu ambiente de linguagem e desenvolvimento preferido.</span><span class="sxs-lookup"><span data-stu-id="a8333-110">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your  preferred language and development environment.</span></span> 
* <span data-ttu-id="a8333-111">Se já tiver o QDK instalado, confirme que o [atualizou](xref:microsoft.quantum.update) para a versão mais recente</span><span class="sxs-lookup"><span data-stu-id="a8333-111">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>

<span data-ttu-id="a8333-112">Também pode acompanhar a narrativa sem instalar o QDK, revendo as visãos gerais da linguagem de Q# programação e os primeiros conceitos de computação quântica.</span><span class="sxs-lookup"><span data-stu-id="a8333-112">You can also follow along with the narrative without installing the QDK, reviewing  the overviews of the Q# programming language and the first concepts of quantum computing.</span></span>

## <a name="in-this-tutorial-youll-learn-how-to"></a><span data-ttu-id="a8333-113">Neste tutorial, irá aprender a:</span><span class="sxs-lookup"><span data-stu-id="a8333-113">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="a8333-114">Criar e combinar operações em Q\#</span><span class="sxs-lookup"><span data-stu-id="a8333-114">Create and combine operations in Q\#</span></span>
> * <span data-ttu-id="a8333-115">Criar operações para colocar qubits em superposição, enredar e medi-los.</span><span class="sxs-lookup"><span data-stu-id="a8333-115">Create operations to put qubits in superposition, entangle and measure them.</span></span>
> * <span data-ttu-id="a8333-116">Demonstre o emaranhado quântico com um Q# programa executado num simulador.</span><span class="sxs-lookup"><span data-stu-id="a8333-116">Demonstrate quantum entanglement with a Q# program run in a simulator.</span></span> 

## <a name="demonstrating-qubit-behavior-with-the-qdk"></a><span data-ttu-id="a8333-117">Demonstrando comportamento qubit com o QDK</span><span class="sxs-lookup"><span data-stu-id="a8333-117">Demonstrating qubit behavior with the QDK</span></span>

<span data-ttu-id="a8333-118">Enquanto os bits clássicos contêm um único valor binário como 0 ou 1, o estado de um [qubit](xref:microsoft.quantum.glossary#qubit) pode estar numa **sobreposição** de 0 e 1.</span><span class="sxs-lookup"><span data-stu-id="a8333-118">Where classical bits hold a single binary value such as a 0 or 1, the state of a [qubit](xref:microsoft.quantum.glossary#qubit) can be in a **superposition** of 0 and 1.</span></span>  <span data-ttu-id="a8333-119">Conceptualmente, o estado de um qubit pode ser considerado como uma direção em um espaço abstrato (também conhecido como um vetor).</span><span class="sxs-lookup"><span data-stu-id="a8333-119">Conceptually, the state of a qubit can be thought of as a direction in an abstract space (also known as a vector).</span></span>  <span data-ttu-id="a8333-120">Um estado qubit pode estar em qualquer uma das direções possíveis.</span><span class="sxs-lookup"><span data-stu-id="a8333-120">A qubit state can be in any of the possible directions.</span></span> <span data-ttu-id="a8333-121">Os dois **estados clássicos** são as duas direções, que representam 100% de probabilidade de medir 0 e 100% de probabilidade de medir 1.</span><span class="sxs-lookup"><span data-stu-id="a8333-121">The two **classical states** are the two directions; representing 100% chance of measuring 0 and 100% chance of measuring 1.</span></span>

<span data-ttu-id="a8333-122">O ato de medição produz um resultado binário e altera o estado de um qubit.</span><span class="sxs-lookup"><span data-stu-id="a8333-122">The act of measurement produces a binary result and changes a qubit state.</span></span>
<span data-ttu-id="a8333-123">A medição produz um valor binário, 0 ou 1.</span><span class="sxs-lookup"><span data-stu-id="a8333-123">Measurement  produces a binary value, either 0 or 1.</span></span>  <span data-ttu-id="a8333-124">O qubit vai do estado de sobreposição (qualquer direção) até um dos estados clássicos.</span><span class="sxs-lookup"><span data-stu-id="a8333-124">The qubit goes from being in superposition (any direction) to one of the classical states.</span></span>  <span data-ttu-id="a8333-125">Depois disso, repetir a mesma medição sem nenhuma operação intermediária produz o mesmo resultado binário.</span><span class="sxs-lookup"><span data-stu-id="a8333-125">Thereafter, repeating the same measurement without any intervening operations produces the same binary result.</span></span>  

<span data-ttu-id="a8333-126">É possível [**entrelaçar**](xref:microsoft.quantum.glossary#entanglement) vários qubits.</span><span class="sxs-lookup"><span data-stu-id="a8333-126">Multiple qubits can be [**entangled**](xref:microsoft.quantum.glossary#entanglement).</span></span>  <span data-ttu-id="a8333-127">Quando fazemos a medição de um qubit entrelaçado, o nosso conhecimento do estado do(s) outro(s) também é atualizado.</span><span class="sxs-lookup"><span data-stu-id="a8333-127">When we make a measurement of one entangled qubit, our knowledge of the state of the other(s) is updated as well.</span></span>

<span data-ttu-id="a8333-128">Estamos prontos para demonstrar como Q# expressa este comportamento.</span><span class="sxs-lookup"><span data-stu-id="a8333-128">Now, we're ready to demonstrate how Q# expresses this behavior.</span></span>  <span data-ttu-id="a8333-129">Vai começar com o programa mais simples possível e compilá-lo para demonstrar a sobreposição quântica e o entrelaçamento quântico.</span><span class="sxs-lookup"><span data-stu-id="a8333-129">You start with the simplest program possible and build it up to demonstrate quantum superposition and quantum entanglement.</span></span>

## <a name="creating-a-no-locq-project"></a><span data-ttu-id="a8333-130">Criar um Q# projeto</span><span class="sxs-lookup"><span data-stu-id="a8333-130">Creating a Q# project</span></span>

<span data-ttu-id="a8333-131">A primeira coisa a fazer é criar um novo Q# projeto.</span><span class="sxs-lookup"><span data-stu-id="a8333-131">The first thing we have to do is to create a new Q# project.</span></span> <span data-ttu-id="a8333-132">Neste tutorial vamos utilizar o ambiente com base em [ Q# aplicações com o Código VS.](xref:microsoft.quantum.install.standalone)</span><span class="sxs-lookup"><span data-stu-id="a8333-132">In this tutorial we are going to use the environment based on [Q# applications with VS Code](xref:microsoft.quantum.install.standalone).</span></span>

<span data-ttu-id="a8333-133">Para criar um novo projeto, em Código VS:</span><span class="sxs-lookup"><span data-stu-id="a8333-133">To create a new project, in VS Code:</span></span> 

1. <span data-ttu-id="a8333-134">Clique em **View** (Ver)  -> **Command Palette** (Paleta de Comandos) e selecione **Q#: Create New Project** (Criar Novo Projeto).</span><span class="sxs-lookup"><span data-stu-id="a8333-134">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="a8333-135">Clique em **Standalone console application** (Aplicação de consola autónoma).</span><span class="sxs-lookup"><span data-stu-id="a8333-135">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="a8333-136">Navegue para a localização para guardar o projeto e clique em **Create Project** (Criar Projeto).</span><span class="sxs-lookup"><span data-stu-id="a8333-136">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="a8333-137">Após a criação do projeto, clique em **Open new project...** (Abrir novo projeto...) no canto inferior direito.</span><span class="sxs-lookup"><span data-stu-id="a8333-137">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="a8333-138">Neste caso, chamámos o `Bell` projeto.</span><span class="sxs-lookup"><span data-stu-id="a8333-138">In this case we called the project `Bell`.</span></span> <span data-ttu-id="a8333-139">Isto gera dois ficheiros: `Bell.csproj` o ficheiro do projeto `Program.qs` e, um modelo de uma Q# aplicação que usaremos para escrever a nossa aplicação.</span><span class="sxs-lookup"><span data-stu-id="a8333-139">This generates two files: `Bell.csproj`, the project file and `Program.qs`, a template of a Q# application that we will use to write our application.</span></span> <span data-ttu-id="a8333-140">O conteúdo `Program.qs` deve ser:</span><span class="sxs-lookup"><span data-stu-id="a8333-140">The content of `Program.qs` should be:</span></span>

```qsharp
   namespace Bell {

      open Microsoft.Quantum.Canon;
      open Microsoft.Quantum.Intrinsic;
    

      @EntryPoint()
      operation HelloQ() : Unit {
          Message("Hello quantum world!");
      }
   }
```

## <a name="write-the-q-application"></a><span data-ttu-id="a8333-141">Escreva a \# aplicação Q</span><span class="sxs-lookup"><span data-stu-id="a8333-141">Write the Q\# application</span></span>
 
<span data-ttu-id="a8333-142">O nosso objetivo é preparar dois qubits num estado quântico específico, demonstrando como operar em qubits Q# para mudar o seu estado e demonstrar os efeitos da sobreposição e do emaranhado.</span><span class="sxs-lookup"><span data-stu-id="a8333-142">Our goal is to prepare two qubits in a specific quantum state, demonstrating how to operate on qubits with Q# to change their state and demonstrate the effects of superposition and entanglement.</span></span> <span data-ttu-id="a8333-143">Vamos construir isto peça a peça para introduzir estados qubit, operações e medição.</span><span class="sxs-lookup"><span data-stu-id="a8333-143">We will build this up piece by piece to introduce qubit states, operations, and measurement.</span></span>

### <a name="initialize-qubit-using-measurement"></a><span data-ttu-id="a8333-144">Inicialize o qubit usando a medição</span><span class="sxs-lookup"><span data-stu-id="a8333-144">Initialize qubit using measurement</span></span>

<span data-ttu-id="a8333-145">No primeiro corte de código abaixo, mostramos-lhe como trabalhar com qubits em Q# .</span><span class="sxs-lookup"><span data-stu-id="a8333-145">In the first code snippet below, we show you how to work with qubits in Q#.</span></span>  <span data-ttu-id="a8333-146">Vamos introduzir duas operações, [`M`](xref:Microsoft.Quantum.Intrinsic.M) e [`X`](xref:Microsoft.Quantum.Intrinsic.X) que transformam o estado de um qubit.</span><span class="sxs-lookup"><span data-stu-id="a8333-146">We’ll introduce two operations, [`M`](xref:Microsoft.Quantum.Intrinsic.M) and [`X`](xref:Microsoft.Quantum.Intrinsic.X) that transform the state of a qubit.</span></span> <span data-ttu-id="a8333-147">Neste fragmento de código, é definida uma operação `SetQubitState`, que utiliza um qubit como parâmetro e outro parâmetro, `desired`, que representa o estado em que queremos que o qubit esteja.</span><span class="sxs-lookup"><span data-stu-id="a8333-147">In this code snippet, an operation `SetQubitState` is defined that takes as a parameter a qubit and another parameter, `desired`, representing the state that we would like the qubit to be in.</span></span>  <span data-ttu-id="a8333-148">A operação `SetQubitState` executa uma medição no qubit através da operação `M`.</span><span class="sxs-lookup"><span data-stu-id="a8333-148">The operation `SetQubitState` performs a measurement on the qubit using the operation `M`.</span></span>  <span data-ttu-id="a8333-149">Em Q# , uma medição de qubit sempre retorna ou `Zero` . `One` .</span><span class="sxs-lookup"><span data-stu-id="a8333-149">In Q#, a qubit measurement always returns either `Zero` or `One`.</span></span>  <span data-ttu-id="a8333-150">Se a medição devolver um valor não igual ao valor pretendido, `SetQubitState` "inverte" o qubit; ou seja, executa uma `X` operação, que altera o estado qubit para um novo estado em que as probabilidades de uma medição regressam `Zero` e são `One` invertidas.</span><span class="sxs-lookup"><span data-stu-id="a8333-150">If the measurement returns a value not equal to the desired value, `SetQubitState` “flips” the qubit; that is, it runs an `X` operation, which changes the qubit state to a new state in which the probabilities of a measurement returning `Zero` and `One` are reversed.</span></span> <span data-ttu-id="a8333-151">Desta forma, `SetQubitState` coloca sempre o qubit alvo no estado desejado.</span><span class="sxs-lookup"><span data-stu-id="a8333-151">This way, `SetQubitState` always puts the target qubit in the desired state.</span></span>

<span data-ttu-id="a8333-152">Substitua o conteúdo do `Program.qs` seguinte código:</span><span class="sxs-lookup"><span data-stu-id="a8333-152">Replace the contents of `Program.qs` with the following code:</span></span>


```qsharp
   namespace Bell {
       open Microsoft.Quantum.Intrinsic;
       open Microsoft.Quantum.Canon;

       operation SetQubitState(desired : Result, q1 : Qubit) : Unit {
           if (desired != M(q1)) {
               X(q1);
           }
       }
   }
```

<span data-ttu-id="a8333-153">Esta operação agora pode ser chamada para definir um qubit para um estado clássico, ao devolver `Zero` ou `One` 100% do tempo.</span><span class="sxs-lookup"><span data-stu-id="a8333-153">This operation may now be called to set a qubit to a classical state, either returning `Zero` 100% of the time or returning `One` 100% of the time.</span></span>
<span data-ttu-id="a8333-154">`Zero` e `One` são constantes que representam os dois únicos resultados possíveis da medição de um qubit.</span><span class="sxs-lookup"><span data-stu-id="a8333-154">`Zero` and `One` are constants that represent the only two possible results of a measurement of a qubit.</span></span>

<span data-ttu-id="a8333-155">A operação `SetQubitState` mede o qubit.</span><span class="sxs-lookup"><span data-stu-id="a8333-155">The operation `SetQubitState` measures the qubit.</span></span> <span data-ttu-id="a8333-156">Se o qubit está no estado que `SetQubitState` queremos, deixa-o em paz; caso contrário, ao executar a `X` operação, mudamos o estado qubit para o estado desejado.</span><span class="sxs-lookup"><span data-stu-id="a8333-156">If the qubit is in the state we want, `SetQubitState` leaves it alone; otherwise, by running the `X` operation, we change the qubit state to the desired state.</span></span>

#### <a name="about-no-locq-operations"></a><span data-ttu-id="a8333-157">Sobre Q# operações</span><span class="sxs-lookup"><span data-stu-id="a8333-157">About Q# operations</span></span>

<span data-ttu-id="a8333-158">Uma Q# operação é uma sub-rotina quântica.</span><span class="sxs-lookup"><span data-stu-id="a8333-158">A Q# operation is a quantum subroutine.</span></span> <span data-ttu-id="a8333-159">Ou seja, é uma rotina callable que contém chamadas para outras operações quânticas.</span><span class="sxs-lookup"><span data-stu-id="a8333-159">That is, it is a callable routine that contains calls to other quantum operations.</span></span>

<span data-ttu-id="a8333-160">Os argumentos para uma operação são especificados como uma cadeia de identificação, entre parênteses.</span><span class="sxs-lookup"><span data-stu-id="a8333-160">The arguments to an operation are specified as a tuple, within parentheses.</span></span>

<span data-ttu-id="a8333-161">O tipo de retorno da operação é especificado após os dois pontos.</span><span class="sxs-lookup"><span data-stu-id="a8333-161">The return type of the operation is specified after a colon.</span></span> <span data-ttu-id="a8333-162">Neste caso, a `SetQubitState` operação não tem tipo de retorno, pelo que está marcada como devolução `Unit` .</span><span class="sxs-lookup"><span data-stu-id="a8333-162">In this case, the `SetQubitState` operation has no return type, so it is marked as returning `Unit`.</span></span> <span data-ttu-id="a8333-163">Este é o Q# equivalente `unit` a em F#, que é aproximadamente análogo a `void` em C#, e um tuple vazio em Python `()` (, representado pelo tipo de sugestão). `Tuple[()]`</span><span class="sxs-lookup"><span data-stu-id="a8333-163">This is the Q# equivalent of `unit` in F#, which is roughly analogous to `void` in C#, and an empty tuple in Python (`()`, represented by the type hint `Tuple[()]`).</span></span>

<span data-ttu-id="a8333-164">Usaste duas operações quânticas na tua primeira Q# operação:</span><span class="sxs-lookup"><span data-stu-id="a8333-164">You have used two quantum operations in your first Q# operation:</span></span>

* <span data-ttu-id="a8333-165">A [`M`](xref:Microsoft.Quantum.Intrinsic.M) operação, que mede o estado do qubit</span><span class="sxs-lookup"><span data-stu-id="a8333-165">The [`M`](xref:Microsoft.Quantum.Intrinsic.M) operation, which measures the state of the qubit</span></span>
* <span data-ttu-id="a8333-166">A [`X`](xref:Microsoft.Quantum.Intrinsic.X) operação, que inverte o estado de um qubit</span><span class="sxs-lookup"><span data-stu-id="a8333-166">The [`X`](xref:Microsoft.Quantum.Intrinsic.X) operation, which flips the state of a qubit</span></span>

<span data-ttu-id="a8333-167">Uma operação quântica transforma o estado de um qubit.</span><span class="sxs-lookup"><span data-stu-id="a8333-167">A quantum operation transforms the state of a qubit.</span></span> <span data-ttu-id="a8333-168">Por vezes, as pessoas falam sobre portas quânticas em vez de operações, em analogia às portas de lógica clássicas e</span><span class="sxs-lookup"><span data-stu-id="a8333-168">Sometime people talk about quantum gates instead of operations, in analogy to classical logic gates.</span></span> <span data-ttu-id="a8333-169">que tem origem nos primórdios da computação quântica quando os algoritmos eram meramente uma construção teórica e visualizados como diagramas da mesma forma que os diagramas de circuito na computação clássica.</span><span class="sxs-lookup"><span data-stu-id="a8333-169">This is rooted in the early days of quantum computing when algorithms were merely a theoretical construct and visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>

### <a name="counting-measurement-outcomes"></a><span data-ttu-id="a8333-170">Contagem dos resultados da medição</span><span class="sxs-lookup"><span data-stu-id="a8333-170">Counting measurement outcomes</span></span>

<span data-ttu-id="a8333-171">Para demonstrar o efeito da operação `SetQubitState`, é adicionada uma operação `TestBellState`.</span><span class="sxs-lookup"><span data-stu-id="a8333-171">To demonstrate the effect of the `SetQubitState` operation, a `TestBellState` operation is then added.</span></span> <span data-ttu-id="a8333-172">Esta operação utiliza como entrada `Zero` ou `One`, chama a operação `SetQubitState` várias vezes com essa entrada e contabiliza o número de vezes que `Zero` foi devolvido pela medição do qubit e o número de vezes que `One` foi devolvido.</span><span class="sxs-lookup"><span data-stu-id="a8333-172">This operation takes as input a `Zero` or `One`, and calls the `SetQubitState` operation some number of times with that input, and counts the number of times that `Zero` was returned from the measurement of the qubit and the number of times that `One` was returned.</span></span> <span data-ttu-id="a8333-173">Como é óbvio, nesta primeira simulação da operação `TestBellState`, esperamos que o resultado mostre que todas as medições do conjunto de qubits com `Zero` como entrada de parâmetro devolva `Zero` e todas as medições de um conjunto de qubits com `One` como entrada de parâmetro devolva `One`.</span><span class="sxs-lookup"><span data-stu-id="a8333-173">Of course, in this first simulation of the `TestBellState` operation, we expect that the output will show that all measurements of the qubit set with `Zero` as the parameter input will return `Zero`, and all measurements of a qubit set with `One` as the parameter input will return `One`.</span></span> <span data-ttu-id="a8333-174">Mais à frente, vamos adicionar código `TestBellState` para demonstrar superposição e emaranhamento.</span><span class="sxs-lookup"><span data-stu-id="a8333-174">Further on, we’ll add code to `TestBellState` to demonstrate superposition and entanglement.</span></span>

<span data-ttu-id="a8333-175">Adicione a seguinte operação ao ficheiro `Program.qs`, dentro do espaço de nomes, após o fim da operação `SetQubitState`:</span><span class="sxs-lookup"><span data-stu-id="a8333-175">Add the following operation to the `Program.qs` file, inside the namespace, after the end of the `SetQubitState` operation:</span></span>

```qsharp
   operation TestBellState(count : Int, initial : Result) : (Int, Int) {

       mutable numOnes = 0;
       using (qubit = Qubit()) {

           for (test in 1..count) {
               SetQubitState(initial, qubit);
               let res = M(qubit);

               // Count the number of ones we saw:
               if (res == One) {
                   set numOnes += 1;
               }
           }
            
           SetQubitState(Zero, qubit);
       }

       // Return number of times we saw a |0> and number of times we saw a |1>
       Message("Test results (# of 0s, # of 1s): ");
       return (count - numOnes, numOnes);
   }
```
<span data-ttu-id="a8333-176">Note que adicionámos uma linha antes de `return` imprimir uma mensagem explicativa na consola com a função `Message` ()[microsoft.quantum.intrínseca.message]</span><span class="sxs-lookup"><span data-stu-id="a8333-176">Note that we added a line before the `return` to print an explanatory message in the console with the function (`Message`)[microsoft.quantum.intrinsic.message]</span></span>

<span data-ttu-id="a8333-177">Esta operação (`TestBellState`) vai gerar um ciclo de `count` iterações, definir um valor `initial` especificado num qubit e, em seguida, medir (`M`) o resultado.</span><span class="sxs-lookup"><span data-stu-id="a8333-177">This operation (`TestBellState`) will loop for `count` iterations, set a specified `initial` value on a qubit and then measure (`M`) the result.</span></span> <span data-ttu-id="a8333-178">Vai recolher estatísticas sobre quantos zeros e uns foram medidos e devolvê-los ao autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="a8333-178">It will gather statistics on how many zeros and ones we've measured and return them to the caller.</span></span> <span data-ttu-id="a8333-179">E, executa ainda outra operação necessária.</span><span class="sxs-lookup"><span data-stu-id="a8333-179">It performs one other necessary operation.</span></span> <span data-ttu-id="a8333-180">Redefine o qubit para um estado conhecido (`Zero`) antes de o devolver, o que permitirá que outros aloquem este qubit num estado conhecido.</span><span class="sxs-lookup"><span data-stu-id="a8333-180">It resets the qubit to a known state (`Zero`) before returning it allowing others to allocate this qubit in a known state.</span></span> <span data-ttu-id="a8333-181">Esta operação é exigida pela instrução `using`.</span><span class="sxs-lookup"><span data-stu-id="a8333-181">This is required by the `using` statement.</span></span>

#### <a name="about-variables-in-q"></a><span data-ttu-id="a8333-182">Sobre variáveis em Q\#</span><span class="sxs-lookup"><span data-stu-id="a8333-182">About variables in Q\#</span></span>

<span data-ttu-id="a8333-183">Por predefinição, as variáveis Q# são imutáveis; o seu valor não pode ser alterado após o seu limite.</span><span class="sxs-lookup"><span data-stu-id="a8333-183">By default, variables in Q# are immutable; their value may not be changed after they are bound.</span></span> <span data-ttu-id="a8333-184">A palavra-chave `let` é utilizada para indicar a vinculação de uma variável imutável.</span><span class="sxs-lookup"><span data-stu-id="a8333-184">The `let` keyword is used to indicate the binding of an immutable variable.</span></span> <span data-ttu-id="a8333-185">Os argumentos da operação são sempre imutáveis.</span><span class="sxs-lookup"><span data-stu-id="a8333-185">Operation arguments are always immutable.</span></span>

<span data-ttu-id="a8333-186">Se precisar de uma variável cujo valor pode ser alterado, como `numOnes`, poderá declarar a variável com a palavra-chave `mutable`.</span><span class="sxs-lookup"><span data-stu-id="a8333-186">If you need a variable whose value can change, such as `numOnes` in the example, you can declare the variable with the `mutable` keyword.</span></span> <span data-ttu-id="a8333-187">Um valor de variável mutável pode ser alterado com uma instrução `set`.</span><span class="sxs-lookup"><span data-stu-id="a8333-187">A mutable variable's value may be changed using a `set` statement.</span></span>

<span data-ttu-id="a8333-188">Em ambos os casos, o tipo de variável é inferido pelo compilador.</span><span class="sxs-lookup"><span data-stu-id="a8333-188">In both cases, the type of a variable is inferred by the compiler.</span></span> <span data-ttu-id="a8333-189">Q# não requer qualquer tipo de anotação para variáveis.</span><span class="sxs-lookup"><span data-stu-id="a8333-189">Q# doesn't require any type annotations for variables.</span></span>

#### <a name="about-using-statements-in-q"></a><span data-ttu-id="a8333-190">Sobre `using` declarações em Q\#</span><span class="sxs-lookup"><span data-stu-id="a8333-190">About `using` statements in Q\#</span></span>

<span data-ttu-id="a8333-191">A `using` declaração também é especial para Q# .</span><span class="sxs-lookup"><span data-stu-id="a8333-191">The `using` statement is also special to Q#.</span></span> <span data-ttu-id="a8333-192">É utilizada para alocar qubits para utilização num bloco de código.</span><span class="sxs-lookup"><span data-stu-id="a8333-192">It is used to allocate qubits for use in a block of code.</span></span> <span data-ttu-id="a8333-193">Em Q# , todos os qubits são dinamicamente alocados e libertados, em vez de serem recursos fixos que estão lá para toda a vida de um algoritmo complexo.</span><span class="sxs-lookup"><span data-stu-id="a8333-193">In Q#, all qubits are dynamically allocated and released, rather than being fixed resources that are there for the entire lifetime of a complex algorithm.</span></span> <span data-ttu-id="a8333-194">Uma instrução `using` aloca um conjunto de qubits no início e liberta esses qubits no final do bloco.</span><span class="sxs-lookup"><span data-stu-id="a8333-194">A `using` statement allocates a set of qubits at the start, and releases those qubits at the end of the block.</span></span>

## <a name="run-the-code-from-the-command-prompt"></a><span data-ttu-id="a8333-195">Executar o código a partir da solicitação de comando</span><span class="sxs-lookup"><span data-stu-id="a8333-195">Run the code from the command prompt</span></span>

<span data-ttu-id="a8333-196">Para executar o código, precisamos dizer ao compilador *que* pode ser executado quando fornenciamos o `dotnet run` comando.</span><span class="sxs-lookup"><span data-stu-id="a8333-196">In order to run the code we need to tell the compiler *which* callable to run when we provide the `dotnet run` command.</span></span> <span data-ttu-id="a8333-197">Isto é feito com uma simples alteração no Q# ficheiro, adicionando uma linha com `@EntryPoint()` a ligação diretamente anterior à chamada: a `TestBellState` operação neste caso.</span><span class="sxs-lookup"><span data-stu-id="a8333-197">This is done with a simple change in the Q# file by adding a line with `@EntryPoint()` directly preceding the callable: the `TestBellState` operation in this case.</span></span> <span data-ttu-id="a8333-198">O código completo deve ser:</span><span class="sxs-lookup"><span data-stu-id="a8333-198">The full code should be:</span></span>

```qsharp
namespace Bell {
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Intrinsic;

    operation SetQubitState(desired : Result, target : Qubit) : Unit {
        if (desired != M(target)) {
            X(target);
        }
    }

    @EntryPoint()
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                SetQubitState(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, qubit);
        }

    // Return number of times we saw a |0> and number of times we saw a |1>
    Message("Test results (# of 0s, # of 1s): ");
    return (count - numOnes, numOnes);
    }
}
```

<span data-ttu-id="a8333-199">Para executar o programa precisamos especificar `count` e argumentos a partir do pedido de `initial` comando.</span><span class="sxs-lookup"><span data-stu-id="a8333-199">To run the program we need to specify `count` and `initial` arguments from the command prompt.</span></span> <span data-ttu-id="a8333-200">Vamos escolher por exemplo `count = 1000` `initial = One` e.</span><span class="sxs-lookup"><span data-stu-id="a8333-200">Let's choose for example `count = 1000` and `initial = One`.</span></span> <span data-ttu-id="a8333-201">Introduza o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a8333-201">Enter the following command:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

<span data-ttu-id="a8333-202">E deve observar a seguinte saída:</span><span class="sxs-lookup"><span data-stu-id="a8333-202">And you should observe the following output:</span></span>

```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

<span data-ttu-id="a8333-203">Se tentar `initial = Zero` com o seu deve observar:</span><span class="sxs-lookup"><span data-stu-id="a8333-203">If you try with `initial = Zero` you should observe:</span></span>

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

## <a name="prepare-superposition"></a><span data-ttu-id="a8333-204">Preparar a sobreposição</span><span class="sxs-lookup"><span data-stu-id="a8333-204">Prepare superposition</span></span>

<span data-ttu-id="a8333-205">Agora vamos ver como Q# expressa formas de colocar qubits em superposição.</span><span class="sxs-lookup"><span data-stu-id="a8333-205">Now let’s look at how Q# expresses ways to put qubits in superposition.</span></span>  <span data-ttu-id="a8333-206">Lembre-se de que o estado de um qubit pode estar numa sobreposição de 0 e 1.</span><span class="sxs-lookup"><span data-stu-id="a8333-206">Recall that the state of a qubit can be in a superposition of 0 and 1.</span></span>  <span data-ttu-id="a8333-207">Vamos utilizar a operação `Hadamard` para esta ação.</span><span class="sxs-lookup"><span data-stu-id="a8333-207">We’ll use the `Hadamard` operation to accomplish this.</span></span> <span data-ttu-id="a8333-208">Se o qubit estiver num dos estados clássicos (em que uma medição devolve sempre `Zero` ou `One`), a operação `Hadamard` ou `H` colocará o qubit num estado em que uma medição do qubit devolverá `Zero` e `One` 50% do tempo.</span><span class="sxs-lookup"><span data-stu-id="a8333-208">If the qubit is in either of the classical states (where a measurement returns `Zero` always or `One` always), then the `Hadamard` or `H` operation will put the qubit in a state where a measurement of the qubit will return `Zero` 50% of the time and return `One` 50% of the time.</span></span>  <span data-ttu-id="a8333-209">Conceitualmente, o qubit pode ser pensado como estando entre `Zero` e `One`.</span><span class="sxs-lookup"><span data-stu-id="a8333-209">Conceputually, the qubit can be thought of as halfway between the `Zero` and `One`.</span></span>  <span data-ttu-id="a8333-210">Agora, quando simularmos a operação `TestBellState`, veremos que os resultados vão devolver aproximadamente um número igual de `Zero` e `One` após a medição.</span><span class="sxs-lookup"><span data-stu-id="a8333-210">Now, when we simulate the `TestBellState` operation, we will see the results will return roughly an equal number of `Zero` and `One` after measurement.</span></span>  

### <a name="x-flips-qubit-state"></a><span data-ttu-id="a8333-211">`X` flips qubit estado</span><span class="sxs-lookup"><span data-stu-id="a8333-211">`X` flips qubit state</span></span>

<span data-ttu-id="a8333-212">Primeiro vamos tentar virar o qubit (se o qubit estiver no `Zero` estado, vai virar para `One` e vice-versa).</span><span class="sxs-lookup"><span data-stu-id="a8333-212">First we'll just try to flip the qubit (if the qubit is in `Zero` state it will flip to `One` and vice versa).</span></span> <span data-ttu-id="a8333-213">Esta inversão pode ser feita ao realizar uma operação `X` antes de o medir em `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="a8333-213">This is accomplished by performing an `X` operation before we measure it in `TestBellState`:</span></span>

```qsharp
X(qubit);
let res = M(qubit);
```

<span data-ttu-id="a8333-214">Agora os resultados são invertidos:</span><span class="sxs-lookup"><span data-stu-id="a8333-214">Now the results are reversed:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

<span data-ttu-id="a8333-215">Agora vamos explorar as propriedades quânticas dos qubits.</span><span class="sxs-lookup"><span data-stu-id="a8333-215">Now let's explore the quantum properties of the qubits.</span></span>

### <a name="h-prepares-superposition"></a><span data-ttu-id="a8333-216">`H` prepara superposição</span><span class="sxs-lookup"><span data-stu-id="a8333-216">`H` prepares superposition</span></span>

<span data-ttu-id="a8333-217">Para tal, só precisamos de substituir a operação `X` na execução anterior por uma operação `H` ou Hadamard.</span><span class="sxs-lookup"><span data-stu-id="a8333-217">All we need to do is replace the `X` operation in the previous run with an `H` or Hadamard operation.</span></span> <span data-ttu-id="a8333-218">Em vez de inverter totalmente o qubit de 0 para 1, vamos invertê-lo apenas metade.</span><span class="sxs-lookup"><span data-stu-id="a8333-218">Instead of flipping the qubit all the way from 0 to 1, we will only flip it halfway.</span></span> <span data-ttu-id="a8333-219">As linhas substituídas em `TestBellState` agora são semelhantes ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="a8333-219">The replaced lines in `TestBellState` now look like:</span></span>

```qsharp
H(qubit);
let res = M(qubit);
```

<span data-ttu-id="a8333-220">Os resultados começam a ficar mais interessantes:</span><span class="sxs-lookup"><span data-stu-id="a8333-220">Now the results get more interesting:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(496, 504)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```

```output
Test results (# of 0s, # of 1s):
(506, 494)
```

<span data-ttu-id="a8333-221">Sempre que medimos, pedimos um valor clássico, mas o qubit encontra-se a meio entre 0 e 1 e assim obtemos (estatisticamente) 0 metade das vezes e 1 metade das vezes,</span><span class="sxs-lookup"><span data-stu-id="a8333-221">Every time we measure, we ask for a classical value, but the qubit is halfway between 0 and 1, so we get (statistically) 0 half the time and 1 half the time.</span></span>
<span data-ttu-id="a8333-222">o quer é conhecido como **sobreposição** e dá-nos a nossa primeira vista real de um estado quântico.</span><span class="sxs-lookup"><span data-stu-id="a8333-222">This is known as **superposition** and gives us our first real view into a quantum state.</span></span>

## <a name="prepare-entanglement"></a><span data-ttu-id="a8333-223">Preparar o entrelaçamento</span><span class="sxs-lookup"><span data-stu-id="a8333-223">Prepare entanglement</span></span>

<span data-ttu-id="a8333-224">Agora vamos ver como Q# expressa formas de envolver qubits.</span><span class="sxs-lookup"><span data-stu-id="a8333-224">Now let’s look at how Q# expresses ways to entangle qubits.</span></span>
<span data-ttu-id="a8333-225">Primeiro, definimos o primeiro qubit para o estado inicial e utilizamos a operação `H` para colocá-lo em sobreposição.</span><span class="sxs-lookup"><span data-stu-id="a8333-225">First, we set the first qubit to the initial state and then use the `H` operation to put it into superposition.</span></span>  <span data-ttu-id="a8333-226">Depois, antes de medirmos o primeiro qubit, usamos uma nova operação ( `CNOT` , que significa *Controlled-NOT*.</span><span class="sxs-lookup"><span data-stu-id="a8333-226">Then, before we measure the first qubit, we use a new operation (`CNOT`), which stands for *Controlled-NOT*.</span></span>  <span data-ttu-id="a8333-227">O resultado da execução desta operação em dois qubits é virar o segundo qubit se o primeiro qubit for `One` .</span><span class="sxs-lookup"><span data-stu-id="a8333-227">The result of running this operation on two qubits is to flip the second qubit if the first qubit is `One`.</span></span>  <span data-ttu-id="a8333-228">Agora, os dois qubits estão entrelaçados.</span><span class="sxs-lookup"><span data-stu-id="a8333-228">Now, the two qubits are entangled.</span></span>  <span data-ttu-id="a8333-229">As nossas estatísticas para o primeiro qubit não foram alteradas (uma probabilidade de 50-50 de um `Zero` ou de um `One` após a medição), mas quando medirmos o segundo qubit, este será __sempre__ igual ao que medimos para o primeiro qubit.</span><span class="sxs-lookup"><span data-stu-id="a8333-229">Our statistics for the first qubit haven't changed (50-50 chance of a `Zero` or a `One` after measurement), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit.</span></span> <span data-ttu-id="a8333-230">O nosso `CNOT` entrelaçou os dois qubits, de modo a que aquilo que acontecer a um deles, aconteça também ao outro.</span><span class="sxs-lookup"><span data-stu-id="a8333-230">Our `CNOT` has entangled the two qubits, so that whatever happens to one of them, happens to the other.</span></span> <span data-ttu-id="a8333-231">Se as medições fossem invertidas (a medição do segundo qubit antes do primeiro), aconteceria a mesma coisa.</span><span class="sxs-lookup"><span data-stu-id="a8333-231">If you reversed the measurements (did the second qubit before the first), the same thing would happen.</span></span> <span data-ttu-id="a8333-232">A primeira medida seria aleatória e a segunda estaria num passo bloqueado para a medição que tivesse sido detetada primeiro.</span><span class="sxs-lookup"><span data-stu-id="a8333-232">The first measurement would be random and the second would be in lock step with whatever was discovered for the first.</span></span>

<span data-ttu-id="a8333-233">A primeira coisa que temos de fazer é alocar dois qubits em vez de um `TestBellState` em:</span><span class="sxs-lookup"><span data-stu-id="a8333-233">The first thing we'll need to do is allocate two qubits instead of one in `TestBellState`:</span></span>

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

<span data-ttu-id="a8333-234">Este procedimento vai permitir adicionar uma nova operação (`CNOT`) antes de medir (`M`) em `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="a8333-234">This will allow us to add a new operation (`CNOT`) before we measure  (`M`) in `TestBellState`:</span></span>

```qsharp
SetQubitState(initial, q0);
SetQubitState(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

<span data-ttu-id="a8333-235">Adicionámos outra operação `SetQubitState` para inicializar o primeiro qubit para confirmar que está sempre no estado `Zero` quando começamos.</span><span class="sxs-lookup"><span data-stu-id="a8333-235">We've added another `SetQubitState` operation to initialize the first qubit to make sure that it's always in the `Zero` state when we start.</span></span>

<span data-ttu-id="a8333-236">Precisamos também de redefinir o segundo qubit antes de o libertar.</span><span class="sxs-lookup"><span data-stu-id="a8333-236">We also need to reset the second qubit before releasing it.</span></span>

```qsharp
SetQubitState(Zero, q0);
SetQubitState(Zero, q1);
```

<span data-ttu-id="a8333-237">A rotina completa é agora semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="a8333-237">The full routine now looks like this:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

<span data-ttu-id="a8333-238">Se a executarmos, vamos obter exatamente o mesmo resultado de 50-50 que obtivemos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a8333-238">If we run this, we'll get exactly the same 50-50 result we got before.</span></span> <span data-ttu-id="a8333-239">No entanto, o que nos interessa é a forma como o segundo qubit reage à primeira medição.</span><span class="sxs-lookup"><span data-stu-id="a8333-239">However, what we're interested in is how the second qubit reacts to the first being measured.</span></span> <span data-ttu-id="a8333-240">Vamos adicionar esta estatística com a nova versão da operação `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="a8333-240">We'll add this statistic with a new version of the `TestBellState` operation:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

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
            
            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return times we saw |0>, times we saw |1>, and times measurements agreed
        Message("Test results (# of 0s, # of 1s, # of agreements)");
        return (count-numOnes, numOnes, agree);
    }
```

<span data-ttu-id="a8333-241">O novo valor de retorno (`agree`) controla cada vez que a medição do primeiro qubit corresponde à medição do segundo qubit.</span><span class="sxs-lookup"><span data-stu-id="a8333-241">The new return value (`agree`) keeps track of every time the measurement from the first qubit matches the measurement of the second qubit.</span></span>

<span data-ttu-id="a8333-242">Executando o código que obtemos:</span><span class="sxs-lookup"><span data-stu-id="a8333-242">Running the code we obtain:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```
```output
(505, 495, 1000)
```
```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s, # of agreements)
(507, 493, 1000)
```

<span data-ttu-id="a8333-243">Conforme mencionado na descrição geral, as nossas estatísticas para o primeiro qubit não foram alteradas (uma probabilidade de 50-50 de um 0 ou de um 1), mas quando medirmos o segundo qubit, este será __sempre__ igual ao que medimos para o primeiro qubit, uma vez que estão entrelaçados!</span><span class="sxs-lookup"><span data-stu-id="a8333-243">As stated in the overview, our statistics for the first qubit haven't changed (50-50 chance of a 0 or a 1), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit, because they are entangled!</span></span>

## <a name="next-steps"></a><span data-ttu-id="a8333-244">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="a8333-244">Next steps</span></span>

<span data-ttu-id="a8333-245">A [pesquisa do](xref:microsoft.quantum.quickstarts.search) tutorial Grover mostra-lhe como construir e executar a pesquisa grover, um dos algoritmos de computação quântica mais populares e oferece um bom exemplo de um Q# programa que pode ser usado para resolver problemas reais com computação quântica.</span><span class="sxs-lookup"><span data-stu-id="a8333-245">The tutorial [Grover’s search](xref:microsoft.quantum.quickstarts.search) shows you how to build and run Grover search, one of the most popular quantum computing algorithms and offers a nice example of a Q# program that can be used to solve real problems with quantum computing.</span></span>  

<span data-ttu-id="a8333-246">[Começar com o Kit de Desenvolvimento Quântico](xref:microsoft.quantum.welcome) recomenda mais formas de aprender Q# e programação quântica.</span><span class="sxs-lookup"><span data-stu-id="a8333-246">[Get Started with the Quantum Development Kit](xref:microsoft.quantum.welcome) recommends more ways to learn Q# and quantum programming.</span></span>
