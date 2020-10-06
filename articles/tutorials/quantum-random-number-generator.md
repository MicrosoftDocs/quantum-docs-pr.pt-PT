---
title: Criar um Gerador de Números Aleatórios Quântico
description: Construir um Q# projeto que demonstre conceitos quânticos fundamentais como a superposição criando um gerador de números aleatórios quânticos.
author: bromeg
ms.author: megbrow
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
no-loc:
- Q#
- $$v
ms.openlocfilehash: cefe35a10dd89c14d2f1abc3080d52ab125236d1
ms.sourcegitcommit: d98190988ff03146d9ca2b0d325870cd717d729a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/06/2020
ms.locfileid: "91771277"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="5e772-103">Tutorial: Implementar um Gerador de Números Aleatórios Quântico em Q\#</span><span class="sxs-lookup"><span data-stu-id="5e772-103">Tutorial: Implement a Quantum Random Number Generator in Q\#</span></span>

<span data-ttu-id="5e772-104">Um exemplo simples de um algoritmo quântico escrito Q# é um gerador de números aleatórios quânticos.</span><span class="sxs-lookup"><span data-stu-id="5e772-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="5e772-105">Este algoritmo tira partido da natureza da mecânica quântica para produzir um número aleatório.</span><span class="sxs-lookup"><span data-stu-id="5e772-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5e772-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="5e772-106">Prerequisites</span></span>

- <span data-ttu-id="5e772-107">O Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="5e772-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- <span data-ttu-id="5e772-108">Crie um Q# projeto para uma [ Q# aplicação,](xref:microsoft.quantum.install.standalone)com um [programa de anfitrião Python,](xref:microsoft.quantum.install.python)ou um [programa de anfitrião C#](xref:microsoft.quantum.install.cs).</span><span class="sxs-lookup"><span data-stu-id="5e772-108">Create a Q# project for either a [Q# application](xref:microsoft.quantum.install.standalone), with a [Python host program](xref:microsoft.quantum.install.python), or a [C# host program](xref:microsoft.quantum.install.cs).</span></span>

## <a name="write-a-no-locq-operation"></a><span data-ttu-id="5e772-109">Escrever uma Q# operação</span><span class="sxs-lookup"><span data-stu-id="5e772-109">Write a Q# operation</span></span>

### <a name="no-locq-operation-code"></a><span data-ttu-id="5e772-110">Q# código de operação</span><span class="sxs-lookup"><span data-stu-id="5e772-110">Q# operation code</span></span>

1. <span data-ttu-id="5e772-111">Substitua o conteúdo do ficheiro Program.qs pelo seguinte código:</span><span class="sxs-lookup"><span data-stu-id="5e772-111">Replace the contents of the Program.qs file with the following code:</span></span>

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

<span data-ttu-id="5e772-112">Conforme mencionado no nosso artigo [Compreender a computação quântica](xref:microsoft.quantum.overview.understanding), um qubit é uma unidade de informações quânticas que pode estar em sobreposição.</span><span class="sxs-lookup"><span data-stu-id="5e772-112">As mentioned in our [Understanding quantum computing](xref:microsoft.quantum.overview.understanding) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="5e772-113">Quando medido, um qubit só pode ser 0 ou 1.</span><span class="sxs-lookup"><span data-stu-id="5e772-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="5e772-114">No entanto, antes da medição, o estado do qubit representa a probabilidade de ler um 0 ou um 1 com uma medição.</span><span class="sxs-lookup"><span data-stu-id="5e772-114">However, before measurement, the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="5e772-115">Este estado de probabilidade é conhecido como sobreposição.</span><span class="sxs-lookup"><span data-stu-id="5e772-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="5e772-116">Podemos utilizar esta probabilidade para gerar números aleatórios.</span><span class="sxs-lookup"><span data-stu-id="5e772-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="5e772-117">Na nossa Q# operação, introduzimos o `Qubit` tipo de dados, nativo Q# de.</span><span class="sxs-lookup"><span data-stu-id="5e772-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="5e772-118">Apenas podemos alocar um `Qubit` com uma instrução `using`.</span><span class="sxs-lookup"><span data-stu-id="5e772-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="5e772-119">Depois de alocados, os qubits estão sempre no estado `Zero`.</span><span class="sxs-lookup"><span data-stu-id="5e772-119">When it gets allocated, a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="5e772-120">Com a operação `H`, podemos colocar o `Qubit` em sobreposição.</span><span class="sxs-lookup"><span data-stu-id="5e772-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="5e772-121">Para medir um qubit e ler o seu valor, pode utilizar a operação intrínseca `M`.</span><span class="sxs-lookup"><span data-stu-id="5e772-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="5e772-122">Ao colocar o `Qubit` em sobreposição e ao medi-lo, o resultado será um valor diferente sempre que o código for invocado.</span><span class="sxs-lookup"><span data-stu-id="5e772-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span>

<span data-ttu-id="5e772-123">Quando um `Qubit` é desalocado, tem de ser definido explicitamente de volta para o estado `Zero`. Caso contrário, o simulador reportará um erro de runtime.</span><span class="sxs-lookup"><span data-stu-id="5e772-123">When a `Qubit` is deallocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="5e772-124">Uma forma fácil de conseguir isto é ao invocar `Reset`.</span><span class="sxs-lookup"><span data-stu-id="5e772-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="5e772-125">Visualizar o código com a Esfera de Bloch</span><span class="sxs-lookup"><span data-stu-id="5e772-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="5e772-126">Na Esfera de Bloch, o polo norte representa o valor clássico **0** e o polo sul representa o valor clássico **1**.</span><span class="sxs-lookup"><span data-stu-id="5e772-126">In the Bloch sphere, the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="5e772-127">Qualquer sobreposição pode ser representada por um ponto na esfera (representada por uma seta).</span><span class="sxs-lookup"><span data-stu-id="5e772-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="5e772-128">Quanto mais próximo estiver o fim da seta de um polo, maior a probabilidade de o qubit ser incluído no valor clássico atribuído a esse polo quando medido.</span><span class="sxs-lookup"><span data-stu-id="5e772-128">The closer the end of the arrow to a pole the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="5e772-129">Por exemplo, o estado do qubit representado pela seta vermelha abaixo tem uma probabilidade mais alta de originar o valor **0** se for medido.</span><span class="sxs-lookup"><span data-stu-id="5e772-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

<span data-ttu-id="5e772-130">Podemos utilizar esta representação para visualizar o que o código está a fazer:</span><span class="sxs-lookup"><span data-stu-id="5e772-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="5e772-131">Primeiro, começamos com um qubit inicializado no estado **0** e aplicamos `H` para criar uma sobreposição em que as probabilidades de **0** e **1** são iguais.</span><span class="sxs-lookup"><span data-stu-id="5e772-131">First we start with a qubit initialized in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">

* <span data-ttu-id="5e772-132">Em seguida, medimos o qubit e guardamos a saída:</span><span class="sxs-lookup"><span data-stu-id="5e772-132">Then we measure the qubit and save the output:</span></span>

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

<span data-ttu-id="5e772-133">Como o resultado da medição é completamente aleatório, obtivemos um bit aleatório.</span><span class="sxs-lookup"><span data-stu-id="5e772-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="5e772-134">Podemos chamar esta operação várias vezes para criar números inteiros.</span><span class="sxs-lookup"><span data-stu-id="5e772-134">We can call this operation several times to create integers.</span></span> <span data-ttu-id="5e772-135">Por exemplo, se chamarmos a operação três vezes para obter três bits aleatórios, poderemos criar números aleatórios de 3 bits (ou seja, um número aleatório entre 0 e 7).</span><span class="sxs-lookup"><span data-stu-id="5e772-135">For example, if we call the operation three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>


## <a name="creating-a-complete-random-number-generator"></a><span data-ttu-id="5e772-136">Criar um gerador de números aleatórios completo</span><span class="sxs-lookup"><span data-stu-id="5e772-136">Creating a complete random number generator</span></span>

<span data-ttu-id="5e772-137">Agora que temos uma Q# operação que gera bits aleatórios, podemos usá-lo para construir um gerador de números quânticos aleatórios.</span><span class="sxs-lookup"><span data-stu-id="5e772-137">Now that we have a Q# operation that generates random bits, we can use it to build a complete quantum random number generator.</span></span> <span data-ttu-id="5e772-138">Podemos usar uma Q# aplicação ou usar um programa de anfitrião.</span><span class="sxs-lookup"><span data-stu-id="5e772-138">We can use a Q# application or use a host program.</span></span>



### <a name="no-locq-applications-with-visual-studio-or-visual-studio-code"></a>[<span data-ttu-id="5e772-139">Q# aplicações com Visual Studio ou Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="5e772-139">Q# applications with Visual Studio or Visual Studio Code</span></span>](#tab/tabid-qsharp)

<span data-ttu-id="5e772-140">Para criar a Q# aplicação completa, adicione o seguinte ponto de entrada ao seu Q# programa:</span><span class="sxs-lookup"><span data-stu-id="5e772-140">To create the full Q# application, add the following entry point to your Q# program:</span></span> 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

<span data-ttu-id="5e772-141">O programa executará a operação ou função marcada com o `@EntryPoint()` atributo num simulador ou estimador de recursos, dependendo da configuração do projeto e das opções de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="5e772-141">The program will run the operation or function marked with the `@EntryPoint()` attribute on a simulator or resource estimator, depending on the project configuration and command-line options.</span></span>

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-34":::

<span data-ttu-id="5e772-142">No Visual Studio, basta premir Ctrl + F5 para executar o script.</span><span class="sxs-lookup"><span data-stu-id="5e772-142">In Visual Studio, simply press Ctrl + F5 to run the script.</span></span>

<span data-ttu-id="5e772-143">No VS Code, crie o ficheiro Program.qs pela primeira vez ao escrever o seguinte no terminal:</span><span class="sxs-lookup"><span data-stu-id="5e772-143">In VS Code, build the Program.qs the first time by typing the below in the terminal:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="5e772-144">Para as execuções subsequentes, não há necessidade de o criar novamente.</span><span class="sxs-lookup"><span data-stu-id="5e772-144">For subsequent runs, there is no need to build it again.</span></span> <span data-ttu-id="5e772-145">Para o executar, escreva o seguinte comando e prima Enter:</span><span class="sxs-lookup"><span data-stu-id="5e772-145">To run it, type the following command and press enter:</span></span>

```dotnetcli
dotnet run --no-build
```

### <a name="python-with-visual-studio-code-or-the-command-prompt"></a>[<span data-ttu-id="5e772-146">Python com Código de Estúdio Visual ou o pedido de comando</span><span class="sxs-lookup"><span data-stu-id="5e772-146">Python with Visual Studio Code or the command prompt</span></span>](#tab/tabid-python)

<span data-ttu-id="5e772-147">Para executar o seu novo Q# programa a partir de Python, guarde o seguinte código `host.py` como:</span><span class="sxs-lookup"><span data-stu-id="5e772-147">To run your new Q# program from Python, save the following code as `host.py`:</span></span>

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

<span data-ttu-id="5e772-148">Em seguida, pode executar o seu programa de anfitrião Python a partir da solicitação de comando:</span><span class="sxs-lookup"><span data-stu-id="5e772-148">You can then run your Python host program from the command prompt:</span></span>

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[<span data-ttu-id="5e772-149">C# com o Visual Studio Code ou o Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5e772-149">C# with Visual Studio Code or Visual Studio</span></span>](#tab/tabid-csharp)

<span data-ttu-id="5e772-150">Para executar o seu novo Q# programa a partir de C#, modifique para incluir o seguinte código `Driver.cs` C# :</span><span class="sxs-lookup"><span data-stu-id="5e772-150">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

<span data-ttu-id="5e772-151">Em seguida, pode executar o seu programa de anfitrião C# a partir da indicação de comando (no Estúdio Visual deve premir F5):</span><span class="sxs-lookup"><span data-stu-id="5e772-151">You can then run your C# host program from the command prompt (in Visual Studio you should press F5):</span></span>

```bash
$ dotnet run
The random number generated is 42
```

***
