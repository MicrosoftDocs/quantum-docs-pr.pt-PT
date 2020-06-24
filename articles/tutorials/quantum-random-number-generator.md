---
title: Criar um Gerador de Números Aleatórios Quântico
description: Crie um projeto Q# que demonstre conceitos quânticos básicos, como a sobreposição, ao criar um gerador de números aleatórios quântico.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: 18e8975e513a87c0a67a6dbb5586cc7dab5a93fb
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275284"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="66d24-103">Tutorial: Implementar um Gerador de Números Aleatórios Quântico em Q\#</span><span class="sxs-lookup"><span data-stu-id="66d24-103">Tutorial: Implement a Quantum Random Number Generator in Q\#</span></span>

<span data-ttu-id="66d24-104">Um exemplo simples de um algoritmo quântico escrito em Q# é um gerador de números aleatórios quântico.</span><span class="sxs-lookup"><span data-stu-id="66d24-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="66d24-105">Este algoritmo tira partido da natureza da mecânica quântica para produzir um número aleatório.</span><span class="sxs-lookup"><span data-stu-id="66d24-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="66d24-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="66d24-106">Prerequisites</span></span>

- <span data-ttu-id="66d24-107">O Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="66d24-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- <span data-ttu-id="66d24-108">Crie um projeto em Q# para poder [utilizar o Q# a partir da linha de comandos](xref:microsoft.quantum.install.standalone) ou com um [programa anfitrião em Python](xref:microsoft.quantum.install.python) ou com um [programa anfitrião em C#](xref:microsoft.quantum.install.cs).</span><span class="sxs-lookup"><span data-stu-id="66d24-108">Create a Q# project for either [using Q# from the command line](xref:microsoft.quantum.install.standalone), or with a [Python host program](xref:microsoft.quantum.install.python) or [C# host program](xref:microsoft.quantum.install.cs).</span></span>

## <a name="write-a-q-operation"></a><span data-ttu-id="66d24-109">Escrever uma operação Q#</span><span class="sxs-lookup"><span data-stu-id="66d24-109">Write a Q# operation</span></span>

### <a name="q-operation-code"></a><span data-ttu-id="66d24-110">Código de operação Q#</span><span class="sxs-lookup"><span data-stu-id="66d24-110">Q# operation code</span></span>

1. <span data-ttu-id="66d24-111">Substitua o conteúdo do ficheiro Program.qs pelo seguinte código:</span><span class="sxs-lookup"><span data-stu-id="66d24-111">Replace the contents of the Program.qs file with the following code:</span></span>

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

<span data-ttu-id="66d24-112">Conforme mencionado no nosso artigo [Compreender a computação quântica](xref:microsoft.quantum.overview.understanding), um qubit é uma unidade de informações quânticas que pode estar em sobreposição.</span><span class="sxs-lookup"><span data-stu-id="66d24-112">As mentioned in our [Understanding quantum computing](xref:microsoft.quantum.overview.understanding) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="66d24-113">Quando medido, um qubit só pode ser 0 ou 1.</span><span class="sxs-lookup"><span data-stu-id="66d24-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="66d24-114">No entanto, durante a execução, o estado do qubit representa a probabilidade de ler um 0 ou um 1 com uma medição.</span><span class="sxs-lookup"><span data-stu-id="66d24-114">However, during execution the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="66d24-115">Este estado de probabilidade é conhecido como sobreposição.</span><span class="sxs-lookup"><span data-stu-id="66d24-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="66d24-116">Podemos utilizar esta probabilidade para gerar números aleatórios.</span><span class="sxs-lookup"><span data-stu-id="66d24-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="66d24-117">Na nossa operação de Q#, apresentamos o tipo de dados `Qubit`, nativo do Q#.</span><span class="sxs-lookup"><span data-stu-id="66d24-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="66d24-118">Apenas podemos alocar um `Qubit` com uma instrução `using`.</span><span class="sxs-lookup"><span data-stu-id="66d24-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="66d24-119">Depois de alocados, os qubits estão sempre no estado `Zero`.</span><span class="sxs-lookup"><span data-stu-id="66d24-119">When it gets allocated, a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="66d24-120">Com a operação `H`, podemos colocar o `Qubit` em sobreposição.</span><span class="sxs-lookup"><span data-stu-id="66d24-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="66d24-121">Para medir um qubit e ler o seu valor, pode utilizar a operação intrínseca `M`.</span><span class="sxs-lookup"><span data-stu-id="66d24-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="66d24-122">Ao colocar o `Qubit` em sobreposição e ao medi-lo, o resultado será um valor diferente sempre que o código for invocado.</span><span class="sxs-lookup"><span data-stu-id="66d24-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span>

<span data-ttu-id="66d24-123">Quando um `Qubit` negócio é estabelecido deve ser explicitamente retorcido para o `Zero` estado, caso contrário o simulador reportará um erro de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="66d24-123">When a `Qubit` is deallocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="66d24-124">Uma forma fácil de conseguir isto é ao invocar `Reset`.</span><span class="sxs-lookup"><span data-stu-id="66d24-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="66d24-125">Visualizar o código com a Esfera de Bloch</span><span class="sxs-lookup"><span data-stu-id="66d24-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="66d24-126">Na Esfera de Bloch, o polo norte representa o valor clássico **0** e o polo sul representa o valor clássico **1**.</span><span class="sxs-lookup"><span data-stu-id="66d24-126">In the Bloch sphere, the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="66d24-127">Qualquer sobreposição pode ser representada por um ponto na esfera (representada por uma seta).</span><span class="sxs-lookup"><span data-stu-id="66d24-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="66d24-128">Quanto mais próximo estiver o fim da seta de um polo, maior a probabilidade de o qubit ser incluído no valor clássico atribuído a esse polo quando medido.</span><span class="sxs-lookup"><span data-stu-id="66d24-128">The closer the end of the arrow to a pole the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="66d24-129">Por exemplo, o estado do qubit representado pela seta vermelha abaixo tem uma probabilidade mais alta de originar o valor **0** se for medido.</span><span class="sxs-lookup"><span data-stu-id="66d24-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

<span data-ttu-id="66d24-130">Podemos utilizar esta representação para visualizar o que o código está a fazer:</span><span class="sxs-lookup"><span data-stu-id="66d24-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="66d24-131">Primeiro, começamos com um qubit inicializado no estado **0** e aplicamos `H` para criar uma sobreposição em que as probabilidades de **0** e **1** são iguais.</span><span class="sxs-lookup"><span data-stu-id="66d24-131">First we start with a qubit initialized in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">

* <span data-ttu-id="66d24-132">Em seguida, medimos o qubit e guardamos a saída:</span><span class="sxs-lookup"><span data-stu-id="66d24-132">Then we measure the qubit and save the output:</span></span>

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

<span data-ttu-id="66d24-133">Como o resultado da medição é completamente aleatório, obtivemos um bit aleatório.</span><span class="sxs-lookup"><span data-stu-id="66d24-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="66d24-134">Podemos chamar esta operação várias vezes para criar números inteiros.</span><span class="sxs-lookup"><span data-stu-id="66d24-134">We can call this operation several times to create integers.</span></span> <span data-ttu-id="66d24-135">Por exemplo, se chamarmos a operação três vezes para obter três bits aleatórios, poderemos criar números aleatórios de 3 bits (ou seja, um número aleatório entre 0 e 7).</span><span class="sxs-lookup"><span data-stu-id="66d24-135">For example, if we call the operation three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>


## <a name="creating-a-complete-random-number-generator"></a><span data-ttu-id="66d24-136">Criar um gerador de números aleatórios completo</span><span class="sxs-lookup"><span data-stu-id="66d24-136">Creating a complete random number generator</span></span>

<span data-ttu-id="66d24-137">Agora que temos uma operação Q# que gera bits aleatórios, podemos utilizá-la para compilar um gerador de números aleatórios quânticos completo.</span><span class="sxs-lookup"><span data-stu-id="66d24-137">Now that we have a Q# operation that generates random bits, we can use it to build a complete quantum random number generator.</span></span> <span data-ttu-id="66d24-138">Podemos utilizar as aplicações de linha de comandos Q# ou um programa anfitrião.</span><span class="sxs-lookup"><span data-stu-id="66d24-138">We can use the Q# command line applications or use a host program.</span></span>



### <a name="q-command-line-applications-with-visual-studio-or-visual-studio-code"></a>[<span data-ttu-id="66d24-139">Aplicações de linha de comandos Q# com o Visual Studio ou o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="66d24-139">Q# command line applications with Visual Studio or Visual Studio Code</span></span>](#tab/tabid-qsharp)

<span data-ttu-id="66d24-140">Para criar a aplicação completa de linha de comandos Q#, adicione o seguinte ponto de entrada ao programa Q#:</span><span class="sxs-lookup"><span data-stu-id="66d24-140">To create the full Q# command line application, add the following entry point to your Q# program:</span></span> 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

<span data-ttu-id="66d24-141">O executável executará a operação ou função marcada com o atributo `@EntryPoint()` num simulador ou estimador de recursos, consoante a configuração do projeto e as opções da linha de comandos.</span><span class="sxs-lookup"><span data-stu-id="66d24-141">The executable will run the operation or function marked with the `@EntryPoint()` attribute on a simulator or resource estimator, depending on the project configuration and command-line options.</span></span>

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-34":::

<span data-ttu-id="66d24-142">No Visual Studio, basta premir Ctrl + F5 para executar o script.</span><span class="sxs-lookup"><span data-stu-id="66d24-142">In Visual Studio, simply press Ctrl + F5 to execute the script.</span></span>

<span data-ttu-id="66d24-143">No VS Code, crie o ficheiro Program.qs pela primeira vez ao escrever o seguinte no terminal:</span><span class="sxs-lookup"><span data-stu-id="66d24-143">In VS Code, build the Program.qs the first time by typing the below in the terminal:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="66d24-144">Para as execuções subsequentes, não há necessidade de o criar novamente.</span><span class="sxs-lookup"><span data-stu-id="66d24-144">For subsequent runs, there is no need to build it again.</span></span> <span data-ttu-id="66d24-145">Para o executar, escreva o seguinte comando e prima Enter:</span><span class="sxs-lookup"><span data-stu-id="66d24-145">To run it, type the following command and press enter:</span></span>

```dotnetcli
dotnet run --no-build
```

### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="66d24-146">Python com o Visual Studio Code ou a Linha de Comandos</span><span class="sxs-lookup"><span data-stu-id="66d24-146">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

<span data-ttu-id="66d24-147">Para executar o novo programa Q# no Python, guarde o seguinte código como `host.py`:</span><span class="sxs-lookup"><span data-stu-id="66d24-147">To run your new Q# program from Python, save the following code as `host.py`:</span></span>

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

<span data-ttu-id="66d24-148">Em seguida, pode executar o programa anfitrião do Python na linha de comandos:</span><span class="sxs-lookup"><span data-stu-id="66d24-148">You can then run your Python host program from the command line:</span></span>

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[<span data-ttu-id="66d24-149">C# com o Visual Studio Code ou o Visual Studio</span><span class="sxs-lookup"><span data-stu-id="66d24-149">C# with Visual Studio Code or Visual Studio</span></span>](#tab/tabid-csharp)

<span data-ttu-id="66d24-150">Para executar o novo programa Q# em C#, modifique `Driver.cs` para incluir o seguinte código C#:</span><span class="sxs-lookup"><span data-stu-id="66d24-150">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

<span data-ttu-id="66d24-151">Em seguida, pode executar o programa anfitrião de C# na linha de comandos (no Visual Studio, deve premir F5):</span><span class="sxs-lookup"><span data-stu-id="66d24-151">You can then run your C# host program from the command line (in Visual Studio you should press F5):</span></span>

```bash
$ dotnet run
The random number generated is 42
```

***
