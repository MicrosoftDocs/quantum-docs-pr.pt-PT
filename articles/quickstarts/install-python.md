---
title: Programar com Q# e Python
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
no-loc:
- Q#
- $$v
ms.openlocfilehash: 01a5c31a7a920a69f4f90701d370f3a772d2c4d2
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866745"
---
# <a name="develop-with-no-locq-and-python"></a><span data-ttu-id="a9913-102">Programar com Q# e Python</span><span class="sxs-lookup"><span data-stu-id="a9913-102">Develop with Q# and Python</span></span>

<span data-ttu-id="a9913-103">Instale o QDK para desenvolver programas anfitriões Python para chamar operações Q#.</span><span class="sxs-lookup"><span data-stu-id="a9913-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

## <a name="install-the-qsharp-python-package"></a><span data-ttu-id="a9913-104">Instale o pacote `qsharp` do Python</span><span class="sxs-lookup"><span data-stu-id="a9913-104">Install the `qsharp` Python package</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="a9913-105">Instale com o conda (recomendado)</span><span class="sxs-lookup"><span data-stu-id="a9913-105">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="a9913-106">Instale o [Miniconda](https://docs.conda.io/en/latest/miniconda.html) ou o [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span><span class="sxs-lookup"><span data-stu-id="a9913-106">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span> <span data-ttu-id="a9913-107">**Nota:** Instalação de 64 bits obrigatória.</span><span class="sxs-lookup"><span data-stu-id="a9913-107">**Note:** 64-bit installation required.</span></span>

1. <span data-ttu-id="a9913-108">Abra um Pedido do Anaconda.</span><span class="sxs-lookup"><span data-stu-id="a9913-108">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="a9913-109">Em alternativa, se preferir utilizar o PowerShell ou o pwsh:, abra uma shell, execute `conda init powershell`, feche e reabra a shell.</span><span class="sxs-lookup"><span data-stu-id="a9913-109">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="a9913-110">Crie e ative um novo ambiente conda com o nome `qsharp-env` com os pacotes necessários (incluindo Jupyter Notebook e IQ#) ao executar os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="a9913-110">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="a9913-111">Execute `python -c "import qsharp"` a partir do mesmo terminal para verificar a instalação e povoar a cache de pacotes local com todos os componentes QDK necessários.</span><span class="sxs-lookup"><span data-stu-id="a9913-111">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="a9913-112">Instale com o .NET CLI e o pip (avançado)</span><span class="sxs-lookup"><span data-stu-id="a9913-112">Install using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="a9913-113">Pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="a9913-113">Prerequisites:</span></span>

    - <span data-ttu-id="a9913-114">[Python](https://www.python.org/downloads/) 3.6 ou posterior</span><span class="sxs-lookup"><span data-stu-id="a9913-114">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="a9913-115">O gestor de pacotes Python [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="a9913-115">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="a9913-116">SDK de .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="a9913-116">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="a9913-117">Instale o pacote `qsharp`, um pacote Python que permite interoperabilidade entre o Q# e o Python.</span><span class="sxs-lookup"><span data-stu-id="a9913-117">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="a9913-118">Instale o IQ#, um kernel que o Jupyter e o Python utilizam e que proporciona a principal funcionalidade para compilar e executar operações Q#.</span><span class="sxs-lookup"><span data-stu-id="a9913-118">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="a9913-119">Se receber um erro durante o passo `dotnet iqsharp install`, abra uma janela de terminal nova e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="a9913-119">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="a9913-120">Se continuar a não funcionar, tente localizar a ferramenta `dotnet-iqsharp` instalada (no Windows, `dotnet-iqsharp.exe`) e executar:</span><span class="sxs-lookup"><span data-stu-id="a9913-120">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="a9913-121">em que `/path/to/dotnet-iqsharp` deve ser substituído pelo caminho absoluto para a ferramenta `dotnet-iqsharp` no sistema de ficheiros.</span><span class="sxs-lookup"><span data-stu-id="a9913-121">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="a9913-122">Geralmente, estará em `.dotnet/tools` na pasta de perfil de utilizador.</span><span class="sxs-lookup"><span data-stu-id="a9913-122">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
***

<span data-ttu-id="a9913-123">Já está!</span><span class="sxs-lookup"><span data-stu-id="a9913-123">That's it!</span></span> <span data-ttu-id="a9913-124">Tem agora o pacote `qsharp` do Python e o kernel do IQ# para Jupyter, que fornecem a principal funcionalidade para compilar e executar operações Q# a partir do Python e utilizar o Q# Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="a9913-124">You now have both the `qsharp` Python package and the IQ# kernel for Jupyter, which provides the core functionality for compiling and executing Q# operations from Python and allows you to use Q# Jupyter Notebooks.</span></span>

## <a name="choose-your-ide"></a><span data-ttu-id="a9913-125">Escolha o seu IDE</span><span class="sxs-lookup"><span data-stu-id="a9913-125">Choose your IDE</span></span>

<span data-ttu-id="a9913-126">Embora possa utilizar o Q# com o Python em qualquer IDE, recomendamos vivamente utilizar o IDE do Visual Studio Code (VS Code) para as aplicações Q# + Python.</span><span class="sxs-lookup"><span data-stu-id="a9913-126">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="a9913-127">Com a extensão QDK do Visual Studio Code, obtém acesso a funcionalidades mais avançadas, como avisos, realce de sintaxe, modelos de projeto e muito mais.</span><span class="sxs-lookup"><span data-stu-id="a9913-127">With the QDK Visual Studio Code extension you gain access to richer functionality such as warnings, syntax highlighting, project templates, and more.</span></span>

<span data-ttu-id="a9913-128">Se quiser utilizar o VS Code:</span><span class="sxs-lookup"><span data-stu-id="a9913-128">If you would like to use VS Code:</span></span>

- <span data-ttu-id="a9913-129">Instale o [VS Code](https://code.visualstudio.com/download) (Windows, Linux e Mac).</span><span class="sxs-lookup"><span data-stu-id="a9913-129">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
- <span data-ttu-id="a9913-130">Instale a [extensão QDK para o VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="a9913-130">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="a9913-131">Se quiser utilizar um editor diferente, as instruções acima têm tudo definido.</span><span class="sxs-lookup"><span data-stu-id="a9913-131">If you would like to use a different editor, the instructions above have you all set.</span></span>

## <a name="write-your-first-no-locq-program"></a><span data-ttu-id="a9913-132">Escreva o seu primeiro programa Q#</span><span class="sxs-lookup"><span data-stu-id="a9913-132">Write your first Q# program</span></span>

<span data-ttu-id="a9913-133">Agora, está preparado para verificar a instalação do pacote `qsharp` do Python ao escrever e executar um programa Q# simples.</span><span class="sxs-lookup"><span data-stu-id="a9913-133">Now you are ready to verify your `qsharp` Python package installation by writing and executing a simple Q# program.</span></span>

1. <span data-ttu-id="a9913-134">Crie uma operação Q# mínima ao criar um ficheiro chamado `Operation.qs` e adicionar ao mesmo o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="a9913-134">Create a minimal Q# operation by creating a file called `Operation.qs` and adding the following code to it:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="3-14":::

1. <span data-ttu-id="a9913-135">Na mesma pasta de `Operation.qs`, crie um programa Python chamado `host.py` para simular a operação Q# `SampleQuantumRandomNumberGenerator()`:</span><span class="sxs-lookup"><span data-stu-id="a9913-135">In the same folder as `Operation.qs`, create a Python program called `host.py` to simulate the Q# `SampleQuantumRandomNumberGenerator()` operation:</span></span>

    ```python
    import qsharp
    from Qrng import SampleQuantumRandomNumberGenerator

    print(SampleQuantumRandomNumberGenerator.simulate())
    ```

1. <span data-ttu-id="a9913-136">A partir do ambiente que criou durante a instalação (ou seja, o ambiente conda ou Python onde instalou `qsharp`), execute o programa:</span><span class="sxs-lookup"><span data-stu-id="a9913-136">From the environment you created during installation (i.e., the conda or Python environment where you installed `qsharp`), run the program:</span></span>

    ```
    python host.py
    ```

1. <span data-ttu-id="a9913-137">Deverá ver o resultado da operação que invocou.</span><span class="sxs-lookup"><span data-stu-id="a9913-137">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="a9913-138">Neste caso, como a operação gera um resultado aleatório, verá `0` ou `1` impressos no ecrã.</span><span class="sxs-lookup"><span data-stu-id="a9913-138">In this case, because your operation generates a random result, you will see either `0` or `1` printed on the screen.</span></span> <span data-ttu-id="a9913-139">Se executar o programa repetidamente, deverá ver cada resultado aproximadamente metade do tempo.</span><span class="sxs-lookup"><span data-stu-id="a9913-139">If you execute the program repeatedly, you should see each result approximately half the time.</span></span>

> [!NOTE]
> * <span data-ttu-id="a9913-140">O código Python é um programa Python normal.</span><span class="sxs-lookup"><span data-stu-id="a9913-140">The Python code is just a normal Python program.</span></span> <span data-ttu-id="a9913-141">Pode utilizar qualquer ambiente Python, incluindo Jupyter Notebooks baseados em Python, para escrever o programa Python e chamar as operações Q#.</span><span class="sxs-lookup"><span data-stu-id="a9913-141">You can use any Python environment, including Python-based Jupyter Notebooks, to write the Python program and call Q# operations.</span></span> <span data-ttu-id="a9913-142">O programa Python pode importar operações Q# a partir de quaisquer ficheiros .qs localizados na mesma pasta do próprio código Python.</span><span class="sxs-lookup"><span data-stu-id="a9913-142">The Python program can import Q# operations from any .qs files located in the same folder as the Python code itself.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a9913-143">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="a9913-143">Next steps</span></span>

<span data-ttu-id="a9913-144">Agora que instalou o Quantum Development Kit no seu ambiente preferido, pode seguir este tutorial para escrever e executar [o seu primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="a9913-144">Now that you have installed the Quantum Development Kit in your preferred environment, you can follow this tutorial to write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
