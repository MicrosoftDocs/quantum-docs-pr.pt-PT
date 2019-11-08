---
title: Saiba como instalar o Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 580ac14f2e839d723884a96e9c5fd336ebcb5da0
ms.sourcegitcommit: 30fcb35986b43388ad65dfb876eb3ad8ad0533ce
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73799152"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="8004c-102">Instalar o Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="8004c-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="8004c-103">Saiba como instalar o Microsoft Quantum Development Kit (QDK), para que possa começar a utilizar a programação quântica.</span><span class="sxs-lookup"><span data-stu-id="8004c-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="8004c-104">O QDK consiste em:</span><span class="sxs-lookup"><span data-stu-id="8004c-104">The QDK consists of:</span></span>

- <span data-ttu-id="8004c-105">linguagem de programação Q#</span><span class="sxs-lookup"><span data-stu-id="8004c-105">the Q# programming language</span></span>
- <span data-ttu-id="8004c-106">um conjunto de bibliotecas para abstração da funcionalidade complexa em Q#</span><span class="sxs-lookup"><span data-stu-id="8004c-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="8004c-107">uma aplicação anfitriã (escrita em Python ou uma linguagem .NET) que executa operações quânticas escritas em Q#</span><span class="sxs-lookup"><span data-stu-id="8004c-107">a host application (written in Python or a .NET language) that runs quantum operations written in Q#</span></span>
- <span data-ttu-id="8004c-108">ferramentas para facilitar a programação</span><span class="sxs-lookup"><span data-stu-id="8004c-108">tools to facilitate your development</span></span>

<span data-ttu-id="8004c-109">Consoante o ambiente de desenvolvimento escolhido, existem diferentes passos de instalação.</span><span class="sxs-lookup"><span data-stu-id="8004c-109">Depending on your chosen development environment, there are different installation steps.</span></span> <span data-ttu-id="8004c-110">Escolha o ambiente nas secções seguintes.</span><span class="sxs-lookup"><span data-stu-id="8004c-110">Choose your environment from the sections below.</span></span>

## <a name="develop-with-python"></a><span data-ttu-id="8004c-111">Programar com Python</span><span class="sxs-lookup"><span data-stu-id="8004c-111">Develop with Python</span></span>

<span data-ttu-id="8004c-112">O pacote qsharp para Python torna mais fácil simular operações e funções Q# no Python.</span><span class="sxs-lookup"><span data-stu-id="8004c-112">The qsharp package for Python makes it easy to simulate Q# operations and functions from within Python.</span></span> <span data-ttu-id="8004c-113">IQ# (pronunciado i-q-sharp) é uma extensão principalmente utilizada pelo Jupyter e Python que fornece a funcionalidade principal que permite compilar e simular operações Q#.</span><span class="sxs-lookup"><span data-stu-id="8004c-113">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python that provides the core functionality for compiling and simulating Q# operations.</span></span>

1. <span data-ttu-id="8004c-114">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="8004c-114">Pre-requisites</span></span>

    - <span data-ttu-id="8004c-115">[Python](https://www.python.org/downloads/) 3.6 ou posterior</span><span class="sxs-lookup"><span data-stu-id="8004c-115">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="8004c-116">O gestor de pacotes Python [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="8004c-116">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="8004c-117">SDK de .NET Core 3.0 ou versão posterior</span><span class="sxs-lookup"><span data-stu-id="8004c-117">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="8004c-118">Instalar o pacote `qsharp`</span><span class="sxs-lookup"><span data-stu-id="8004c-118">Install the `qsharp` package</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="8004c-119">Instalar o pacote `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="8004c-119">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="8004c-120">Verificar a instalação ao criar uma aplicação `Hello World`</span><span class="sxs-lookup"><span data-stu-id="8004c-120">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="8004c-121">Crie uma operação Q# mínima ao criar um ficheiro chamado `Operation.qs` e adicionar ao mesmo o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="8004c-121">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld
        {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Result {
                Message("Hello from quantum world!");
                return Zero;
            }
        }
        ```

    - <span data-ttu-id="8004c-122">Crie um programa Python chamado `hello_world.py` para chamar a operação Q# `SayHello()`:</span><span class="sxs-lookup"><span data-stu-id="8004c-122">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="8004c-123">Execute o programa:</span><span class="sxs-lookup"><span data-stu-id="8004c-123">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="8004c-124">Verifique o resultado.</span><span class="sxs-lookup"><span data-stu-id="8004c-124">Verify the output.</span></span> <span data-ttu-id="8004c-125">O programa deverá produzir as seguintes linhas:</span><span class="sxs-lookup"><span data-stu-id="8004c-125">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a><span data-ttu-id="8004c-126">Programar com Jupyter Notebooks</span><span class="sxs-lookup"><span data-stu-id="8004c-126">Develop with Jupyter notebooks</span></span>

<span data-ttu-id="8004c-127">O Jupyter Notebook, um dos serviços favoritos no contexto académico, laboratórios científicos e programação colaborativa online, oferece execução de código no local (que agora inclui código Q#) juntamente com instruções, notas e outros conteúdos.</span><span class="sxs-lookup"><span data-stu-id="8004c-127">A favorite of academic settings, scientific labs, and online-based collaborative programming, Jupyter Notebooks offer in-place code execution—now including Q# code—along with instructions, notes, and other content.</span></span>  <span data-ttu-id="8004c-128">Eis o que tem de fazer para começar a criar os seus próprios blocos de notas em Q#.</span><span class="sxs-lookup"><span data-stu-id="8004c-128">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="8004c-129">IQ# (pronunciado i-q-sharp) é uma extensão principalmente utilizada pelo Jupyter e Python para o SDK de .NET Core que fornece a funcionalidade principal que permite compilar e simular operações Q#.</span><span class="sxs-lookup"><span data-stu-id="8004c-129">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>


1. <span data-ttu-id="8004c-130">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="8004c-130">Pre-requisites</span></span>

    - <span data-ttu-id="8004c-131">[Python](https://www.python.org/downloads/) 3.6 ou posterior</span><span class="sxs-lookup"><span data-stu-id="8004c-131">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="8004c-132">Bloco de Notas do Jupyter</span><span class="sxs-lookup"><span data-stu-id="8004c-132">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="8004c-133">SDK de .NET Core 3.0 ou versão posterior</span><span class="sxs-lookup"><span data-stu-id="8004c-133">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="8004c-134">Instalar o pacote `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="8004c-134">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="8004c-135">Verificar a instalação ao criar uma aplicação `Hello World`</span><span class="sxs-lookup"><span data-stu-id="8004c-135">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="8004c-136">Execute o comando seguinte para iniciar o servidor de blocos de notas:</span><span class="sxs-lookup"><span data-stu-id="8004c-136">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="8004c-137">Navegue para o URL mostrado na linha de comandos.</span><span class="sxs-lookup"><span data-stu-id="8004c-137">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="8004c-138">Por exemplo: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="8004c-138">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

    - <span data-ttu-id="8004c-139">Crie um Jupyter Notebook com um kernel Q# e adicione o seguinte código à primeira célula do bloco de notas:</span><span class="sxs-lookup"><span data-stu-id="8004c-139">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="8004c-140">Execute esta célula do bloco de notas:</span><span class="sxs-lookup"><span data-stu-id="8004c-140">Run this cell of the notebook:</span></span>

        ![Célula do Jupyter Notebook com código Q#](~/media/install-guide-jupyter.png)

        <span data-ttu-id="8004c-142">Deverá ver `SayHello` na saída da célula.</span><span class="sxs-lookup"><span data-stu-id="8004c-142">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="8004c-143">Ao executar em Jupyter Notebooks, o código Q# é compilado e o bloco de notas produz o nome das operações que encontra.</span><span class="sxs-lookup"><span data-stu-id="8004c-143">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="8004c-144">Numa nova célula, simule num computador quântico a execução da operação que acabou de criar com o magic `%simulate`:</span><span class="sxs-lookup"><span data-stu-id="8004c-144">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

        ![Célula do Jupyter Notebook com o magic %simulate](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="8004c-146">Deverá ver a mensagem impressa no ecrã com o resultado da operação que invocou (neste caso, está vazio).</span><span class="sxs-lookup"><span data-stu-id="8004c-146">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>


## <a name="develop-with-c-on-windows-using-visual-studio"></a><span data-ttu-id="8004c-147">Desenvolver com C# em Windows, com o Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8004c-147">Develop with C# on Windows, using Visual Studio</span></span>

<span data-ttu-id="8004c-148">O Visual Studio oferece um ambiente avançado para o desenvolvimento de programas Q#, além de disponibilizar ótimas funcionalidades como conclusão de código e realce de sintaxe que orienta o programador no percurso de criação de aplicações.</span><span class="sxs-lookup"><span data-stu-id="8004c-148">Visual Studio offers a rich environment for developing Q# programs, offering great features like code completion and syntax highlighting that guide the developer in building their applications.</span></span>  <span data-ttu-id="8004c-149">A extensão Q# do Visual Studio contém modelos para ficheiros e projetos Q#, bem como realce de sintaxe e suporte IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="8004c-149">The Q# Visual Studio extension contains templates for Q# files and projects as well as syntax highlighting and IntelliSense support.</span></span>


1. <span data-ttu-id="8004c-150">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="8004c-150">Pre-requisites</span></span>

    - <span data-ttu-id="8004c-151">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, com a carga de trabalho de desenvolvimento para várias plataformas .NET Core ativada</span><span class="sxs-lookup"><span data-stu-id="8004c-151">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="8004c-152">Instalar a extensão do Visual Studio Q#</span><span class="sxs-lookup"><span data-stu-id="8004c-152">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="8004c-153">Transfira a [extensão do Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="8004c-153">Download the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="8004c-154">Adicione a extensão ao Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8004c-154">Add the extension to Visual Studio</span></span>

1. <span data-ttu-id="8004c-155">Verificar a instalação ao criar uma aplicação `Hello World`</span><span class="sxs-lookup"><span data-stu-id="8004c-155">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="8004c-156">Crie uma nova aplicação Q#</span><span class="sxs-lookup"><span data-stu-id="8004c-156">Create a new Q# application</span></span>

        - <span data-ttu-id="8004c-157">Aceda a **Ficheiro** -> **Novo** -> **Projeto**</span><span class="sxs-lookup"><span data-stu-id="8004c-157">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="8004c-158">Escreva `Q#` na caixa de pesquisa</span><span class="sxs-lookup"><span data-stu-id="8004c-158">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="8004c-159">Selecione **Aplicação Q#**</span><span class="sxs-lookup"><span data-stu-id="8004c-159">Select **Q# Application**</span></span>
        - <span data-ttu-id="8004c-160">Selecione **Seguinte**</span><span class="sxs-lookup"><span data-stu-id="8004c-160">Select **Next**</span></span>
        - <span data-ttu-id="8004c-161">Escolha um nome e uma localização para a aplicação</span><span class="sxs-lookup"><span data-stu-id="8004c-161">Choose a name and location for your application</span></span>
        - <span data-ttu-id="8004c-162">Selecione **Criar**</span><span class="sxs-lookup"><span data-stu-id="8004c-162">Select **Create**</span></span>

    - <span data-ttu-id="8004c-163">Inspecione o projeto</span><span class="sxs-lookup"><span data-stu-id="8004c-163">Inspect the project</span></span>

        <span data-ttu-id="8004c-164">Deverá ver dois ficheiros criados: `Driver.cs`, que é a aplicação anfitriã C#; e `Operation.qs`, que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola.</span><span class="sxs-lookup"><span data-stu-id="8004c-164">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="8004c-165">Executar a aplicação</span><span class="sxs-lookup"><span data-stu-id="8004c-165">Run the application</span></span>

        - <span data-ttu-id="8004c-166">Selecione **Depurar** -> **Iniciar sem Depurar**</span><span class="sxs-lookup"><span data-stu-id="8004c-166">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="8004c-167">Deverá ver o texto `Hello quantum world!` impresso numa janela da consola.</span><span class="sxs-lookup"><span data-stu-id="8004c-167">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="8004c-168">Se tiver vários projetos numa solução do Visual Studio, todos os projetos contidos na solução têm de estar na mesma pasta que a solução ou numa das suas subpastas.</span><span class="sxs-lookup"><span data-stu-id="8004c-168">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="develop-with-c-using-visual-studio-code"></a><span data-ttu-id="8004c-169">Desenvolver com C# com o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="8004c-169">Develop with C#, using Visual Studio Code</span></span>

<span data-ttu-id="8004c-170">O Visual Studio Code (VS Code) oferece um ambiente avançado para o desenvolvimento de programas Q# em vários ambientes de computação, incluindo Windows, Linux e Mac, além de disponibilizar ótimas funcionalidades como conclusão de código e realce de sintaxe que orienta o programador no percurso de criação de aplicações.</span><span class="sxs-lookup"><span data-stu-id="8004c-170">Visual Studio Code (VS Code) offers a rich environment for developing Q# programs across many multiple computer environments, including Windows, Linux and Mac, offering great features like code completion and syntax highlighting that guide the developer in building their applications.</span></span>  <span data-ttu-id="8004c-171">A extensão Q# do VS Code contém realce de sintaxe e fragmentos de código Q#.</span><span class="sxs-lookup"><span data-stu-id="8004c-171">The Q# VS Code extension contains syntax highlighting, and Q# code snippets.</span></span>

1. <span data-ttu-id="8004c-172">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="8004c-172">Pre-requisites</span></span>

   - [<span data-ttu-id="8004c-173">Código VS</span><span class="sxs-lookup"><span data-stu-id="8004c-173">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="8004c-174">SDK de .NET Core 3.0 ou versão posterior</span><span class="sxs-lookup"><span data-stu-id="8004c-174">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="8004c-175">Instalar a extensão do VS Code Quantum</span><span class="sxs-lookup"><span data-stu-id="8004c-175">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="8004c-176">Instale a [extensão do VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span><span class="sxs-lookup"><span data-stu-id="8004c-176">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="8004c-177">Instalar os modelos de projeto Quantum:</span><span class="sxs-lookup"><span data-stu-id="8004c-177">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="8004c-178">Aceda a **Ver** -> **Paleta de Comandos**</span><span class="sxs-lookup"><span data-stu-id="8004c-178">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="8004c-179">Selecione **Q#: Instalar modelos de projetos**</span><span class="sxs-lookup"><span data-stu-id="8004c-179">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="8004c-180">Agora, tem o Quantum Development Kit instalado e pronto para utilizar nas aplicações e bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="8004c-180">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="8004c-181">Verificar a instalação ao criar uma aplicação `Hello World`</span><span class="sxs-lookup"><span data-stu-id="8004c-181">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="8004c-182">Crie um novo projeto:</span><span class="sxs-lookup"><span data-stu-id="8004c-182">Create a new project:</span></span>

        - <span data-ttu-id="8004c-183">Aceda a **Ver** -> **Paleta de Comandos**</span><span class="sxs-lookup"><span data-stu-id="8004c-183">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="8004c-184">Selecione **Q#: Criar Novo Projeto**</span><span class="sxs-lookup"><span data-stu-id="8004c-184">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="8004c-185">Navegue para a localização no sistema de ficheiros onde quer criar a aplicação</span><span class="sxs-lookup"><span data-stu-id="8004c-185">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="8004c-186">Clique no botão **Abrir novo projeto...** , após o projeto ser criado.</span><span class="sxs-lookup"><span data-stu-id="8004c-186">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="8004c-187">Execute a aplicação:</span><span class="sxs-lookup"><span data-stu-id="8004c-187">Run the application:</span></span>

        - <span data-ttu-id="8004c-188">Aceda a **Depurar** -> **Iniciar sem Depurar**</span><span class="sxs-lookup"><span data-stu-id="8004c-188">Go to **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="8004c-189">Deverá ver o seguinte texto na janela de saída `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="8004c-189">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> * > * <span data-ttu-id="8004c-190">As áreas de trabalho com várias pastas raiz não são atualmente suportadas pela extensão do Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="8004c-190">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="8004c-191">Se tiver vários projetos numa área de trabalho do VS Code, todos os projetos terão de estar na mesma pasta raiz.</span><span class="sxs-lookup"><span data-stu-id="8004c-191">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="8004c-192">Programar com C# através da ferramenta de linha de comandos `dotnet`</span><span class="sxs-lookup"><span data-stu-id="8004c-192">Develop with C#, using the `dotnet` command-line tool</span></span>

<span data-ttu-id="8004c-193">Como é óbvio, também pode criar e executar programas Q# a partir da linha de comandos ao simplesmente instalar o SDK de .NET Core e os modelos de projeto do QDK.</span><span class="sxs-lookup"><span data-stu-id="8004c-193">Of course, you can also build and run Q# programs from the command line by simply installing the .NET Core SDK and the QDK project templates.</span></span> 

1. <span data-ttu-id="8004c-194">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="8004c-194">Pre-requisites</span></span>

    - [<span data-ttu-id="8004c-195">SDK de .NET Core 3.0 ou versão posterior</span><span class="sxs-lookup"><span data-stu-id="8004c-195">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="8004c-196">Instalar os modelos de projeto Quantum para .NET</span><span class="sxs-lookup"><span data-stu-id="8004c-196">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="8004c-197">Agora, tem o Quantum Development Kit instalado e pronto para utilizar nas aplicações e bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="8004c-197">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="8004c-198">Verificar a instalação ao criar uma aplicação `Hello World`</span><span class="sxs-lookup"><span data-stu-id="8004c-198">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="8004c-199">Criar uma nova aplicação</span><span class="sxs-lookup"><span data-stu-id="8004c-199">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="8004c-200">Navegue para o novo diretório de aplicação</span><span class="sxs-lookup"><span data-stu-id="8004c-200">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="8004c-201">Deverá ver que foram criados dois ficheiros, juntamente com os ficheiros de projeto da aplicação: um ficheiro Q# (`Operation.qs`) e um ficheiro de anfitrião C# (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="8004c-201">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="8004c-202">Executar a aplicação</span><span class="sxs-lookup"><span data-stu-id="8004c-202">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="8004c-203">Deverá ver o resultado seguinte: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="8004c-203">You should see the following output: `Hello quantum world!`</span></span>

## <a name="whats-next"></a><span data-ttu-id="8004c-204">Passos seguintes?</span><span class="sxs-lookup"><span data-stu-id="8004c-204">What's next?</span></span>

<span data-ttu-id="8004c-205">Agora que instalou o Quantum Development Kit no ambiente pretendido, pode escrever e executar [o primeiro programa quântico](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="8004c-205">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
