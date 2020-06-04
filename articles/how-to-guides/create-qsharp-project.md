---
title: Saiba como criar um projeto Q# com o Kit de Desenvolvimento Quântico (QDK)
description: Inicialize um projeto para desenvolvimento quântico com o QDK e Q# no ambiente de desenvolvimento da sua escolha
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: 8019b32a3290e2d45124ebb1eb75395f6cb758db
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327531"
---
# <a name="create-a-q-project-in-your-development-environment"></a><span data-ttu-id="2bb64-103">Crie um projeto Q# no seu ambiente de desenvolvimento</span><span class="sxs-lookup"><span data-stu-id="2bb64-103">Create a Q# project in your development environment</span></span>

<span data-ttu-id="2bb64-104">Saiba como criar um projeto Q# com o QDK.</span><span class="sxs-lookup"><span data-stu-id="2bb64-104">Learn how to create a Q# project with the QDK.</span></span>

<span data-ttu-id="2bb64-105">Um projeto Q# contém ficheiros Q# que contêm código quântico, bem como um programa de anfitrião para executar o programa quântico.</span><span class="sxs-lookup"><span data-stu-id="2bb64-105">A Q# project contains Q# files containing quantum code, as well as a host program to run the quantum program.</span></span> <span data-ttu-id="2bb64-106">Pode escrever o programa de anfitrião em línguas .NET como C#, ou em Python.</span><span class="sxs-lookup"><span data-stu-id="2bb64-106">You can write the host program in .NET languages such as C#, or in Python.</span></span> <span data-ttu-id="2bb64-107">Também pode executar o código Q# num Bloco de Notas Jupyter utilizando o núcleo IQ#.</span><span class="sxs-lookup"><span data-stu-id="2bb64-107">You can also run Q# code in a Jupyter Notebook using the IQ# kernel.</span></span>

<span data-ttu-id="2bb64-108">Escolha o seu ambiente de desenvolvimento e linguagem a partir das secções abaixo:</span><span class="sxs-lookup"><span data-stu-id="2bb64-108">Choose your development environment and language from the sections below:</span></span>

* [<span data-ttu-id="2bb64-109">Python</span><span class="sxs-lookup"><span data-stu-id="2bb64-109">Python</span></span>](#create-a-python-project)
* [<span data-ttu-id="2bb64-110">Q# Jupyter Notebooks</span><span class="sxs-lookup"><span data-stu-id="2bb64-110">Q# Jupyter Notebooks</span></span>](#create-a-q-jupyter-notebook-project)
* [<span data-ttu-id="2bb64-111">C# com Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2bb64-111">C# with Visual Studio</span></span>](#create-a-c-project-on-windows-using-visual-studio)
* [<span data-ttu-id="2bb64-112">C# com Código VS</span><span class="sxs-lookup"><span data-stu-id="2bb64-112">C# with VS Code</span></span>](#create-a-c-project-using-vs-code)
* [<span data-ttu-id="2bb64-113">C# com a linha de comando</span><span class="sxs-lookup"><span data-stu-id="2bb64-113">C# with the command line</span></span>](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a><span data-ttu-id="2bb64-114">Criar um projeto Python</span><span class="sxs-lookup"><span data-stu-id="2bb64-114">Create a Python project</span></span>

1. <span data-ttu-id="2bb64-115">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="2bb64-115">Pre-requisites</span></span>

     * <span data-ttu-id="2bb64-116">Instale o [Kit de Desenvolvimento Quântico para Python](xref:microsoft.quantum.install.python)</span><span class="sxs-lookup"><span data-stu-id="2bb64-116">Install the [Quantum Development Kit for Python](xref:microsoft.quantum.install.python)</span></span>

1. <span data-ttu-id="2bb64-117">Crie uma pasta para o seu projeto e navegue para essa pasta</span><span class="sxs-lookup"><span data-stu-id="2bb64-117">Create a folder for your project, and navigate to that folder</span></span>

1. <span data-ttu-id="2bb64-118">Crie um ficheiro Q# chamado `Operation.qs` , e adicione o seu código Q# ao mesmo.</span><span class="sxs-lookup"><span data-stu-id="2bb64-118">Create a Q# file called `Operation.qs`, and add your Q# code to it.</span></span> <span data-ttu-id="2bb64-119">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2bb64-119">For example:</span></span>

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

1. <span data-ttu-id="2bb64-120">Crie um ficheiro de hospedeiro python chamado `host.py` para ligar para a sua operação Q#.</span><span class="sxs-lookup"><span data-stu-id="2bb64-120">Create a python host file called `host.py` to call your Q# operation.</span></span> <span data-ttu-id="2bb64-121">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2bb64-121">For example:</span></span>

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. <span data-ttu-id="2bb64-122">Execute o programa:</span><span class="sxs-lookup"><span data-stu-id="2bb64-122">Run the program:</span></span>

    ```bash
    python host.py
    ```

1. <span data-ttu-id="2bb64-123">Verifique o resultado.</span><span class="sxs-lookup"><span data-stu-id="2bb64-123">Verify the output.</span></span> <span data-ttu-id="2bb64-124">O programa deverá produzir as seguintes linhas:</span><span class="sxs-lookup"><span data-stu-id="2bb64-124">Your program should output the following lines:</span></span>

    ```bash
    Hello from quantum world!
    0
    ```

<span data-ttu-id="2bb64-125">Agora pode continuar a desenvolver o seu programa quântico.</span><span class="sxs-lookup"><span data-stu-id="2bb64-125">You can now continue to develop your quantum program.</span></span>

## <a name="create-a-q-jupyter-notebook-project"></a><span data-ttu-id="2bb64-126">Criar um projeto Q# Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="2bb64-126">Create a Q# Jupyter Notebook project</span></span>

1. <span data-ttu-id="2bb64-127">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="2bb64-127">Pre-requisites</span></span>

    * <span data-ttu-id="2bb64-128">Instale o [Kit de Desenvolvimento Quântico para Cadernos Jupyter](xref:microsoft.quantum.install.jupyter)</span><span class="sxs-lookup"><span data-stu-id="2bb64-128">Install the [Quantum Development Kit for Jupyter Notebooks](xref:microsoft.quantum.install.jupyter)</span></span>

1. <span data-ttu-id="2bb64-129">Execute o comando seguinte para iniciar o servidor de blocos de notas:</span><span class="sxs-lookup"><span data-stu-id="2bb64-129">Run the following command to start the notebook server:</span></span>

    ```bash
    jupyter notebook
    ```

1. <span data-ttu-id="2bb64-130">Navegue para o URL mostrado na linha de comandos.</span><span class="sxs-lookup"><span data-stu-id="2bb64-130">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="2bb64-131">Por exemplo: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span><span class="sxs-lookup"><span data-stu-id="2bb64-131">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

1. <span data-ttu-id="2bb64-132">Uma página jupyter aparece no navegador.</span><span class="sxs-lookup"><span data-stu-id="2bb64-132">A Jupyter page appears in the browser.</span></span> <span data-ttu-id="2bb64-133">No **separador Ficheiros,** selecione **New**  >  **Q#** para criar um Bloco de Notas Jupyter com um kernel Q# .</span><span class="sxs-lookup"><span data-stu-id="2bb64-133">On the **Files** tab, select **New** > **Q#** to create a Jupyter Notebook with a Q# kernel.</span></span> <span data-ttu-id="2bb64-134">Adicione o seguinte código à primeira célula do portátil:</span><span class="sxs-lookup"><span data-stu-id="2bb64-134">Add the following code to the first notebook cell:</span></span>

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. <span data-ttu-id="2bb64-135">Selecione **Cell**  >  **Cell Run Cells** para executar o caderno.</span><span class="sxs-lookup"><span data-stu-id="2bb64-135">Select **Cell** > **Run Cells** to run the notebook.</span></span> <span data-ttu-id="2bb64-136">`SayHello`em breve aparecerão na saída da célula:</span><span class="sxs-lookup"><span data-stu-id="2bb64-136">`SayHello` will soon appear in the cell output:</span></span>

    ![Célula de caderno Jupyter com código Q#](~/media/install-guide-jupyter.png)

    <span data-ttu-id="2bb64-138">Ao correr em Cadernos Jupyter, o código Q# é compilado e o portátil produz o nome da(s) operação(s) que encontra.</span><span class="sxs-lookup"><span data-stu-id="2bb64-138">When running in Jupyter Notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

1. <span data-ttu-id="2bb64-139">Numa nova célula, simule num computador quântico a execução da operação que acabou de criar com o magic `%simulate`:</span><span class="sxs-lookup"><span data-stu-id="2bb64-139">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

    ![Célula de Caderno Jupyter com %simular magia](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="2bb64-141">Deverá ver a mensagem impressa no ecrã com o resultado da operação que invocou (neste caso, está vazio).</span><span class="sxs-lookup"><span data-stu-id="2bb64-141">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>

<span data-ttu-id="2bb64-142">Agora pode adicionar outras operações Q# para continuar o seu desenvolvimento quântico.</span><span class="sxs-lookup"><span data-stu-id="2bb64-142">You can now add other Q# operations to continue your quantum development.</span></span>

## <a name="create-a-c-project-on-windows-using-visual-studio"></a><span data-ttu-id="2bb64-143">Criar um projeto C# no Windows, utilizando o Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2bb64-143">Create a C# project on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="2bb64-144">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="2bb64-144">Pre-requisites</span></span>

    * <span data-ttu-id="2bb64-145">Instale a extensão do [Kit de Desenvolvimento Quântico para o Estúdio Visual](xref:microsoft.quantum.install.cs)</span><span class="sxs-lookup"><span data-stu-id="2bb64-145">Install the [Quantum Development Kit extension for Visual Studio](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="2bb64-146">Crie uma nova aplicação Q#</span><span class="sxs-lookup"><span data-stu-id="2bb64-146">Create a new Q# application</span></span>

    * <span data-ttu-id="2bb64-147">Ir para **arquivar**  ->  **novo**  ->  **projeto**</span><span class="sxs-lookup"><span data-stu-id="2bb64-147">Go to **File** -> **New** -> **Project**</span></span>
    * <span data-ttu-id="2bb64-148">Escreva `Q#` na caixa de pesquisa</span><span class="sxs-lookup"><span data-stu-id="2bb64-148">Type `Q#` in the search box</span></span>
    * <span data-ttu-id="2bb64-149">Selecione **Aplicação Q#**</span><span class="sxs-lookup"><span data-stu-id="2bb64-149">Select **Q# Application**</span></span>
    * <span data-ttu-id="2bb64-150">Selecione **Seguinte**</span><span class="sxs-lookup"><span data-stu-id="2bb64-150">Select **Next**</span></span>
    * <span data-ttu-id="2bb64-151">Escolha um nome e uma localização para a aplicação</span><span class="sxs-lookup"><span data-stu-id="2bb64-151">Choose a name and location for your application</span></span>
    * <span data-ttu-id="2bb64-152">Selecione **Criar**</span><span class="sxs-lookup"><span data-stu-id="2bb64-152">Select **Create**</span></span>

1. <span data-ttu-id="2bb64-153">Inspecione o projeto</span><span class="sxs-lookup"><span data-stu-id="2bb64-153">Inspect the project</span></span>

    <span data-ttu-id="2bb64-154">Deverá ver dois ficheiros criados: `Driver.cs`, que é a aplicação anfitriã C#; e `Operation.qs`, que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola.</span><span class="sxs-lookup"><span data-stu-id="2bb64-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

1. <span data-ttu-id="2bb64-155">Executar a aplicação</span><span class="sxs-lookup"><span data-stu-id="2bb64-155">Run the application</span></span>

    * <span data-ttu-id="2bb64-156">Selecione **Debug**  ->  **Start Without Debugging**</span><span class="sxs-lookup"><span data-stu-id="2bb64-156">Select **Debug** -> **Start Without Debugging**</span></span>
    * <span data-ttu-id="2bb64-157">Deverá ver o texto `Hello quantum world!` impresso numa janela da consola.</span><span class="sxs-lookup"><span data-stu-id="2bb64-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

<span data-ttu-id="2bb64-158">Agora pode continuar o seu desenvolvimento quântico usando o Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2bb64-158">You can now continue your quantum development using Visual Studio</span></span>

> [!NOTE]
> * <span data-ttu-id="2bb64-159">Se tiver vários projetos numa solução do Visual Studio, todos os projetos contidos na solução têm de estar na mesma pasta que a solução ou numa das suas subpastas.</span><span class="sxs-lookup"><span data-stu-id="2bb64-159">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="create-a-c-project-using-vs-code"></a><span data-ttu-id="2bb64-160">Criar um projeto C#, utilizando o Código VS</span><span class="sxs-lookup"><span data-stu-id="2bb64-160">Create a C# project, using VS Code</span></span>

1. <span data-ttu-id="2bb64-161">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="2bb64-161">Pre-requisites</span></span>

    * <span data-ttu-id="2bb64-162">Instale a extensão do [Kit de Desenvolvimento Quântico para o Código VS](xref:microsoft.quantum.install.cs)</span><span class="sxs-lookup"><span data-stu-id="2bb64-162">Install the [Quantum Development Kit extension for VS Code](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="2bb64-163">Crie um novo projeto:</span><span class="sxs-lookup"><span data-stu-id="2bb64-163">Create a new project:</span></span>

    * <span data-ttu-id="2bb64-164">Ir para **ver paleta**  ->  **de comando**</span><span class="sxs-lookup"><span data-stu-id="2bb64-164">Go to **View** -> **Command Palette**</span></span>
    * <span data-ttu-id="2bb64-165">Selecione **Q#: Criar novo projeto**</span><span class="sxs-lookup"><span data-stu-id="2bb64-165">Select **Q#: Create New Project**</span></span>
    * <span data-ttu-id="2bb64-166">Selecione **aplicação de consola autónoma**</span><span class="sxs-lookup"><span data-stu-id="2bb64-166">Select **Standalone console application**</span></span>
    * <span data-ttu-id="2bb64-167">Navegue para a localização no sistema de ficheiros onde quer criar a aplicação</span><span class="sxs-lookup"><span data-stu-id="2bb64-167">Navigate to the location on the file system where you would like to create the application</span></span>
    * <span data-ttu-id="2bb64-168">Clique no botão **Abrir novo projeto...**, após o projeto ser criado.</span><span class="sxs-lookup"><span data-stu-id="2bb64-168">Click on the **Open new project...** button, once the project has been created</span></span>

1. <span data-ttu-id="2bb64-169">Execute a aplicação:</span><span class="sxs-lookup"><span data-stu-id="2bb64-169">Run the application:</span></span>

    * <span data-ttu-id="2bb64-170">Ir para **terminal**  ->  **novo terminal**</span><span class="sxs-lookup"><span data-stu-id="2bb64-170">Go to **Terminal** -> **New Terminal**</span></span>
    * <span data-ttu-id="2bb64-171">Inserir`dotnet run`</span><span class="sxs-lookup"><span data-stu-id="2bb64-171">Enter `dotnet run`</span></span>
    * <span data-ttu-id="2bb64-172">Deverá ver o seguinte texto na janela de saída `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="2bb64-172">You should see the following text in the output window `Hello quantum world!`</span></span>

<span data-ttu-id="2bb64-173">Agora pode continuar o seu desenvolvimento quântico usando o Código do Estúdio Visual.</span><span class="sxs-lookup"><span data-stu-id="2bb64-173">You can now continue your quantum development using Visual Studio Code.</span></span>

> [!NOTE]
> * <span data-ttu-id="2bb64-174">As áreas de trabalho com várias pastas raiz não são atualmente suportadas pela extensão do Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="2bb64-174">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="2bb64-175">Se tiver vários projetos numa área de trabalho do VS Code, todos os projetos terão de estar na mesma pasta raiz.</span><span class="sxs-lookup"><span data-stu-id="2bb64-175">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a><span data-ttu-id="2bb64-176">Criar um projeto C#, utilizando a `dotnet` ferramenta de linha de comando</span><span class="sxs-lookup"><span data-stu-id="2bb64-176">Create a C# project, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="2bb64-177">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="2bb64-177">Pre-requisites</span></span>

    * <span data-ttu-id="2bb64-178">Instale o [Kit de Desenvolvimento Quântico para a linha de comando](xref:microsoft.quantum.install.standalone)</span><span class="sxs-lookup"><span data-stu-id="2bb64-178">Install the [Quantum Development Kit for the command line](xref:microsoft.quantum.install.standalone)</span></span>

1. <span data-ttu-id="2bb64-179">Criar uma nova aplicação</span><span class="sxs-lookup"><span data-stu-id="2bb64-179">Create a new application</span></span>

    ```dotnetcli
    dotnet new console -lang Q# -o <project name>
    ```

1. <span data-ttu-id="2bb64-180">Navegue para o novo diretório de aplicação</span><span class="sxs-lookup"><span data-stu-id="2bb64-180">Navigate to the new application directory</span></span>

    ```bash
    cd <project name>
    ```

    <span data-ttu-id="2bb64-181">Deverá ver que foram criados dois ficheiros, juntamente com os ficheiros de projeto da aplicação: um ficheiro Q# (`Operation.qs`) e um ficheiro de anfitrião C# (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="2bb64-181">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

1. <span data-ttu-id="2bb64-182">Executar a aplicação</span><span class="sxs-lookup"><span data-stu-id="2bb64-182">Run the application</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="2bb64-183">Deverá ver o resultado seguinte: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="2bb64-183">You should see the following output: `Hello quantum world!`</span></span>

<span data-ttu-id="2bb64-184">Agora continuas o teu desenvolvimento quântico, usando ferramentas de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="2bb64-184">You now continue your quantum development, using command line tools.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2bb64-185">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="2bb64-185">Next steps</span></span>

<span data-ttu-id="2bb64-186">Agora que criou um projeto no seu ambiente preferido, pode continuar o seu desenvolvimento quântico.</span><span class="sxs-lookup"><span data-stu-id="2bb64-186">Now that you have created a project in your preferred environment, you can continue your quantum development.</span></span>
