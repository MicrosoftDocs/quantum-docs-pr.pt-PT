---
title: Saiba como criar um projeto Q# com o Quantum Development Kit (QDK)
description: Inicialize um projeto para o desenvolvimento quântico com o QDK e Q# no ambiente de desenvolvimento da sua escolha
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: 5fa32f14291fa2070b49e4bb3b720cbf31ee614b
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819897"
---
# <a name="create-a-q-project-in-your-development-environment"></a><span data-ttu-id="95049-103">Crie um projeto Q# no seu ambiente de desenvolvimento</span><span class="sxs-lookup"><span data-stu-id="95049-103">Create a Q# project in your development environment</span></span>

<span data-ttu-id="95049-104">Aprenda a criar um projeto Q# com o QDK.</span><span class="sxs-lookup"><span data-stu-id="95049-104">Learn how to create a Q# project with the QDK.</span></span>

<span data-ttu-id="95049-105">Um projeto Q# contém ficheiros Q# contendo código quântico, bem como um programa de anfitriões para executar o programa quântico.</span><span class="sxs-lookup"><span data-stu-id="95049-105">A Q# project contains Q# files containing quantum code, as well as a host program to run the quantum program.</span></span> <span data-ttu-id="95049-106">Pode escrever o programa anfitrião em C#línguas .NET, como, ou em Python.</span><span class="sxs-lookup"><span data-stu-id="95049-106">You can write the host program in .NET languages such as C#, or in Python.</span></span> <span data-ttu-id="95049-107">Você também pode executar o código Q# em um caderno Jupyter usando o kernel IQ#.</span><span class="sxs-lookup"><span data-stu-id="95049-107">You can also run Q# code in a Jupyter notebook using the IQ# kernel.</span></span>

<span data-ttu-id="95049-108">Escolha o seu ambiente e linguagem de desenvolvimento nas secções abaixo:</span><span class="sxs-lookup"><span data-stu-id="95049-108">Choose your development environment and language from the sections below:</span></span>

* [<span data-ttu-id="95049-109">Python</span><span class="sxs-lookup"><span data-stu-id="95049-109">Python</span></span>](#create-a-python-project)
* [<span data-ttu-id="95049-110">Cadernos Q# Jupyter</span><span class="sxs-lookup"><span data-stu-id="95049-110">Q# Jupyter notebooks</span></span>](#create-a-q-jupyter-notebook-project)
* [<span data-ttu-id="95049-111">C#com Estúdio Visual</span><span class="sxs-lookup"><span data-stu-id="95049-111">C# with Visual Studio</span></span>](#create-a-c-project-on-windows-using-visual-studio)
* [<span data-ttu-id="95049-112">C#com código VS</span><span class="sxs-lookup"><span data-stu-id="95049-112">C# with VS Code</span></span>](#create-a-c-project-using-vs-code)
* [<span data-ttu-id="95049-113">C#com a linha de comando</span><span class="sxs-lookup"><span data-stu-id="95049-113">C# with the command line</span></span>](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a><span data-ttu-id="95049-114">Criar um projeto Python</span><span class="sxs-lookup"><span data-stu-id="95049-114">Create a Python project</span></span>

1. <span data-ttu-id="95049-115">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="95049-115">Pre-requisites</span></span>

     * <span data-ttu-id="95049-116">Instale o [Kit de Desenvolvimento Quântico para Python](xref:microsoft.quantum.install.python)</span><span class="sxs-lookup"><span data-stu-id="95049-116">Install the [Quantum Development Kit for Python](xref:microsoft.quantum.install.python)</span></span>

1. <span data-ttu-id="95049-117">Crie uma pasta para o seu projeto e navegue para essa pasta</span><span class="sxs-lookup"><span data-stu-id="95049-117">Create a folder for your project, and navigate to that folder</span></span>

1. <span data-ttu-id="95049-118">Crie um ficheiro Q# chamado `Operation.qs`e adicione-lhe o seu código Q#.</span><span class="sxs-lookup"><span data-stu-id="95049-118">Create a Q# file called `Operation.qs`, and add your Q# code to it.</span></span> <span data-ttu-id="95049-119">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="95049-119">For example:</span></span>

    ```qsharp
    namespace HelloWorld {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation SayHello() : Result {
            Message("Hello from quantum world!");
            return Zero;
        }
    }
    ```

1. <span data-ttu-id="95049-120">Crie um ficheiro de anfitriões python chamado `host.py` para ligar para a sua operação Q#.</span><span class="sxs-lookup"><span data-stu-id="95049-120">Create a python host file called `host.py` to call your Q# operation.</span></span> <span data-ttu-id="95049-121">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="95049-121">For example:</span></span>

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. <span data-ttu-id="95049-122">Execute o programa:</span><span class="sxs-lookup"><span data-stu-id="95049-122">Run the program:</span></span>

    ```bash
    python host.py
    ```

1. <span data-ttu-id="95049-123">Verifique o resultado.</span><span class="sxs-lookup"><span data-stu-id="95049-123">Verify the output.</span></span> <span data-ttu-id="95049-124">O programa deverá produzir as seguintes linhas:</span><span class="sxs-lookup"><span data-stu-id="95049-124">Your program should output the following lines:</span></span>

    ```bash
    Hello from quantum world!
    0
    ```

<span data-ttu-id="95049-125">Agora pode continuar a desenvolver o seu programa quântico.</span><span class="sxs-lookup"><span data-stu-id="95049-125">You can now continue to develop your quantum program.</span></span>

## <a name="create-a-q-jupyter-notebook-project"></a><span data-ttu-id="95049-126">Crie um projeto Q# Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="95049-126">Create a Q# Jupyter Notebook project</span></span>

1. <span data-ttu-id="95049-127">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="95049-127">Pre-requisites</span></span>

    * <span data-ttu-id="95049-128">Instale o [Kit de Desenvolvimento Quântico para os cadernos Jupyter](xref:microsoft.quantum.install.jupyter)</span><span class="sxs-lookup"><span data-stu-id="95049-128">Install the [Quantum Development Kit for Jupyter notebooks](xref:microsoft.quantum.install.jupyter)</span></span>

1. <span data-ttu-id="95049-129">Execute o comando seguinte para iniciar o servidor de blocos de notas:</span><span class="sxs-lookup"><span data-stu-id="95049-129">Run the following command to start the notebook server:</span></span>

    ```bash
    jupyter notebook
    ```

1. <span data-ttu-id="95049-130">Navegue para o URL mostrado na linha de comandos.</span><span class="sxs-lookup"><span data-stu-id="95049-130">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="95049-131">Por exemplo: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="95049-131">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

1. <span data-ttu-id="95049-132">Uma página de Jupyter aparece no navegador.</span><span class="sxs-lookup"><span data-stu-id="95049-132">A Jupyter page appears in the browser.</span></span> <span data-ttu-id="95049-133">No separador **Ficheiros,** selecione **New** > **Q#** para criar um caderno Jupyter com um kernel Q#.</span><span class="sxs-lookup"><span data-stu-id="95049-133">On the **Files** tab, select **New** > **Q#** to create a Jupyter notebook with a Q# kernel.</span></span> <span data-ttu-id="95049-134">Adicione o seguinte código à primeira célula de caderno:</span><span class="sxs-lookup"><span data-stu-id="95049-134">Add the following code to the first notebook cell:</span></span>

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. <span data-ttu-id="95049-135">Selecione **Cell** > **Executar Células** para executar o caderno.</span><span class="sxs-lookup"><span data-stu-id="95049-135">Select **Cell** > **Run Cells** to run the notebook.</span></span> <span data-ttu-id="95049-136">`SayHello` aparecerão em breve na saída da célula:</span><span class="sxs-lookup"><span data-stu-id="95049-136">`SayHello` will soon appear in the cell output:</span></span>

    ![Célula do Jupyter Notebook com código Q#](~/media/install-guide-jupyter.png)

    <span data-ttu-id="95049-138">Ao ser recorrido em Cadernos Jupyter, o código Q# é compilado e o caderno produz o nome da operação(s) que encontra.</span><span class="sxs-lookup"><span data-stu-id="95049-138">When running in Jupyter Notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

1. <span data-ttu-id="95049-139">Numa nova célula, simule num computador quântico a execução da operação que acabou de criar com o magic `%simulate`:</span><span class="sxs-lookup"><span data-stu-id="95049-139">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

    ![Célula do Jupyter Notebook com o magic %simulate](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="95049-141">Deverá ver a mensagem impressa no ecrã com o resultado da operação que invocou (neste caso, está vazio).</span><span class="sxs-lookup"><span data-stu-id="95049-141">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>

<span data-ttu-id="95049-142">Agora pode adicionar outras operações de Q# para continuar o seu desenvolvimento quântico.</span><span class="sxs-lookup"><span data-stu-id="95049-142">You can now add other Q# operations to continue your quantum development.</span></span>

## <a name="create-a-c-project-on-windows-using-visual-studio"></a><span data-ttu-id="95049-143">Criar C# um projeto no Windows, utilizando o Visual Studio</span><span class="sxs-lookup"><span data-stu-id="95049-143">Create a C# project on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="95049-144">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="95049-144">Pre-requisites</span></span>

    * <span data-ttu-id="95049-145">Instale a [extensão do Kit de Desenvolvimento Quântico para Estúdio Visual](xref:microsoft.quantum.install.cs)</span><span class="sxs-lookup"><span data-stu-id="95049-145">Install the [Quantum Development Kit extension for Visual Studio](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="95049-146">Crie uma nova aplicação Q#</span><span class="sxs-lookup"><span data-stu-id="95049-146">Create a new Q# application</span></span>

    * <span data-ttu-id="95049-147">Aceda a **Ficheiro** -> **Novo** -> **Projeto**</span><span class="sxs-lookup"><span data-stu-id="95049-147">Go to **File** -> **New** -> **Project**</span></span>
    * <span data-ttu-id="95049-148">Escreva `Q#` na caixa de pesquisa</span><span class="sxs-lookup"><span data-stu-id="95049-148">Type `Q#` in the search box</span></span>
    * <span data-ttu-id="95049-149">Selecione **Aplicação Q#**</span><span class="sxs-lookup"><span data-stu-id="95049-149">Select **Q# Application**</span></span>
    * <span data-ttu-id="95049-150">Selecione **Seguinte**</span><span class="sxs-lookup"><span data-stu-id="95049-150">Select **Next**</span></span>
    * <span data-ttu-id="95049-151">Escolha um nome e uma localização para a aplicação</span><span class="sxs-lookup"><span data-stu-id="95049-151">Choose a name and location for your application</span></span>
    * <span data-ttu-id="95049-152">Selecione **Criar**</span><span class="sxs-lookup"><span data-stu-id="95049-152">Select **Create**</span></span>

1. <span data-ttu-id="95049-153">Inspecione o projeto</span><span class="sxs-lookup"><span data-stu-id="95049-153">Inspect the project</span></span>

    <span data-ttu-id="95049-154">Deverá ver dois ficheiros criados: `Driver.cs`, que é a aplicação anfitriã C#; e `Operation.qs`, que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola.</span><span class="sxs-lookup"><span data-stu-id="95049-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

1. <span data-ttu-id="95049-155">Executar a aplicação</span><span class="sxs-lookup"><span data-stu-id="95049-155">Run the application</span></span>

    * <span data-ttu-id="95049-156">Selecione **Depurar** -> **Iniciar sem Depurar**</span><span class="sxs-lookup"><span data-stu-id="95049-156">Select **Debug** -> **Start Without Debugging**</span></span>
    * <span data-ttu-id="95049-157">Deverá ver o texto `Hello quantum world!` impresso numa janela da consola.</span><span class="sxs-lookup"><span data-stu-id="95049-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

<span data-ttu-id="95049-158">Agora pode continuar o seu desenvolvimento quântico usando o Visual Studio</span><span class="sxs-lookup"><span data-stu-id="95049-158">You can now continue your quantum development using Visual Studio</span></span>

> [!NOTE]
> * <span data-ttu-id="95049-159">Se tiver vários projetos numa solução do Visual Studio, todos os projetos contidos na solução têm de estar na mesma pasta que a solução ou numa das suas subpastas.</span><span class="sxs-lookup"><span data-stu-id="95049-159">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="create-a-c-project-using-vs-code"></a><span data-ttu-id="95049-160">Criar C# um projeto, usando o Código VS</span><span class="sxs-lookup"><span data-stu-id="95049-160">Create a C# project, using VS Code</span></span>

1. <span data-ttu-id="95049-161">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="95049-161">Pre-requisites</span></span>

    * <span data-ttu-id="95049-162">Instale a [extensão do Kit de Desenvolvimento Quântico para o Código VS](xref:microsoft.quantum.install.cs)</span><span class="sxs-lookup"><span data-stu-id="95049-162">Install the [Quantum Development Kit extension for VS Code](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="95049-163">Crie um novo projeto:</span><span class="sxs-lookup"><span data-stu-id="95049-163">Create a new project:</span></span>

    * <span data-ttu-id="95049-164">Aceda a **Ver** -> **Paleta de Comandos**</span><span class="sxs-lookup"><span data-stu-id="95049-164">Go to **View** -> **Command Palette**</span></span>
    * <span data-ttu-id="95049-165">Selecione **Q#: Criar novo projeto**</span><span class="sxs-lookup"><span data-stu-id="95049-165">Select **Q#: Create New Project**</span></span>
    * <span data-ttu-id="95049-166">Selecione **aplicação** de consola autónoma</span><span class="sxs-lookup"><span data-stu-id="95049-166">Select **Standalone console application**</span></span>
    * <span data-ttu-id="95049-167">Navegue para a localização no sistema de ficheiros onde quer criar a aplicação</span><span class="sxs-lookup"><span data-stu-id="95049-167">Navigate to the location on the file system where you would like to create the application</span></span>
    * <span data-ttu-id="95049-168">Clique no botão **Abrir novo projeto...** , após o projeto ser criado.</span><span class="sxs-lookup"><span data-stu-id="95049-168">Click on the **Open new project...** button, once the project has been created</span></span>

1. <span data-ttu-id="95049-169">Execute a aplicação:</span><span class="sxs-lookup"><span data-stu-id="95049-169">Run the application:</span></span>

    * <span data-ttu-id="95049-170">Ir ao **Terminal** -> **Novo Terminal**</span><span class="sxs-lookup"><span data-stu-id="95049-170">Go to **Terminal** -> **New Terminal**</span></span>
    * <span data-ttu-id="95049-171">Insira `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="95049-171">Enter `dotnet run`</span></span>
    * <span data-ttu-id="95049-172">Deverá ver o seguinte texto na janela de saída `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="95049-172">You should see the following text in the output window `Hello quantum world!`</span></span>

<span data-ttu-id="95049-173">Agora pode continuar o seu desenvolvimento quântico usando o Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="95049-173">You can now continue your quantum development using Visual Studio Code.</span></span>

> [!NOTE]
> * <span data-ttu-id="95049-174">As áreas de trabalho com várias pastas raiz não são atualmente suportadas pela extensão do Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="95049-174">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="95049-175">Se tiver vários projetos numa área de trabalho do VS Code, todos os projetos terão de estar na mesma pasta raiz.</span><span class="sxs-lookup"><span data-stu-id="95049-175">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a><span data-ttu-id="95049-176">Criar C# um projeto, utilizando a ferramenta `dotnet` linha de comando</span><span class="sxs-lookup"><span data-stu-id="95049-176">Create a C# project, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="95049-177">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="95049-177">Pre-requisites</span></span>

    * <span data-ttu-id="95049-178">Instale o [Kit de Desenvolvimento Quântico para a Linha de Comando](xref:microsoft.quantum.install.cs)</span><span class="sxs-lookup"><span data-stu-id="95049-178">Install the [Quantum Development Kit for the Command Line](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="95049-179">Criar uma nova aplicação</span><span class="sxs-lookup"><span data-stu-id="95049-179">Create a new application</span></span>

    ```bash
    dotnet new console -lang Q# -o <project name>
    ```

1. <span data-ttu-id="95049-180">Navegue para o novo diretório de aplicação</span><span class="sxs-lookup"><span data-stu-id="95049-180">Navigate to the new application directory</span></span>

    ```bash
    cd <project name>
    ```

    <span data-ttu-id="95049-181">Deverá ver que foram criados dois ficheiros, juntamente com os ficheiros de projeto da aplicação: um ficheiro Q# (`Operation.qs`) e um ficheiro de anfitrião C# (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="95049-181">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

1. <span data-ttu-id="95049-182">Executar a aplicação</span><span class="sxs-lookup"><span data-stu-id="95049-182">Run the application</span></span>

    ```bash
    dotnet run
    ```

    <span data-ttu-id="95049-183">Deverá ver o resultado seguinte: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="95049-183">You should see the following output: `Hello quantum world!`</span></span>

<span data-ttu-id="95049-184">Agora continua o teu desenvolvimento quântico, usando ferramentas de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="95049-184">You now continue your quantum development, using command line tools.</span></span>

## <a name="whats-next"></a><span data-ttu-id="95049-185">O que se segue?</span><span class="sxs-lookup"><span data-stu-id="95049-185">What's next?</span></span>

<span data-ttu-id="95049-186">Agora que criou um projeto no seu ambiente preferido, pode continuar o seu desenvolvimento quântico.</span><span class="sxs-lookup"><span data-stu-id="95049-186">Now that you have created a project in your preferred environment, you can continue your quantum development.</span></span>
