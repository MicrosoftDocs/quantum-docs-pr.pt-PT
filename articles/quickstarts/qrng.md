---
title: Criar um Gerador de Números Aleatórios Quântico
description: Crie um projeto Q# que demonstre conceitos quânticos básicos, como a sobreposição, ao criar um gerador de números aleatórios quântico.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: b9c8592b1296a7de1b9ad5d0538ad1972ec25e31
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/16/2020
ms.locfileid: "77906989"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="46078-103">Início Rápido: Implementar um Gerador de Números Aleatórios Quântico em Q#</span><span class="sxs-lookup"><span data-stu-id="46078-103">Quickstart: Implement a Quantum Random Number Generator in Q#</span></span>
<span data-ttu-id="46078-104">Um exemplo simples de um algoritmo quântico escrito em Q# é um gerador de números aleatórios quântico.</span><span class="sxs-lookup"><span data-stu-id="46078-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="46078-105">Este algoritmo tira partido da natureza da mecânica quântica para produzir um número aleatório.</span><span class="sxs-lookup"><span data-stu-id="46078-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="46078-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="46078-106">Prerequisites</span></span>

- <span data-ttu-id="46078-107">O Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="46078-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- [<span data-ttu-id="46078-108">Criar um Projeto Q#</span><span class="sxs-lookup"><span data-stu-id="46078-108">Create a Q# Project</span></span>](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a><span data-ttu-id="46078-109">Escrever uma operação Q#</span><span class="sxs-lookup"><span data-stu-id="46078-109">Write a Q# operation</span></span>

### <a name="q-operation-code"></a><span data-ttu-id="46078-110">Código de operação Q#</span><span class="sxs-lookup"><span data-stu-id="46078-110">Q# operation code</span></span>

1. <span data-ttu-id="46078-111">Substitua o conteúdo do ficheiro Operation.qs pelo seguinte código:</span><span class="sxs-lookup"><span data-stu-id="46078-111">Replace the contents of the Operation.qs file with the following code:</span></span>

 :::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-14":::

<span data-ttu-id="46078-112">Conforme mencionado no nosso artigo [O que é a Computação Quântica?](xref:microsoft.quantum.overview.what), um qubit é uma unidade de informações quânticas que pode estar em sobreposição.</span><span class="sxs-lookup"><span data-stu-id="46078-112">As mentioned in our [What is Quantum Computing?](xref:microsoft.quantum.overview.what) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="46078-113">Quando medido, um qubit só pode ser 0 ou 1.</span><span class="sxs-lookup"><span data-stu-id="46078-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="46078-114">No entanto, durante a execução, o estado do qubit representa a probabilidade de ler um 0 ou um 1 com uma medição.</span><span class="sxs-lookup"><span data-stu-id="46078-114">However, during execution the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="46078-115">Este estado de probabilidade é conhecido como sobreposição.</span><span class="sxs-lookup"><span data-stu-id="46078-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="46078-116">Podemos utilizar esta probabilidade para gerar números aleatórios.</span><span class="sxs-lookup"><span data-stu-id="46078-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="46078-117">Na nossa operação de Q#, apresentamos o tipo de dados `Qubit`, nativo do Q#.</span><span class="sxs-lookup"><span data-stu-id="46078-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="46078-118">Apenas podemos alocar um `Qubit` com uma instrução `using`.</span><span class="sxs-lookup"><span data-stu-id="46078-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="46078-119">Depois de alocados, os qubits estão sempre no estado `Zero`.</span><span class="sxs-lookup"><span data-stu-id="46078-119">When it gets allocated, a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="46078-120">Com a operação `H`, podemos colocar o `Qubit` em sobreposição.</span><span class="sxs-lookup"><span data-stu-id="46078-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="46078-121">Para medir um qubit e ler o seu valor, pode utilizar a operação intrínseca `M`.</span><span class="sxs-lookup"><span data-stu-id="46078-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="46078-122">Ao colocar o `Qubit` em sobreposição e ao medi-lo, o resultado será um valor diferente sempre que o código for invocado.</span><span class="sxs-lookup"><span data-stu-id="46078-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span> 

<span data-ttu-id="46078-123">Quando um `Qubit` é desalocado, tem de ser definido explicitamente de volta para o estado `Zero`. Caso contrário, o simulador reportará um erro de runtime.</span><span class="sxs-lookup"><span data-stu-id="46078-123">When a `Qubit` is de-allocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="46078-124">Uma forma fácil de conseguir isto é ao invocar `Reset`.</span><span class="sxs-lookup"><span data-stu-id="46078-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="46078-125">Visualizar o código com a Esfera de Bloch</span><span class="sxs-lookup"><span data-stu-id="46078-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="46078-126">Na Esfera de Bloch, o polo norte representa o valor clássico **0** e o polo sul representa o valor clássico **1**.</span><span class="sxs-lookup"><span data-stu-id="46078-126">In the Bloch sphere, the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="46078-127">Qualquer sobreposição pode ser representada por um ponto na esfera (representada por uma seta).</span><span class="sxs-lookup"><span data-stu-id="46078-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="46078-128">Quanto mais próximo estiver o fim da seta de um polo, maior a probabilidade de o qubit ser incluído no valor clássico atribuído a esse polo quando medido.</span><span class="sxs-lookup"><span data-stu-id="46078-128">The closer the end of the arrow to a pole the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="46078-129">Por exemplo, o estado do qubit representado pela seta vermelha abaixo tem uma probabilidade mais alta de originar o valor **0** se for medido.</span><span class="sxs-lookup"><span data-stu-id="46078-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

<span data-ttu-id="46078-130">Podemos utilizar esta representação para visualizar o que o código está a fazer:</span><span class="sxs-lookup"><span data-stu-id="46078-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="46078-131">Primeiro, começamos com um qubit inicializado no estado **0** e aplicamos `H` para criar uma sobreposição em que as probabilidades de **0** e **1** são iguais.</span><span class="sxs-lookup"><span data-stu-id="46078-131">First we start with a qubit initialized in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">


* <span data-ttu-id="46078-132">Em seguida, medimos o qubit e guardamos a saída:</span><span class="sxs-lookup"><span data-stu-id="46078-132">Then we measure the qubit and save the output:</span></span>

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

<span data-ttu-id="46078-133">Como o resultado da medição é completamente aleatório, obtivemos um bit aleatório.</span><span class="sxs-lookup"><span data-stu-id="46078-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="46078-134">Podemos chamar esta operação várias vezes para criar números inteiros.</span><span class="sxs-lookup"><span data-stu-id="46078-134">We can call this operation several times to create integers.</span></span> <span data-ttu-id="46078-135">Por exemplo, se chamarmos a operação três vezes para obter três bits aleatórios, poderemos criar números aleatórios de 3 bits (ou seja, um número aleatório entre 0 e 7).</span><span class="sxs-lookup"><span data-stu-id="46078-135">For example, if we call the operation three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>

## <a name="creating-a-complete-random-number-generator-using-a-host-program"></a><span data-ttu-id="46078-136">Utilizar um programa anfitrião para criar um gerador de números aleatórios completo</span><span class="sxs-lookup"><span data-stu-id="46078-136">Creating a complete random number generator using a host program</span></span>

<span data-ttu-id="46078-137">Agora que temos uma operação Q# que gera bits aleatórios, podemos utilizá-la para compilar um gerador de números aleatórios quânticos completo com um programa anfitrião.</span><span class="sxs-lookup"><span data-stu-id="46078-137">Now that we have a Q# operation that generates random bits, we can use it to build a complete quantum random number generator with a host program.</span></span>

 ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="46078-138">Python com o Visual Studio Code ou a Linha de Comandos</span><span class="sxs-lookup"><span data-stu-id="46078-138">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)
 
 <span data-ttu-id="46078-139">Para executar o novo programa Q# no Python, guarde o seguinte código como `host.py`:</span><span class="sxs-lookup"><span data-stu-id="46078-139">To run your new Q# program from Python, save the following code as `host.py`:</span></span>
 
:::code language="python" source="~/quantum/samples/getting-started/qrng/host.py" range="11-30":::

 <span data-ttu-id="46078-140">Em seguida, pode executar o programa anfitrião do Python na linha de comandos:</span><span class="sxs-lookup"><span data-stu-id="46078-140">You can then run your Python host program from the command line:</span></span>
 ```bash
 $ python host.py
 Preparing Q# environment...
 ..The random number generated is 42
 ```
 ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="46078-141">C# com o Visual Studio Code ou a Linha de Comandos</span><span class="sxs-lookup"><span data-stu-id="46078-141">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)
 
 <span data-ttu-id="46078-142">Para executar o novo programa Q# em C#, modifique `Driver.cs` para incluir o seguinte código C#:</span><span class="sxs-lookup"><span data-stu-id="46078-142">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>
 
 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::
 
 <span data-ttu-id="46078-143">Em seguida, pode executar o programa anfitrião de C# na linha de comandos:</span><span class="sxs-lookup"><span data-stu-id="46078-143">You can then run your C# host program from the command line:</span></span>
 
 ```bash
 $ dotnet run
 The random number generated is 42
 ```

 ### <a name="c-with-visual-studio-2019"></a>[<span data-ttu-id="46078-144">C# com o Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="46078-144">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

 <span data-ttu-id="46078-145">Para executar o novo programa Q# em C# no Visual Studio, modifique `Driver.cs` para incluir o seguinte código C#:</span><span class="sxs-lookup"><span data-stu-id="46078-145">To run your new Q# program from C# in Visual Studio, modify `Driver.cs` to include the following C# code:</span></span>

 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::

 <span data-ttu-id="46078-146">Em seguida, prima F5. O programa inicia a execução e é apresentada uma janela nova com o número aleatório gerado:</span><span class="sxs-lookup"><span data-stu-id="46078-146">Then press F5, the program will start execution and a new window will pop up with the random number generated:</span></span> 

 ```bash
 $ dotnet run
 The random number generated is 42
 ```
 ***
