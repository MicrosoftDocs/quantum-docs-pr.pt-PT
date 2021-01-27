---
title: Algoritmo de pesquisa de Run Grover em Q# - Quantum Development Kit
description: Construa um Q# projeto que demonstre o algoritmo de Grover, um dos algoritmos quânticos canónicos.
author: cgranade
ms.author: chgranad
ms.date: 10/19/2019
ms.topic: tutorial
uid: microsoft.quantum.quickstarts.search
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5e0398338ff710decc0f3038c07c9b7d39514195
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856623"
---
# <a name="tutorial-implement-grovers-search-algorithm-in-q"></a><span data-ttu-id="d4ebe-103">Tutorial: implementar o algoritmo de pesquisa de Grover em Q\#</span><span class="sxs-lookup"><span data-stu-id="d4ebe-103">Tutorial: Implement Grover's search algorithm in Q\#</span></span>

<span data-ttu-id="d4ebe-104">Neste tutorial, pode aprender a compilar e executar a pesquisa de Grover para acelerar a pesquisa de dados não estruturados.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-104">In this tutorial, you can learn how to build and run Grover search to speed up the search of unstructured data.</span></span>  <span data-ttu-id="d4ebe-105">A pesquisa de Grover é um dos algoritmos de computação quântica mais populares, e esta implementação relativamente pequena Q# dá-lhe uma sensação de algumas das vantagens de programar soluções quânticas com uma linguagem de programação quântica de alto nível Q# para expressar algoritmos quânticos.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-105">Grover's search is one of the most popular quantum computing algorithms, and this relatively small Q# implementation gives you a sense of some of the advantages of programming quantum solutions with a high-level Q# quantum programming language to express quantum algorithms.</span></span>  <span data-ttu-id="d4ebe-106">No final do guia, verá o resultado da simulação que demonstra como encontrar com êxito uma cadeia específica numa lista de entradas desordenadas numa fração do tempo que levaria a pesquisar toda a lista num computador clássico.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-106">At the end of the guide, you will see the simulation output demonstrates successfully finding a specific string among a list of unordered entries in a fraction of the time it would take to search the whole list on a classical computer.</span></span>

<span data-ttu-id="d4ebe-107">O algoritmo de Grover procura itens específicos numa lista de dados não estruturados.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-107">Grover's algorithm searches a list of unstructured data for specific items.</span></span> <span data-ttu-id="d4ebe-108">Por exemplo, pode responder à pergunta: Esta carta tirada de um baralho de cartas é um ás de copas?</span><span class="sxs-lookup"><span data-stu-id="d4ebe-108">For example, it can answer the question: Is this card drawn from a pack of cards an ace of hearts?</span></span> <span data-ttu-id="d4ebe-109">A identificação do item específico é chamada _entrada marcada_.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-109">The labeling of the specific item is called _marked input_.</span></span>

<span data-ttu-id="d4ebe-110">Com o algoritmo de pesquisa de Grover, é garantido que um computador quântico executa esta pesquisa em menos passos do que o número de itens contidos na lista onde está a efetuar a pesquisa — algo que nenhum algoritmo clássico consegue fazer.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-110">Using Grover's search algorithm, a quantum computer is guaranteed to run this search in fewer steps than the number of items in the list that you're searching — something no classical algorithm can do.</span></span> <span data-ttu-id="d4ebe-111">A maior velocidade no caso de um baralho de cartas é insignificante; no entanto, em listas que contenham milhões ou milhares de milhões de itens, torna-se significativa.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-111">The increased speed in the case of a pack of cards is negligible; however, in lists containing millions or billions of items, it becomes significant.</span></span>

<span data-ttu-id="d4ebe-112">Pode criar o algoritmo de pesquisa de Grover com apenas algumas linhas de código.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-112">You can build Grover's search algorithm with just a few lines of code.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d4ebe-113">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="d4ebe-113">Prerequisites</span></span>

- <span data-ttu-id="d4ebe-114">O Microsoft [Quantum Development Kit][install].</span><span class="sxs-lookup"><span data-stu-id="d4ebe-114">The Microsoft [Quantum Development Kit][install].</span></span>

## <a name="what-does-grovers-search-algorithm-do"></a><span data-ttu-id="d4ebe-115">O que é que algoritmo de pesquisa de Grover faz?</span><span class="sxs-lookup"><span data-stu-id="d4ebe-115">What does Grover's search algorithm do?</span></span>

<span data-ttu-id="d4ebe-116">O algoritmo de Grover pergunta se um item contido na lista é aquele de que estamos à procura.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-116">Grover's algorithm asks whether an item in a list is the one we are searching for.</span></span> <span data-ttu-id="d4ebe-117">O algoritmo faz isto ao construir uma sobreposição quântica dos índices da lista com cada coeficiente ou amplitude de probabilidade, de forma a representar a probabilidade desse índice específico ser aquele de que está à procura.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-117">It does this by constructing a quantum superposition of the indexes of the list with each coefficient, or probability amplitude, representing the probability of that specific index being the one you are looking for.</span></span>

<span data-ttu-id="d4ebe-118">No centro do algoritmo existem dois passos que aumentam incrementalmente o coeficiente do índice de que estamos à procura, até que a amplitude de probabilidade desse coeficiente se aproxime de um.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-118">At the heart of the algorithm are two steps that incrementally boost the coefficient of the index that we are looking for, until the probability amplitude of that coefficient approaches one.</span></span>

<span data-ttu-id="d4ebe-119">O número de aumentos incrementais é inferior ao número de itens contidos na lista.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-119">The number of incremental boosts is fewer than the number of items in the list.</span></span> <span data-ttu-id="d4ebe-120">É por isso que o algoritmo de pesquisa de Grover executa a pesquisa em menos passos do que qualquer algoritmo clássico.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-120">This is why Grover's search algorithm performs the search in fewer steps than any classical algorithm.</span></span>

![Diagrama funcional do algoritmo de pesquisa de Grover](~/media/grover.png)

## <a name="write-the-code"></a><span data-ttu-id="d4ebe-122">Escrever o código</span><span class="sxs-lookup"><span data-stu-id="d4ebe-122">Write the code</span></span>

1. <span data-ttu-id="d4ebe-123">Utilizando o Kit de Desenvolvimento Quântico, [crie um novo projeto para a Q# aplicação.](xref:microsoft.quantum.install.standalone)</span><span class="sxs-lookup"><span data-stu-id="d4ebe-123">Using the Quantum Development Kit, [create a new Q# project for the application](xref:microsoft.quantum.install.standalone).</span></span> <span data-ttu-id="d4ebe-124">Dê um título ao projeto `Grover`.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-124">Title the project `Grover`.</span></span>

1. <span data-ttu-id="d4ebe-125">Adicione o seguinte código ao ficheiro `Program.qs` no novo projeto:</span><span class="sxs-lookup"><span data-stu-id="d4ebe-125">Add the following code to the `Program.qs` file in your new project:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-41":::

1. <span data-ttu-id="d4ebe-126">Para definir a lista que estamos a pesquisar, crie um novo ficheiro `Reflections.qs` e cole no seguinte código:</span><span class="sxs-lookup"><span data-stu-id="d4ebe-126">To define the list that we're searching, create a new file `Reflections.qs`, and paste in the following code:</span></span>

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    <span data-ttu-id="d4ebe-127">A operação `ReflectAboutMarked` define a entrada marcada que está a pesquisar: a cadeia de zeros e uns alternados.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-127">The `ReflectAboutMarked` operation defines the marked input that you are searching for: the string of alternating zeros and ones.</span></span> <span data-ttu-id="d4ebe-128">Esta amostra codifica a entrada marcada e pode ser expandida para pesquisar entradas diferentes ou generalizadas para qualquer entrada.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-128">This sample hard-codes the marked input, and can be extended to search for different inputs or generalized for any input.</span></span>

1. <span data-ttu-id="d4ebe-129">Em seguida, execute o seu novo Q# programa para encontrar o item marcado por `ReflectAboutMarked` .</span><span class="sxs-lookup"><span data-stu-id="d4ebe-129">Next, run your new Q# program to find the item marked by `ReflectAboutMarked`.</span></span>

### <a name="no-locq-applications-with-visual-studio-or-visual-studio-code"></a><span data-ttu-id="d4ebe-130">Q# aplicações com Visual Studio ou Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="d4ebe-130">Q# applications with Visual Studio or Visual Studio Code</span></span>

<span data-ttu-id="d4ebe-131">O programa executará a operação ou função marcada com o `@EntryPoint()` atributo num simulador ou estimador de recursos, dependendo da configuração do projeto e das opções de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-131">The program will run the operation or function marked with the `@EntryPoint()` attribute on a simulator or resource estimator, depending on the project configuration and command-line options.</span></span>

<span data-ttu-id="d4ebe-132">No Visual Studio, basta premir Ctrl + F5 para executar o script.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-132">In Visual Studio, simply press Ctrl + F5 to run the script.</span></span>

<span data-ttu-id="d4ebe-133">No VS Code, crie o ficheiro `Program.qs` pela primeira vez ao escrever o seguinte no terminal:</span><span class="sxs-lookup"><span data-stu-id="d4ebe-133">In VS Code, build the `Program.qs` the first time by typing the below in the terminal:</span></span>

```Command line
dotnet build
```

<span data-ttu-id="d4ebe-134">Para as execuções subsequentes, não há necessidade de o criar novamente.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-134">For subsequent runs, there is no need to build it again.</span></span> <span data-ttu-id="d4ebe-135">Para o executar, escreva o seguinte comando e prima Enter:</span><span class="sxs-lookup"><span data-stu-id="d4ebe-135">To run it, type the following command and press enter:</span></span>

```Command line
dotnet run --no-build
```

<span data-ttu-id="d4ebe-136">Deverá ser apresentada a seguinte mensagem no terminal:</span><span class="sxs-lookup"><span data-stu-id="d4ebe-136">You should see the following message displayed in the terminal:</span></span>

```
operations.qs:
This operation applies Grover's algorithm to search all possible inputs to an operation to find a particular marked state.
Usage:
operations.qs [options] [command]

--n-qubits <n-qubits> (REQUIRED)
-s, --simulator <simulator>         The name of the simulator to use.
--version                           Show version information
-?, -h, --help                      Show help and usage information
Commands:
```

<span data-ttu-id="d4ebe-137">Isto porque não especificou o número de qubits que queria utilizar, pelo que o terminal mostra-lhe os comandos disponíveis para o programa executável.</span><span class="sxs-lookup"><span data-stu-id="d4ebe-137">This is because you didn't specify the number of qubits you wanted to use, so the terminal shows you the commands available for the executable program.</span></span> <span data-ttu-id="d4ebe-138">Se quisermos usar 5 qubits, devemos escrever:</span><span class="sxs-lookup"><span data-stu-id="d4ebe-138">If we want to use 5 qubits, we should type:</span></span>

```Command line
dotnet run --n-qubits 5
```

<span data-ttu-id="d4ebe-139">Deverá ver o resultado seguinte quando premir Enter:</span><span class="sxs-lookup"><span data-stu-id="d4ebe-139">Pressing enter you should see the following output:</span></span>

```
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
[Zero,One,Zero,One,Zero]
```

## <a name="next-steps"></a><span data-ttu-id="d4ebe-140">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="d4ebe-140">Next steps</span></span>

<span data-ttu-id="d4ebe-141">Se gostou deste tutorial, confira alguns dos recursos abaixo para saber mais sobre como pode usar Q# para escrever as suas próprias aplicações quânticas:</span><span class="sxs-lookup"><span data-stu-id="d4ebe-141">If you enjoyed this tutorial, check out some of the resources below to learn more about how you can use Q# to write your own quantum applications:</span></span>

- [<span data-ttu-id="d4ebe-142">Voltar à Introdução com o guia do QDK</span><span class="sxs-lookup"><span data-stu-id="d4ebe-142">Back to the Getting Started with QDK guide</span></span>](xref:microsoft.quantum.welcome)
- <span data-ttu-id="d4ebe-143">Experimente uma [amostra](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/database-search) do algoritmo de pesquisa de Grover mais geral</span><span class="sxs-lookup"><span data-stu-id="d4ebe-143">Try a more general Grover's search algorithm [sample](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/database-search)</span></span>
- [<span data-ttu-id="d4ebe-144">Saiba mais sobre a pesquisa de Grover com os Quantum Katas</span><span class="sxs-lookup"><span data-stu-id="d4ebe-144">Learn more about Grover's search with the Quantum Katas</span></span>](xref:microsoft.quantum.overview.katas)
- <span data-ttu-id="d4ebe-145">Leia mais sobre [Amplificação de amplitude][amplitude-amplification], a técnica de computação quântica em que se baseia o algoritmo de pesquisa de Grover</span><span class="sxs-lookup"><span data-stu-id="d4ebe-145">Read more about [Amplitude amplification][amplitude-amplification], the quantum computing technique behind Grover's search algorithm</span></span>
- [<span data-ttu-id="d4ebe-146">Conceitos de computação quântica</span><span class="sxs-lookup"><span data-stu-id="d4ebe-146">Quantum computing concepts</span></span>](xref:microsoft.quantum.concepts.intro)
- [<span data-ttu-id="d4ebe-147">Amostras do Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="d4ebe-147">Quantum Development Kit Samples</span></span>](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
[amplitude-amplification]: xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification
