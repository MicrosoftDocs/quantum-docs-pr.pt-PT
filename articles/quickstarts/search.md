---
title: Executar o algoritmo de pesquisa de Grover em Q# – Quantum Development Kit
description: Crie um projeto Q# que demonstre o algoritmo de Grover, um dos algoritmos quânticos canónicos.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: 75028a1dc29abe5fbea2e789d896563f3d6331c9
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443941"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a><span data-ttu-id="6f6eb-103">Início Rápido: Implementar o algoritmo de pesquisa de Grover em Q#</span><span class="sxs-lookup"><span data-stu-id="6f6eb-103">Quickstart: Implement Grover's search algorithm in Q#</span></span>

<span data-ttu-id="6f6eb-104">Neste guia de Início Rápido, pode aprender a compilar e executar a pesquisa de Grover para acelerar a pesquisa de dados não estruturados.</span><span class="sxs-lookup"><span data-stu-id="6f6eb-104">In this Quickstart, you can learn how to build and run Grover search to speed up the search of unstructured data.</span></span>  <span data-ttu-id="6f6eb-105">A pesquisa de Grover é um dos mais populares algoritmos de computação quântica e esta implementação de Q# relativamente pequena permite-lhe ter uma noção de algumas das vantagens da programação de soluções quânticas com uma linguagem de programação quântica Q# de alto nível para expressar algoritmos quânticos.</span><span class="sxs-lookup"><span data-stu-id="6f6eb-105">Grover's search is one of the most popular quantum computing algorithms, and this relatively small Q# implementation gives you a sense of some of the advantages of programming quantum solutions with a high-level Q# quantum programming language to express quantum algorithms.</span></span>  <span data-ttu-id="6f6eb-106">No final do guia, verá o resultado da simulação que demonstra como encontrar com êxito uma cadeia específica numa lista de entradas desordenadas numa fração do tempo que levaria a pesquisar toda a lista num computador clássico.</span><span class="sxs-lookup"><span data-stu-id="6f6eb-106">At the end of the guide, you will see the simulation output demonstrates successfully finding a specific string among a list of onordered entries in a fraction of the time it would take to search the whole list on a classical computer.</span></span>

<span data-ttu-id="6f6eb-107">O algoritmo de Grover procura itens específicos numa lista de dados não estruturados.</span><span class="sxs-lookup"><span data-stu-id="6f6eb-107">Grover's algorithm searches a list of unstructured data for specific items.</span></span> <span data-ttu-id="6f6eb-108">Por exemplo, pode responder à pergunta: Esta carta tirada de um baralho de cartas é um ás de copas?</span><span class="sxs-lookup"><span data-stu-id="6f6eb-108">For example, it can answer the question: Is this card drawn from a pack of cards an ace of hearts?</span></span> <span data-ttu-id="6f6eb-109">A identificação do item específico é chamada _entrada marcada_.</span><span class="sxs-lookup"><span data-stu-id="6f6eb-109">The labeling of the specific item is called _marked input_.</span></span>

<span data-ttu-id="6f6eb-110">Com o algoritmo de pesquisa de Grover, é garantido que um computador quântico executa esta pesquisa em menos passos do que o número de itens contidos na lista onde está a efetuar a pesquisa — algo que nenhum algoritmo clássico consegue fazer.</span><span class="sxs-lookup"><span data-stu-id="6f6eb-110">Using Grover's search algorithm, a quantum computer is guaranteed to run this search in fewer steps than the number of items in the list that you're searching — something no classical algorithm can do.</span></span> <span data-ttu-id="6f6eb-111">A maior velocidade no caso de um baralho de cartas é insignificante; no entanto, em listas que contenham milhões ou milhares de milhões de itens, torna-se significativa.</span><span class="sxs-lookup"><span data-stu-id="6f6eb-111">The increased speed in the case of a pack of cards is negligible; however, in lists containing millions or billions of items, it becomes significant.</span></span>

<span data-ttu-id="6f6eb-112">Pode criar o algoritmo de pesquisa de Grover com apenas algumas linhas de código.</span><span class="sxs-lookup"><span data-stu-id="6f6eb-112">You can build Grover's search algorithm with just a few lines of code.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6f6eb-113">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="6f6eb-113">Prerequisites</span></span>

- <span data-ttu-id="6f6eb-114">O Microsoft [Quantum Development Kit][install].</span><span class="sxs-lookup"><span data-stu-id="6f6eb-114">The Microsoft [Quantum Development Kit][install].</span></span>

## <a name="what-does-grovers-search-algorithm-do"></a><span data-ttu-id="6f6eb-115">O que é que algoritmo de pesquisa de Grover faz?</span><span class="sxs-lookup"><span data-stu-id="6f6eb-115">What does Grover's search algorithm do?</span></span>

<span data-ttu-id="6f6eb-116">O algoritmo de Grover pergunta se um item contido na lista é aquele de que estamos à procura.</span><span class="sxs-lookup"><span data-stu-id="6f6eb-116">Grover's algorithm asks whether an item in a list is the one we are searching for.</span></span> <span data-ttu-id="6f6eb-117">O algoritmo faz isto ao construir uma sobreposição quântica dos índices da lista com cada coeficiente ou amplitude de probabilidade, de forma a representar a probabilidade desse índice específico ser aquele de que está à procura.</span><span class="sxs-lookup"><span data-stu-id="6f6eb-117">It does this by constructing a quantum superposition of the indexes of the list with each coefficient, or probability amplitude, representing the probability of that specific index being the one you are looking for.</span></span>

<span data-ttu-id="6f6eb-118">No centro do algoritmo existem dois passos que aumentam incrementalmente o coeficiente do índice de que estamos à procura, até que a amplitude de probabilidade desse coeficiente se aproxime de um.</span><span class="sxs-lookup"><span data-stu-id="6f6eb-118">At the heart of the algorithm are two steps that incrementally boost the coefficient of the index that we are looking for, until the probability amplitude of that coefficient approaches one.</span></span>

<span data-ttu-id="6f6eb-119">O número de aumentos incrementais é inferior ao número de itens contidos na lista.</span><span class="sxs-lookup"><span data-stu-id="6f6eb-119">The number of incremental boosts is fewer than the number of items in the list.</span></span> <span data-ttu-id="6f6eb-120">É por isso que o algoritmo de pesquisa de Grover executa a pesquisa em menos passos do que qualquer algoritmo clássico.</span><span class="sxs-lookup"><span data-stu-id="6f6eb-120">This is why Grover's search algorithm performs the search in fewer steps than any classical algorithm.</span></span>

![Diagrama funcional do algoritmo de pesquisa de Grover](~/media/grover.png)

## <a name="write-the-code"></a><span data-ttu-id="6f6eb-122">Escrever o código</span><span class="sxs-lookup"><span data-stu-id="6f6eb-122">Write the code</span></span>

1. <span data-ttu-id="6f6eb-123">Através do Quantum Development Kit, [crie um novo projeto Q#](xref:microsoft.quantum.howto.createproject) chamado `Grover`, no ambiente de desenvolvimento de eleição.</span><span class="sxs-lookup"><span data-stu-id="6f6eb-123">Using the Quantum Development Kit, [create a new Q# project](xref:microsoft.quantum.howto.createproject) called `Grover`, in your development environment of choice.</span></span>

1. <span data-ttu-id="6f6eb-124">Adicione o seguinte código ao ficheiro `Operations.qs` no novo projeto:</span><span class="sxs-lookup"><span data-stu-id="6f6eb-124">Add the following code to the `Operations.qs` file in your new project:</span></span>

    [!code-qsharp[](~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs?highlight=5,27)]

1. <span data-ttu-id="6f6eb-125">Para definir a lista que estamos a pesquisar, crie um novo ficheiro `Reflections.qs` e cole no seguinte código:</span><span class="sxs-lookup"><span data-stu-id="6f6eb-125">To define the list that we're searching, create a new file `Reflections.qs`, and paste in the following code:</span></span>

    [!code-qsharp[](~/quantum/samples/algorithms/simple-grover/Reflections.qs)]

    <span data-ttu-id="6f6eb-126">A operação `ReflectAboutMarked` define a entrada marcada que está a pesquisar: a cadeia de zeros e uns alternados.</span><span class="sxs-lookup"><span data-stu-id="6f6eb-126">The `ReflectAboutMarked` operation defines the marked input that you are searching for: the string of alternating zeros and ones.</span></span> <span data-ttu-id="6f6eb-127">Esta amostra codifica a entrada marcada e pode ser expandida para pesquisar entradas diferentes ou generalizadas para qualquer entrada.</span><span class="sxs-lookup"><span data-stu-id="6f6eb-127">This sample hard-codes the marked input, and can be extended to search for different inputs or generalized for any input.</span></span>

1. <span data-ttu-id="6f6eb-128">Em seguida, execute o novo programa Q# para encontrar o item marcado pela operação `ReflectAboutMarked`.</span><span class="sxs-lookup"><span data-stu-id="6f6eb-128">Next, run your new Q# program to find the item marked by `ReflectAboutMarked`.</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-linetabtabid-python"></a>[<span data-ttu-id="6f6eb-129">Python com o Visual Studio Code ou a Linha de Comandos</span><span class="sxs-lookup"><span data-stu-id="6f6eb-129">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="6f6eb-130">Para executar o novo programa Q# no Python, guarde o seguinte código como `host.py`:</span><span class="sxs-lookup"><span data-stu-id="6f6eb-130">To run your new Q# program from Python, save the following code as `host.py`:</span></span>

    [!code-python[](~/quantum/samples/algorithms/simple-grover/host.py)]

    <span data-ttu-id="6f6eb-131">Em seguida, pode executar o programa anfitrião do Python na linha de comandos:</span><span class="sxs-lookup"><span data-stu-id="6f6eb-131">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    [0, 1, 0, 1, 0]
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-linetabtabid-csharp"></a>[<span data-ttu-id="6f6eb-132">C# com o Visual Studio Code ou a Linha de Comandos</span><span class="sxs-lookup"><span data-stu-id="6f6eb-132">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="6f6eb-133">Para executar o novo programa Q# em C#, modifique `Driver.cs` para incluir o seguinte código C#:</span><span class="sxs-lookup"><span data-stu-id="6f6eb-133">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>

    [!code-csharp[](~/quantum/samples/algorithms/simple-grover/Host.cs)]

    <span data-ttu-id="6f6eb-134">Em seguida, pode executar o programa anfitrião de C# na linha de comandos:</span><span class="sxs-lookup"><span data-stu-id="6f6eb-134">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```

    ### <a name="c-with-visual-studio-2019tabtabid-vs2019"></a>[<span data-ttu-id="6f6eb-135">C# com o Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="6f6eb-135">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="6f6eb-136">Para executar o novo programa Q# em C# no Visual Studio, modifique `Driver.cs` para incluir o seguinte código C#:</span><span class="sxs-lookup"><span data-stu-id="6f6eb-136">To run your new Q# program from C# in Visual Studio, modify `Driver.cs` to include the following C# code:</span></span>

    [!code-csharp[](~/quantum/samples/algorithms/simple-grover/Host.cs)]

    <span data-ttu-id="6f6eb-137">Em seguida, prima F5, o programa iniciará a execução e será apresentada uma nova janela com os seguintes resultados:</span><span class="sxs-lookup"><span data-stu-id="6f6eb-137">Then press F5, the program will start execution and a new windows will pop-up with the following results:</span></span> 

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```
    ***

    <span data-ttu-id="6f6eb-138">A operação `ReflectAboutMarked` é chamada apenas quatro vezes, mas o programa Q# conseguiu encontrar a entrada “01010” entre $2^{5} = 32$ entradas possíveis!</span><span class="sxs-lookup"><span data-stu-id="6f6eb-138">The `ReflectAboutMarked` operation is called only four times, but your Q# program was able to find the "01010" input amongst $2^{5} = 32$ possible inputs!</span></span>

## <a name="next-steps"></a><span data-ttu-id="6f6eb-139">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="6f6eb-139">Next steps</span></span>

<span data-ttu-id="6f6eb-140">Se gostou deste e início rápido, veja alguns dos recursos abaixo para saber mais sobre como pode utilizar a Q# para escrever as suas próprias aplicações quânticas:</span><span class="sxs-lookup"><span data-stu-id="6f6eb-140">If you enjoyed this quickstart, check out some of the resources below to learn more about how you can use Q# to write your own quantum applications:</span></span>

- [<span data-ttu-id="6f6eb-141">Voltar à Introdução com o guia do QDK</span><span class="sxs-lookup"><span data-stu-id="6f6eb-141">Back to the Getting Started with QDK guide</span></span>](xref:microsoft.quantum.welcome)
- <span data-ttu-id="6f6eb-142">Experimente uma [amostra](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search) do algoritmo de pesquisa de Grover mais geral</span><span class="sxs-lookup"><span data-stu-id="6f6eb-142">Try a more general Grover's search algorithm [sample](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search)</span></span>
- [<span data-ttu-id="6f6eb-143">Saiba mais sobre a pesquisa de Grover com os Quantum Katas</span><span class="sxs-lookup"><span data-stu-id="6f6eb-143">Learn more about Grover's search with the Quantum Katas</span></span>](xref:microsoft.quantum.overview.katas)
- <span data-ttu-id="6f6eb-144">Leia mais sobre [Amplificação de amplitude](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification), a técnica de computação quântica em que se baseia o algoritmo de pesquisa de Grover</span><span class="sxs-lookup"><span data-stu-id="6f6eb-144">Read more about [Amplitude amplification](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification), the quantum computing technique behind Grover's search algorithm</span></span>
- [<span data-ttu-id="6f6eb-145">Conceitos de computação quântica</span><span class="sxs-lookup"><span data-stu-id="6f6eb-145">Quantum computing concepts</span></span>](xref:microsoft.quantum.concepts.intro)
- [<span data-ttu-id="6f6eb-146">Amostras do Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="6f6eb-146">Quantum Development Kit Samples</span></span>](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
