---
title: Saiba como instalar o Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 3ec53934436b47908fd4d794a98933010f6059a7
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035285"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="569b8-102">Instalar o Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="569b8-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="569b8-103">Saiba como instalar o Microsoft Quantum Development Kit (QDK), para que possa começar a utilizar a programação quântica.</span><span class="sxs-lookup"><span data-stu-id="569b8-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="569b8-104">O QDK consiste em:</span><span class="sxs-lookup"><span data-stu-id="569b8-104">The QDK consists of:</span></span>

- <span data-ttu-id="569b8-105">linguagem de programação Q#</span><span class="sxs-lookup"><span data-stu-id="569b8-105">the Q# programming language</span></span>
- <span data-ttu-id="569b8-106">um conjunto de bibliotecas para abstração da funcionalidade complexa em Q#</span><span class="sxs-lookup"><span data-stu-id="569b8-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="569b8-107">uma aplicação anfitriã (escrita em Python ou uma linguagem .NET) que executa operações quânticas escritas em Q#</span><span class="sxs-lookup"><span data-stu-id="569b8-107">a host application (written in Python or a .NET language) that runs quantum operations written in Q#</span></span>
- <span data-ttu-id="569b8-108">ferramentas para facilitar a programação</span><span class="sxs-lookup"><span data-stu-id="569b8-108">tools to facilitate your development</span></span>

<span data-ttu-id="569b8-109">Consoante o ambiente de desenvolvimento escolhido, existem diferentes passos de instalação.</span><span class="sxs-lookup"><span data-stu-id="569b8-109">Depending on your chosen development environment, there are different installation steps.</span></span> <span data-ttu-id="569b8-110">Escolha o ambiente nas secções seguintes.</span><span class="sxs-lookup"><span data-stu-id="569b8-110">Choose your environment from the sections below.</span></span>

## <a name="develop-with-python"></a><span data-ttu-id="569b8-111">Programar com Python</span><span class="sxs-lookup"><span data-stu-id="569b8-111">Develop with Python</span></span>

1. <span data-ttu-id="569b8-112">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="569b8-112">Pre-requisites</span></span>

    - <span data-ttu-id="569b8-113">[Python](https://www.python.org/downloads/) 3.6 ou posterior</span><span class="sxs-lookup"><span data-stu-id="569b8-113">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="569b8-114">O gestor de pacotes Python [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="569b8-114">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - <span data-ttu-id="569b8-115">SDK [.NET Core 2.1 ou posterior](https://www.microsoft.com/net/download)</span><span class="sxs-lookup"><span data-stu-id="569b8-115">[.NET Core SDK 2.1 or later](https://www.microsoft.com/net/download)</span></span>

1. <span data-ttu-id="569b8-116">Instalar o pacote `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="569b8-116">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="569b8-117">Instalar o pacote `qsharp`</span><span class="sxs-lookup"><span data-stu-id="569b8-117">Install the `qsharp` package</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="569b8-118">Verificar a instalação ao criar uma aplicação `Hello World`</span><span class="sxs-lookup"><span data-stu-id="569b8-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="569b8-119">Crie uma operação Q# mínima ao criar um ficheiro chamado `Operation.qs` e adicionar ao mesmo o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="569b8-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

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

    - <span data-ttu-id="569b8-120">Crie um programa Python chamado `hello_world.py` para chamar a operação Q# `SayHello()`:</span><span class="sxs-lookup"><span data-stu-id="569b8-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="569b8-121">Execute o programa:</span><span class="sxs-lookup"><span data-stu-id="569b8-121">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="569b8-122">Verifique o resultado.</span><span class="sxs-lookup"><span data-stu-id="569b8-122">Verify the output.</span></span> <span data-ttu-id="569b8-123">O programa deverá produzir as seguintes linhas:</span><span class="sxs-lookup"><span data-stu-id="569b8-123">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a><span data-ttu-id="569b8-124">Programar com Jupyter Notebooks</span><span class="sxs-lookup"><span data-stu-id="569b8-124">Develop with Jupyter notebooks</span></span>

1. <span data-ttu-id="569b8-125">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="569b8-125">Pre-requisites</span></span>

    - <span data-ttu-id="569b8-126">[Python](https://www.python.org/downloads/) 3.6 ou posterior</span><span class="sxs-lookup"><span data-stu-id="569b8-126">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="569b8-127">Bloco de Notas do Jupyter</span><span class="sxs-lookup"><span data-stu-id="569b8-127">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - <span data-ttu-id="569b8-128">SDK [.NET Core 2.1 ou posterior](https://www.microsoft.com/net/download)</span><span class="sxs-lookup"><span data-stu-id="569b8-128">[.NET Core SDK 2.1 or later](https://www.microsoft.com/net/download)</span></span>

1. <span data-ttu-id="569b8-129">Instalar o pacote `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="569b8-129">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="569b8-130">Verificar a instalação ao criar uma aplicação `Hello World`</span><span class="sxs-lookup"><span data-stu-id="569b8-130">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="569b8-131">Execute o comando seguinte para iniciar o servidor de blocos de notas:</span><span class="sxs-lookup"><span data-stu-id="569b8-131">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="569b8-132">Navegue para o URL mostrado na linha de comandos.</span><span class="sxs-lookup"><span data-stu-id="569b8-132">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="569b8-133">Por exemplo: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="569b8-133">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

    - <span data-ttu-id="569b8-134">Crie um Jupyter Notebook com um kernel Q# e adicione o seguinte código à primeira célula do bloco de notas:</span><span class="sxs-lookup"><span data-stu-id="569b8-134">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="569b8-135">Execute esta célula do bloco de notas:</span><span class="sxs-lookup"><span data-stu-id="569b8-135">Run this cell of the notebook:</span></span>

        ![Célula do Jupyter Notebook](~/media/install-guide-jupyter.png)

        <span data-ttu-id="569b8-137">Deverá ver `SayHello` na saída da célula.</span><span class="sxs-lookup"><span data-stu-id="569b8-137">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="569b8-138">Ao executar em Jupyter Notebooks, o código Q# é compilado e o bloco de notas produz o nome das operações que encontra.</span><span class="sxs-lookup"><span data-stu-id="569b8-138">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

## <a name="develop-with-c-on-windows-using-visual-studio"></a><span data-ttu-id="569b8-139">Desenvolver com C# em Windows, com o Visual Studio</span><span class="sxs-lookup"><span data-stu-id="569b8-139">Develop with C# on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="569b8-140">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="569b8-140">Pre-requisites</span></span>

    - <span data-ttu-id="569b8-141">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, com a carga de trabalho de desenvolvimento para várias plataformas .NET Core ativada</span><span class="sxs-lookup"><span data-stu-id="569b8-141">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="569b8-142">Instalar a extensão do Visual Studio Q#</span><span class="sxs-lookup"><span data-stu-id="569b8-142">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="569b8-143">Transfira a [extensão do Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="569b8-143">Download the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="569b8-144">Adicione a extensão ao Visual Studio</span><span class="sxs-lookup"><span data-stu-id="569b8-144">Add the extension to Visual Studio</span></span>

1. <span data-ttu-id="569b8-145">Verificar a instalação ao criar uma aplicação `Hello World`</span><span class="sxs-lookup"><span data-stu-id="569b8-145">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="569b8-146">Crie uma nova aplicação Q#</span><span class="sxs-lookup"><span data-stu-id="569b8-146">Create a new Q# application</span></span>

        - <span data-ttu-id="569b8-147">Aceda a **Ficheiro** -> **Novo** -> **Projeto**</span><span class="sxs-lookup"><span data-stu-id="569b8-147">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="569b8-148">Escreva `Q#` na caixa de pesquisa</span><span class="sxs-lookup"><span data-stu-id="569b8-148">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="569b8-149">Selecione **Aplicação Q#**</span><span class="sxs-lookup"><span data-stu-id="569b8-149">Select **Q# Application**</span></span>
        - <span data-ttu-id="569b8-150">Selecione **Seguinte**</span><span class="sxs-lookup"><span data-stu-id="569b8-150">Select **Next**</span></span>
        - <span data-ttu-id="569b8-151">Escolha um nome e uma localização para a aplicação</span><span class="sxs-lookup"><span data-stu-id="569b8-151">Choose a name and location for your application</span></span>
        - <span data-ttu-id="569b8-152">Selecione **Criar**</span><span class="sxs-lookup"><span data-stu-id="569b8-152">Select **Create**</span></span>

    - <span data-ttu-id="569b8-153">Inspecione o projeto</span><span class="sxs-lookup"><span data-stu-id="569b8-153">Inspect the project</span></span>

        <span data-ttu-id="569b8-154">Deverá ver dois ficheiros criados: `Driver.cs`, que é a aplicação anfitriã C#; e `Operation.qs`, que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola.</span><span class="sxs-lookup"><span data-stu-id="569b8-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="569b8-155">Executar a aplicação</span><span class="sxs-lookup"><span data-stu-id="569b8-155">Run the application</span></span>

        - <span data-ttu-id="569b8-156">Selecione **Depurar** -> **Iniciar sem Depurar**</span><span class="sxs-lookup"><span data-stu-id="569b8-156">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="569b8-157">Deverá ver o texto `Hello quantum world!` impresso numa janela da consola.</span><span class="sxs-lookup"><span data-stu-id="569b8-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="569b8-158">Se tiver vários projetos numa solução do Visual Studio, todos os projetos contidos na solução têm de estar na mesma pasta que a solução ou numa das suas subpastas.</span><span class="sxs-lookup"><span data-stu-id="569b8-158">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="develop-with-c-using-vs-code"></a><span data-ttu-id="569b8-159">Desenvolver com C#, através do VS Code</span><span class="sxs-lookup"><span data-stu-id="569b8-159">Develop with C#, using VS Code</span></span>

1. <span data-ttu-id="569b8-160">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="569b8-160">Pre-requisites</span></span>

   - [<span data-ttu-id="569b8-161">Código VS</span><span class="sxs-lookup"><span data-stu-id="569b8-161">VS Code</span></span>](https://code.visualstudio.com/download)
   - <span data-ttu-id="569b8-162">SDK [.NET Core 2.1 ou posterior](https://www.microsoft.com/net/download)</span><span class="sxs-lookup"><span data-stu-id="569b8-162">[.NET Core SDK 2.1 or later](https://www.microsoft.com/net/download)</span></span>

1. <span data-ttu-id="569b8-163">Instalar a extensão do VS Code Quantum</span><span class="sxs-lookup"><span data-stu-id="569b8-163">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="569b8-164">Instale a [extensão do VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span><span class="sxs-lookup"><span data-stu-id="569b8-164">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="569b8-165">Instalar os modelos de projeto Quantum:</span><span class="sxs-lookup"><span data-stu-id="569b8-165">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="569b8-166">Aceda a **Ver** -> **Paleta de Comandos**</span><span class="sxs-lookup"><span data-stu-id="569b8-166">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="569b8-167">Selecione **Q#: Instalar modelos de projetos**</span><span class="sxs-lookup"><span data-stu-id="569b8-167">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="569b8-168">Agora, tem o Quantum Development Kit instalado e pronto para utilizar nas aplicações e bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="569b8-168">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="569b8-169">Verificar a instalação ao criar uma aplicação `Hello World`</span><span class="sxs-lookup"><span data-stu-id="569b8-169">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="569b8-170">Crie um novo projeto:</span><span class="sxs-lookup"><span data-stu-id="569b8-170">Create a new project:</span></span>

        - <span data-ttu-id="569b8-171">Aceda a **Ver** -> **Paleta de Comandos**</span><span class="sxs-lookup"><span data-stu-id="569b8-171">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="569b8-172">Selecione **Q#: Criar Novo Projeto**</span><span class="sxs-lookup"><span data-stu-id="569b8-172">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="569b8-173">Navegue para a localização no sistema de ficheiros onde quer criar a aplicação</span><span class="sxs-lookup"><span data-stu-id="569b8-173">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="569b8-174">Clique no botão **Abrir novo projeto...** , após o projeto ser criado.</span><span class="sxs-lookup"><span data-stu-id="569b8-174">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="569b8-175">Execute a aplicação:</span><span class="sxs-lookup"><span data-stu-id="569b8-175">Run the application:</span></span>

        - <span data-ttu-id="569b8-176">Aceda a **Depurar** -> **Iniciar sem Depurar**</span><span class="sxs-lookup"><span data-stu-id="569b8-176">Go to **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="569b8-177">Deverá ver o seguinte texto na janela de saída `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="569b8-177">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> * > * <span data-ttu-id="569b8-178">As áreas de trabalho com várias pastas raiz não são atualmente suportadas pela extensão do Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="569b8-178">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="569b8-179">Se tiver vários projetos numa área de trabalho do VS Code, todos os projetos terão de estar na mesma pasta raiz.</span><span class="sxs-lookup"><span data-stu-id="569b8-179">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="569b8-180">Programar com C# através da ferramenta de linha de comandos `dotnet`</span><span class="sxs-lookup"><span data-stu-id="569b8-180">Develop with C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="569b8-181">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="569b8-181">Pre-requisites</span></span>

    - <span data-ttu-id="569b8-182">SDK [.NET Core 2.1 ou posterior](https://www.microsoft.com/net/download)</span><span class="sxs-lookup"><span data-stu-id="569b8-182">[.NET Core SDK 2.1 or later](https://www.microsoft.com/net/download)</span></span>

1. <span data-ttu-id="569b8-183">Instalar os modelos de projeto Quantum para .NET</span><span class="sxs-lookup"><span data-stu-id="569b8-183">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="569b8-184">Agora, tem o Quantum Development Kit instalado e pronto para utilizar nas aplicações e bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="569b8-184">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="569b8-185">Verificar a instalação ao criar uma aplicação `Hello World`</span><span class="sxs-lookup"><span data-stu-id="569b8-185">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="569b8-186">Criar uma nova aplicação</span><span class="sxs-lookup"><span data-stu-id="569b8-186">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="569b8-187">Navegue para o novo diretório de aplicação</span><span class="sxs-lookup"><span data-stu-id="569b8-187">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="569b8-188">Deverá ver que foram criados dois ficheiros, juntamente com os ficheiros de projeto da aplicação: um ficheiro Q# (`Operation.qs`) e um ficheiro de anfitrião C# (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="569b8-188">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="569b8-189">Executar a aplicação</span><span class="sxs-lookup"><span data-stu-id="569b8-189">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="569b8-190">Deverá ver o resultado seguinte: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="569b8-190">You should see the following output: `Hello quantum world!`</span></span>

## <a name="whats-next"></a><span data-ttu-id="569b8-191">Passos seguintes?</span><span class="sxs-lookup"><span data-stu-id="569b8-191">What's next?</span></span>

<span data-ttu-id="569b8-192">Agora que instalou o Quantum Development Kit no ambiente pretendido, pode escrever e executar [o primeiro programa quântico](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="569b8-192">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
