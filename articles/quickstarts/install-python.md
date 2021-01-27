---
title: Programar com Q# e Python
description: Saiba como criar uma aplicação Q# com o Python.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: quickstart
uid: microsoft.quantum.install.python
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1ec40b6f1b7a8d9144860e3b8cfd554eb51bae81
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844275"
---
# <a name="develop-with-no-locq-and-python"></a><span data-ttu-id="907b7-103">Programar com Q# e Python</span><span class="sxs-lookup"><span data-stu-id="907b7-103">Develop with Q# and Python</span></span>

<span data-ttu-id="907b7-104">Instale o QDK para desenvolver programas anfitriões Python para chamar operações Q#.</span><span class="sxs-lookup"><span data-stu-id="907b7-104">Install the QDK to develop Python host programs to call Q# operations.</span></span>

## <a name="install-the-qsharp-python-package"></a><span data-ttu-id="907b7-105">Instale o pacote `qsharp` do Python</span><span class="sxs-lookup"><span data-stu-id="907b7-105">Install the `qsharp` Python package</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="907b7-106">Instale com o conda (recomendado)</span><span class="sxs-lookup"><span data-stu-id="907b7-106">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="907b7-107">Instale o [Miniconda](https://docs.conda.io/en/latest/miniconda.html) ou o [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span><span class="sxs-lookup"><span data-stu-id="907b7-107">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span> <span data-ttu-id="907b7-108">**Nota:** Instalação de 64 bits obrigatória.</span><span class="sxs-lookup"><span data-stu-id="907b7-108">**Note:** 64-bit installation required.</span></span>

1. <span data-ttu-id="907b7-109">Abra um Pedido do Anaconda.</span><span class="sxs-lookup"><span data-stu-id="907b7-109">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="907b7-110">Em alternativa, se preferir utilizar o PowerShell ou o pwsh:, abra uma shell, execute `conda init powershell`, feche e reabra a shell.</span><span class="sxs-lookup"><span data-stu-id="907b7-110">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="907b7-111">Crie e ative um novo ambiente conda com o nome `qsharp-env` com os pacotes necessários (incluindo Jupyter Notebook e IQ#) ao executar os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="907b7-111">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="907b7-112">Execute `python -c "import qsharp"` a partir do mesmo terminal para verificar a instalação e povoar a cache de pacotes local com todos os componentes QDK necessários.</span><span class="sxs-lookup"><span data-stu-id="907b7-112">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="907b7-113">Instale com o .NET CLI e o pip (avançado)</span><span class="sxs-lookup"><span data-stu-id="907b7-113">Install using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="907b7-114">Pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="907b7-114">Prerequisites:</span></span>

    - <span data-ttu-id="907b7-115">[Python](https://www.python.org/downloads/) 3.6 ou posterior</span><span class="sxs-lookup"><span data-stu-id="907b7-115">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="907b7-116">O gestor de pacotes Python [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="907b7-116">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="907b7-117">SDK de .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="907b7-117">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="907b7-118">Instale o pacote `qsharp`, um pacote Python que permite interoperabilidade entre o Q# e o Python.</span><span class="sxs-lookup"><span data-stu-id="907b7-118">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="907b7-119">Instale o IQ#, um kernel que o Jupyter e o Python utilizam e que proporciona a principal funcionalidade para compilar e executar operações Q#.</span><span class="sxs-lookup"><span data-stu-id="907b7-119">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and running Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="907b7-120">Se receber um erro durante o passo `dotnet iqsharp install`, abra uma janela de terminal nova e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="907b7-120">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="907b7-121">Se continuar a não funcionar, tente localizar a ferramenta `dotnet-iqsharp` instalada (no Windows, `dotnet-iqsharp.exe`) e executar:</span><span class="sxs-lookup"><span data-stu-id="907b7-121">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="907b7-122">em que `/path/to/dotnet-iqsharp` deve ser substituído pelo caminho absoluto para a ferramenta `dotnet-iqsharp` no sistema de ficheiros.</span><span class="sxs-lookup"><span data-stu-id="907b7-122">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="907b7-123">Geralmente, estará em `.dotnet/tools` na pasta de perfil de utilizador.</span><span class="sxs-lookup"><span data-stu-id="907b7-123">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
<span data-ttu-id="907b7-124">\*\*_</span><span class="sxs-lookup"><span data-stu-id="907b7-124">\*\*_</span></span>

<span data-ttu-id="907b7-125">Já está!</span><span class="sxs-lookup"><span data-stu-id="907b7-125">That's it!</span></span> <span data-ttu-id="907b7-126">Tem agora o pacote `qsharp` do Python e o kernel do IQ# para Jupyter, que fornecem a principal funcionalidade para compilar e executar operações Q# a partir do Python e utilizar o Q# Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="907b7-126">You now have both the `qsharp` Python package and the IQ# kernel for Jupyter, which provide the core functionality for compiling and running Q# operations from Python and allows you to use Q# Jupyter Notebooks.</span></span>

## <a name="choose-your-ide"></a><span data-ttu-id="907b7-127">Escolha o seu IDE</span><span class="sxs-lookup"><span data-stu-id="907b7-127">Choose your IDE</span></span>

<span data-ttu-id="907b7-128">Embora possa utilizar o Q# com o Python em qualquer IDE, recomendamos vivamente utilizar o IDE do Visual Studio Code (VS Code) para as aplicações Q# + Python.</span><span class="sxs-lookup"><span data-stu-id="907b7-128">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="907b7-129">Com a extensão QDK do Visual Studio Code, obtém acesso a funcionalidades mais avançadas, como avisos, realce de sintaxe, modelos de projeto e muito mais.</span><span class="sxs-lookup"><span data-stu-id="907b7-129">With the QDK Visual Studio Code extension you gain access to richer functionality such as warnings, syntax highlighting, project templates, and more.</span></span>

<span data-ttu-id="907b7-130">Se quiser utilizar o VS Code:</span><span class="sxs-lookup"><span data-stu-id="907b7-130">If you would like to use VS Code:</span></span>

- <span data-ttu-id="907b7-131">Instale o [VS Code](https://code.visualstudio.com/download) (Windows, Linux e Mac).</span><span class="sxs-lookup"><span data-stu-id="907b7-131">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
- <span data-ttu-id="907b7-132">Instale a [extensão QDK para o VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="907b7-132">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="907b7-133">Se quiser utilizar um editor diferente, as instruções acima têm tudo definido.</span><span class="sxs-lookup"><span data-stu-id="907b7-133">If you would like to use a different editor, the instructions above have you all set.</span></span>

## <a name="write-your-first-no-locq-program"></a><span data-ttu-id="907b7-134">Escreva o seu primeiro programa Q#</span><span class="sxs-lookup"><span data-stu-id="907b7-134">Write your first Q# program</span></span>

<span data-ttu-id="907b7-135">Agora, está preparado para verificar a instalação do pacote `qsharp` do Python ao escrever e executar um programa Q# simples.</span><span class="sxs-lookup"><span data-stu-id="907b7-135">Now you are ready to verify your `qsharp` Python package installation by writing and running a simple Q# program.</span></span>

1. <span data-ttu-id="907b7-136">Crie uma operação Q# mínima ao criar um ficheiro chamado `Operation.qs` e adicionar ao mesmo o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="907b7-136">Create a minimal Q# operation by creating a file called `Operation.qs` and adding the following code to it:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="3-14":::

1. <span data-ttu-id="907b7-137">Na mesma pasta de `Operation.qs`, crie um programa Python chamado `host.py` para simular a operação Q# `SampleQuantumRandomNumberGenerator()`:</span><span class="sxs-lookup"><span data-stu-id="907b7-137">In the same folder as `Operation.qs`, create a Python program called `host.py` to simulate the Q# `SampleQuantumRandomNumberGenerator()` operation:</span></span>

    ```python
    import qsharp
    from Qrng import SampleQuantumRandomNumberGenerator

    print(SampleQuantumRandomNumberGenerator.simulate())
    ```

1. <span data-ttu-id="907b7-138">A partir do ambiente que criou durante a instalação (ou seja, o ambiente conda ou Python onde instalou `qsharp`), execute o programa:</span><span class="sxs-lookup"><span data-stu-id="907b7-138">From the environment you created during installation (i.e., the conda or Python environment where you installed `qsharp`), run the program:</span></span>

    ```
    python host.py
    ```

1. <span data-ttu-id="907b7-139">Deverá ver o resultado da operação que invocou.</span><span class="sxs-lookup"><span data-stu-id="907b7-139">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="907b7-140">Neste caso, como a operação gera um resultado aleatório, verá `0` ou `1` impressos no ecrã.</span><span class="sxs-lookup"><span data-stu-id="907b7-140">In this case, because your operation generates a random result, you will see either `0` or `1` printed on the screen.</span></span> <span data-ttu-id="907b7-141">Se executar o programa repetidamente, deverá ver cada resultado aproximadamente metade do tempo.</span><span class="sxs-lookup"><span data-stu-id="907b7-141">If you run the program repeatedly, you should see each result approximately half the time.</span></span>

> [!NOTE]
> <span data-ttu-id="907b7-142">_ O código Python é apenas um programa python normal.</span><span class="sxs-lookup"><span data-stu-id="907b7-142">_ The Python code is just a normal Python program.</span></span> <span data-ttu-id="907b7-143">Pode utilizar qualquer ambiente Python, incluindo Jupyter Notebooks baseados em Python, para escrever o programa Python e chamar as operações Q#.</span><span class="sxs-lookup"><span data-stu-id="907b7-143">You can use any Python environment, including Python-based Jupyter Notebooks, to write the Python program and call Q# operations.</span></span> <span data-ttu-id="907b7-144">O programa Python pode importar operações Q# a partir de quaisquer ficheiros .qs localizados na mesma pasta do próprio código Python.</span><span class="sxs-lookup"><span data-stu-id="907b7-144">The Python program can import Q# operations from any .qs files located in the same folder as the Python code itself.</span></span>

## <a name="next-steps"></a><span data-ttu-id="907b7-145">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="907b7-145">Next steps</span></span>

<span data-ttu-id="907b7-146">Agora que testou o Quantum Development Kit no seu ambiente preferido, pode seguir este tutorial para escrever e executar [o seu primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="907b7-146">Now that you have tested the Quantum Development Kit in your preferred environment, you can follow this tutorial to write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
