---
title: Programar com o Q# Jupyter Notebook
description: Saiba como criar uma aplicação Q# com o Jupyter Notebook.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
no-loc:
- Q#
- $$v
ms.openlocfilehash: b34d89ab33a4644c1dd4342949685f9bf84babd8
ms.sourcegitcommit: d98190988ff03146d9ca2b0d325870cd717d729a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/06/2020
ms.locfileid: "91771400"
---
# <a name="develop-with-no-locq-jupyter-notebooks"></a><span data-ttu-id="8d06d-103">Programar com o Q# Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="8d06d-103">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="8d06d-104">Instale o QDK para desenvolver operações Q# no Q# Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="8d06d-104">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="8d06d-105">O Jupyter Notebook permitem executar código no local juntamente com instruções, notas e outros conteúdos.</span><span class="sxs-lookup"><span data-stu-id="8d06d-105">Jupyter Notebooks allow running code in-place alongside instructions, notes, and other content.</span></span> <span data-ttu-id="8d06d-106">Este ambiente é ideal para escrever código Q# com explicações incorporadas ou tutoriais interativos de computação quântica.</span><span class="sxs-lookup"><span data-stu-id="8d06d-106">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="8d06d-107">Eis o que tem de fazer para começar a criar os seus próprios blocos de notas em Q#.</span><span class="sxs-lookup"><span data-stu-id="8d06d-107">Here's what you need to do to start creating your own Q# notebooks.</span></span>

## <a name="install-the-ino-locq-jupyter-kernel"></a><span data-ttu-id="8d06d-108">Instale o kernel do IQ# Jupyter</span><span class="sxs-lookup"><span data-stu-id="8d06d-108">Install the IQ# Jupyter kernel</span></span>

<span data-ttu-id="8d06d-109">IQ# (pronunciado i-q-sharp) é uma extensão principalmente utilizada pelo Jupyter e Python para o SDK de .NET Core que fornece a funcionalidade principal que permite compilar e simular operações Q#.</span><span class="sxs-lookup"><span data-stu-id="8d06d-109">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="8d06d-110">Instale com o conda (recomendado)</span><span class="sxs-lookup"><span data-stu-id="8d06d-110">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="8d06d-111">Instale o [Miniconda](https://docs.conda.io/en/latest/miniconda.html) ou o [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span><span class="sxs-lookup"><span data-stu-id="8d06d-111">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span> <span data-ttu-id="8d06d-112">**Nota:** Instalação de 64 bits obrigatória.</span><span class="sxs-lookup"><span data-stu-id="8d06d-112">**Note:** 64-bit installation required.</span></span>

1. <span data-ttu-id="8d06d-113">Abra um Pedido do Anaconda.</span><span class="sxs-lookup"><span data-stu-id="8d06d-113">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="8d06d-114">Em alternativa, se preferir utilizar o PowerShell ou o pwsh:, abra uma shell, execute `conda init powershell`, feche e reabra a shell.</span><span class="sxs-lookup"><span data-stu-id="8d06d-114">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="8d06d-115">Crie e ative um novo ambiente conda com o nome `qsharp-env` com os pacotes necessários (incluindo Jupyter Notebook e IQ#) ao executar os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="8d06d-115">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="8d06d-116">Execute `python -c "import qsharp"` a partir do mesmo terminal para verificar a instalação e povoar a cache de pacotes local com todos os componentes QDK necessários.</span><span class="sxs-lookup"><span data-stu-id="8d06d-116">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-advanced"></a>[<span data-ttu-id="8d06d-117">Instale com o .NET CLI (avançado)</span><span class="sxs-lookup"><span data-stu-id="8d06d-117">Install using .NET CLI (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="8d06d-118">Pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="8d06d-118">Prerequisites:</span></span>

    - <span data-ttu-id="8d06d-119">[Python](https://www.python.org/downloads/) 3.6 ou posterior</span><span class="sxs-lookup"><span data-stu-id="8d06d-119">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="8d06d-120">Bloco de Notas do Jupyter</span><span class="sxs-lookup"><span data-stu-id="8d06d-120">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="8d06d-121">SDK de .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="8d06d-121">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="8d06d-122">Instale o pacote `Microsoft.Quantum.IQSharp`.</span><span class="sxs-lookup"><span data-stu-id="8d06d-122">Install the `Microsoft.Quantum.IQSharp` package.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

> [!NOTE]
> <span data-ttu-id="8d06d-123">Se receber um erro durante o passo `dotnet iqsharp install`, abra uma janela de terminal nova e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="8d06d-123">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
> <span data-ttu-id="8d06d-124">Se continuar a não funcionar, tente localizar a ferramenta `dotnet-iqsharp` instalada (no Windows, `dotnet-iqsharp.exe`) e executar:</span><span class="sxs-lookup"><span data-stu-id="8d06d-124">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
> ```
> /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
> ```
> <span data-ttu-id="8d06d-125">em que `/path/to/dotnet-iqsharp` deve ser substituído pelo caminho absoluto para a ferramenta `dotnet-iqsharp` no sistema de ficheiros.</span><span class="sxs-lookup"><span data-stu-id="8d06d-125">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
> <span data-ttu-id="8d06d-126">Geralmente, estará em `.dotnet/tools` na pasta de perfil de utilizador.</span><span class="sxs-lookup"><span data-stu-id="8d06d-126">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
***

<span data-ttu-id="8d06d-127">Já está!</span><span class="sxs-lookup"><span data-stu-id="8d06d-127">That's it!</span></span> <span data-ttu-id="8d06d-128">Tem agora o kernel do IQ# para Jupyter, que fornece a principal funcionalidade para compilar e executar operações Q# a partir do Q# Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="8d06d-128">You now have the IQ# kernel for Jupyter, which provides the core functionality for compiling and running Q# operations from Q# Jupyter Notebooks.</span></span>

## <a name="create-your-first-no-locq-notebook"></a><span data-ttu-id="8d06d-129">Crie o seu primeiro bloco de notas Q#</span><span class="sxs-lookup"><span data-stu-id="8d06d-129">Create your first Q# notebook</span></span>

<span data-ttu-id="8d06d-130">Agora, está preparado para verificar a instalação do Q# Jupyter Notebook ao escrever e executar uma operação Q# simples.</span><span class="sxs-lookup"><span data-stu-id="8d06d-130">Now you are ready to verify your Q# Jupyter Notebook installation by writing and running a simple Q# operation.</span></span>

1. <span data-ttu-id="8d06d-131">A partir do ambiente que criou durante a instalação (ou seja, o ambiente conda que criou ou o ambiente Python onde instalou o Jupyter), execute o seguinte comando para iniciar o servidor do Jupyter Notebook:</span><span class="sxs-lookup"><span data-stu-id="8d06d-131">From the environment you created during installation (i.e., either the conda environment you created, or the Python environment where you installed Jupyter), run the following command to start the Jupyter Notebook server:</span></span>

    ```
    jupyter notebook
    ```

    - <span data-ttu-id="8d06d-132">Se o Jupyter Notebook não abrir automaticamente no browser, copie e cole o URL fornecido pela linha de comandos no browser.</span><span class="sxs-lookup"><span data-stu-id="8d06d-132">If the Jupyter Notebook doesn't open automatically in your browser, copy and paste the URL provided by the command line into your browser.</span></span>

1. <span data-ttu-id="8d06d-133">Escolha **Novo → Q#** para criar um Jupyter Notebook com um kernel do Q# e adicione o seguinte código à primeira célula do bloco de notas:</span><span class="sxs-lookup"><span data-stu-id="8d06d-133">Choose **New → Q#** to create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="6-13":::

1. <span data-ttu-id="8d06d-134">Execute esta célula do bloco de notas:</span><span class="sxs-lookup"><span data-stu-id="8d06d-134">Run this cell of the notebook:</span></span>

    ![Célula do Jupyter Notebook com código Q#](~/media/install-guide-jupyter.png)

    <span data-ttu-id="8d06d-136">Deverá ver `SampleQuantumRandomNumberGenerator` na saída da célula.</span><span class="sxs-lookup"><span data-stu-id="8d06d-136">You should see `SampleQuantumRandomNumberGenerator` in the output of the cell.</span></span> <span data-ttu-id="8d06d-137">Ao executar no Jupyter Notebook, o código Q# é compilado e a célula produz o nome das operações que encontra.</span><span class="sxs-lookup"><span data-stu-id="8d06d-137">When running in Jupyter Notebook, the Q# code is compiled, and the cell outputs the name of any operations that it finds.</span></span>

1. <span data-ttu-id="8d06d-138">Numa célula nova, execute a operação que acabou de criar (num simulador) com o comando `%simulate`:</span><span class="sxs-lookup"><span data-stu-id="8d06d-138">In a new cell, run the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

    ![Célula do bloco de notas do Jupyter Notebook com o magic %simulate](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="8d06d-140">Deverá ver o resultado da operação que invocou.</span><span class="sxs-lookup"><span data-stu-id="8d06d-140">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="8d06d-141">Neste caso, como a operação gera um resultado aleatório, verá `Zero` ou `One` impressos no ecrã.</span><span class="sxs-lookup"><span data-stu-id="8d06d-141">In this case, because your operation generates a random result, you will see either `Zero` or `One` printed on the screen.</span></span> <span data-ttu-id="8d06d-142">Se executar a célula repetidamente, deverá ver cada resultado aproximadamente metade do tempo.</span><span class="sxs-lookup"><span data-stu-id="8d06d-142">If you run the cell repeatedly, you should see each result approximately half the time.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8d06d-143">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="8d06d-143">Next steps</span></span>

<span data-ttu-id="8d06d-144">Agora que instalou o QDK para o Q# Jupyter Notebook, pode escrever e executar [o seu primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng) ao escrever código Q# diretamente no ambiente do Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="8d06d-144">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="8d06d-145">Para obter mais exemplos do que pode fazer com o Q# Jupyter Notebook, veja:</span><span class="sxs-lookup"><span data-stu-id="8d06d-145">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>

- <span data-ttu-id="8d06d-146">[Introdução ao Q# e ao Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span><span class="sxs-lookup"><span data-stu-id="8d06d-146">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="8d06d-147">Aqui, encontrará um Q# Jupyter Notebook que mostra mais detalhes sobre como utilizar o Q# no ambiente do Jupyter.</span><span class="sxs-lookup"><span data-stu-id="8d06d-147">There you will find a Q# Jupyter Notebook that provides more details on how to use Q# in the Jupyter environment.</span></span>
- <span data-ttu-id="8d06d-148">[Quantum Katas](xref:microsoft.quantum.overview.katas), uma coleção open-source de tutoriais ao seu ritmo e de conjuntos de exercícios de programação na forma de blocos de notas do Q# Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="8d06d-148">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="8d06d-149">Os [blocos de notas de tutoriais do Quantum Katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) são um bom ponto de partida.</span><span class="sxs-lookup"><span data-stu-id="8d06d-149">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="8d06d-150">Os Quantum Katas têm como objetivo ensinar-lhe elementos de computação quântica e programação em Q# ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="8d06d-150">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="8d06d-151">São um excelente exemplo dos tipos de conteúdos que pode criar com o Q# Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="8d06d-151">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
