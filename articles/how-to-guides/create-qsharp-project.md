---
title: 'Saiba como criar um projeto do Q # com o kit de desenvolvimento Quantum (QDK)'
description: 'Inicialize um projeto para o desenvolvimento Quantum com o QDK e o Q # no ambiente de desenvolvimento de sua escolha'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: b4bec5e7a174b7e2d588331dd2093c7b23a728b0
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/02/2019
ms.locfileid: "73444179"
---
# <a name="create-a-q-project-in-your-development-environment"></a><span data-ttu-id="fa2cd-103">Criar um projeto do Q # em seu ambiente de desenvolvimento</span><span class="sxs-lookup"><span data-stu-id="fa2cd-103">Create a Q# project in your development environment</span></span>

<span data-ttu-id="fa2cd-104">Saiba como criar um projeto do Q # com o QDK.</span><span class="sxs-lookup"><span data-stu-id="fa2cd-104">Learn how to create a Q# project with the QDK.</span></span>

<span data-ttu-id="fa2cd-105">Um projeto Q # contém os arquivos Q # contendo o código Quantum, bem como um programa de host para executar o programa Quantum.</span><span class="sxs-lookup"><span data-stu-id="fa2cd-105">A Q# project contains Q# files containing quantum code, as well as a host program to run the quantum program.</span></span> <span data-ttu-id="fa2cd-106">Você pode escrever o programa host em linguagens C#.net, como ou em Python.</span><span class="sxs-lookup"><span data-stu-id="fa2cd-106">You can write the host program in .NET languages such as C#, or in Python.</span></span> <span data-ttu-id="fa2cd-107">Você também pode executar o código Q # em um notebook Jupyter usando o kernel IQ #.</span><span class="sxs-lookup"><span data-stu-id="fa2cd-107">You can also run Q# code in a Jupyter notebook using the IQ# kernel.</span></span>

<span data-ttu-id="fa2cd-108">Escolha seu ambiente de desenvolvimento e idioma nas seções a seguir:</span><span class="sxs-lookup"><span data-stu-id="fa2cd-108">Choose your development environment and language from the sections below:</span></span>

* [<span data-ttu-id="fa2cd-109">Python</span><span class="sxs-lookup"><span data-stu-id="fa2cd-109">Python</span></span>](#create-a-python-project)
* [<span data-ttu-id="fa2cd-110">Blocos de anotações do Jupyter</span><span class="sxs-lookup"><span data-stu-id="fa2cd-110">Jupyter notebooks</span></span>](#create-a-jupyter-notebook-project)
* [<span data-ttu-id="fa2cd-111">C#com o Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fa2cd-111">C# with Visual Studio</span></span>](#create-a-c-project-on-windows-using-visual-studio)
* [<span data-ttu-id="fa2cd-112">C#com VS Code</span><span class="sxs-lookup"><span data-stu-id="fa2cd-112">C# with VS Code</span></span>](#create-a-c-project-using-vs-code)
* [<span data-ttu-id="fa2cd-113">C#com a linha de comando</span><span class="sxs-lookup"><span data-stu-id="fa2cd-113">C# with the command line</span></span>](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a><span data-ttu-id="fa2cd-114">Criar um projeto Python</span><span class="sxs-lookup"><span data-stu-id="fa2cd-114">Create a Python project</span></span>

1. <span data-ttu-id="fa2cd-115">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="fa2cd-115">Pre-requisites</span></span>

     * <span data-ttu-id="fa2cd-116">O [Kit de desenvolvimento Quantum para Python](xref:microsoft.quantum.install#develop-with-python)</span><span class="sxs-lookup"><span data-stu-id="fa2cd-116">The [Quantum Development Kit for Python](xref:microsoft.quantum.install#develop-with-python)</span></span>

1. <span data-ttu-id="fa2cd-117">Criar uma pasta para seu projeto e navegar até essa pasta</span><span class="sxs-lookup"><span data-stu-id="fa2cd-117">Create a folder for your project, and navigate to that folder</span></span>

1. <span data-ttu-id="fa2cd-118">Crie um arquivo Q # chamado `Operation.qs`e adicione o código Q # a ele.</span><span class="sxs-lookup"><span data-stu-id="fa2cd-118">Create a Q# file called `Operation.qs`, and add your Q# code to it.</span></span> <span data-ttu-id="fa2cd-119">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fa2cd-119">For example:</span></span>

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

1. <span data-ttu-id="fa2cd-120">Crie um arquivo de host Python chamado `host.py` para chamar a operação Q #.</span><span class="sxs-lookup"><span data-stu-id="fa2cd-120">Create a python host file called `host.py` to call your Q# operation.</span></span> <span data-ttu-id="fa2cd-121">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fa2cd-121">For example:</span></span>

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. <span data-ttu-id="fa2cd-122">Execute o programa:</span><span class="sxs-lookup"><span data-stu-id="fa2cd-122">Run the program:</span></span>

    ```bash
    python host.py
    ```

1. <span data-ttu-id="fa2cd-123">Verifique o resultado.</span><span class="sxs-lookup"><span data-stu-id="fa2cd-123">Verify the output.</span></span> <span data-ttu-id="fa2cd-124">O programa deverá produzir as seguintes linhas:</span><span class="sxs-lookup"><span data-stu-id="fa2cd-124">Your program should output the following lines:</span></span>

    ```bash
    Hello from quantum world!
    0
    ```

<span data-ttu-id="fa2cd-125">Agora você pode continuar a desenvolver seu programa Quantum.</span><span class="sxs-lookup"><span data-stu-id="fa2cd-125">You can now continue to develop your quantum program.</span></span>

## <a name="create-a-jupyter-notebook-project"></a><span data-ttu-id="fa2cd-126">Criar um projeto Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="fa2cd-126">Create a Jupyter Notebook project</span></span>

1. <span data-ttu-id="fa2cd-127">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="fa2cd-127">Pre-requisites</span></span>

    * <span data-ttu-id="fa2cd-128">O [Kit de desenvolvimento Quantum para notebooks Jupyter](xref:microsoft.quantum.install#develop-with-jupyter-notebooks)</span><span class="sxs-lookup"><span data-stu-id="fa2cd-128">The [Quantum Development Kit for Jupyter notebooks](xref:microsoft.quantum.install#develop-with-jupyter-notebooks)</span></span>

1. <span data-ttu-id="fa2cd-129">Execute o comando seguinte para iniciar o servidor de blocos de notas:</span><span class="sxs-lookup"><span data-stu-id="fa2cd-129">Run the following command to start the notebook server:</span></span>

    ```bash
    jupyter notebook
    ```

1. <span data-ttu-id="fa2cd-130">Navegue para o URL mostrado na linha de comandos.</span><span class="sxs-lookup"><span data-stu-id="fa2cd-130">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="fa2cd-131">Por exemplo: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="fa2cd-131">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

1. <span data-ttu-id="fa2cd-132">Uma página Jupyter aparece no navegador.</span><span class="sxs-lookup"><span data-stu-id="fa2cd-132">A Jupyter page appears in the browser.</span></span> <span data-ttu-id="fa2cd-133">Na guia **arquivos** , selecione **novo** > **Q #** para criar um notebook Jupyter com um kernel Q #.</span><span class="sxs-lookup"><span data-stu-id="fa2cd-133">On the **Files** tab, select **New** > **Q#** to create a Jupyter notebook with a Q# kernel.</span></span> <span data-ttu-id="fa2cd-134">Adicione o seguinte código à primeira célula do bloco de anotações:</span><span class="sxs-lookup"><span data-stu-id="fa2cd-134">Add the following code to the first notebook cell:</span></span>

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. <span data-ttu-id="fa2cd-135">Selecione a **célula** > **executar células** para executar o bloco de anotações.</span><span class="sxs-lookup"><span data-stu-id="fa2cd-135">Select **Cell** > **Run Cells** to run the notebook.</span></span> <span data-ttu-id="fa2cd-136">`SayHello` aparecerá em breve na saída da célula:</span><span class="sxs-lookup"><span data-stu-id="fa2cd-136">`SayHello` will soon appear in the cell output:</span></span>

    ![Célula do notebook Jupyter com o código de Q #](~/media/install-guide-jupyter.png)

    <span data-ttu-id="fa2cd-138">Ao executar em notebooks Jupyter, o código Q # é compilado e o notebook gera o nome da (s) operação (ões) que encontrará.</span><span class="sxs-lookup"><span data-stu-id="fa2cd-138">When running in Jupyter Notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

1. <span data-ttu-id="fa2cd-139">Em uma nova célula, simule a execução em um computador Quantum da operação que você acabou de criar usando a mágica `%simulate`:</span><span class="sxs-lookup"><span data-stu-id="fa2cd-139">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

    ![Célula do notebook Jupyter com% simula mágica](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="fa2cd-141">Você deve ver a mensagem impressa na tela, juntamente com o resultado da operação que você chamou (nesse caso, vazio).</span><span class="sxs-lookup"><span data-stu-id="fa2cd-141">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>

<span data-ttu-id="fa2cd-142">Agora você pode adicionar outras operações Q # para continuar o desenvolvimento do Quantum.</span><span class="sxs-lookup"><span data-stu-id="fa2cd-142">You can now add other Q# operations to continue your quantum development.</span></span>

## <a name="create-a-c-project-on-windows-using-visual-studio"></a><span data-ttu-id="fa2cd-143">Criar um C# projeto no Windows usando o Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fa2cd-143">Create a C# project on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="fa2cd-144">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="fa2cd-144">Pre-requisites</span></span>

    * <span data-ttu-id="fa2cd-145">O [Kit de desenvolvimento Quantum para Visual Studio](xref:microsoft.quantum.install#develop-with-c-on-windows-using-visual-studio)</span><span class="sxs-lookup"><span data-stu-id="fa2cd-145">The [Quantum Development Kit for Visual Studio](xref:microsoft.quantum.install#develop-with-c-on-windows-using-visual-studio)</span></span>

1. <span data-ttu-id="fa2cd-146">Crie uma nova aplicação Q#</span><span class="sxs-lookup"><span data-stu-id="fa2cd-146">Create a new Q# application</span></span>

    * <span data-ttu-id="fa2cd-147">Aceda a **Ficheiro** -> **Novo** -> **Projeto**</span><span class="sxs-lookup"><span data-stu-id="fa2cd-147">Go to **File** -> **New** -> **Project**</span></span>
    * <span data-ttu-id="fa2cd-148">Escreva `Q#` na caixa de pesquisa</span><span class="sxs-lookup"><span data-stu-id="fa2cd-148">Type `Q#` in the search box</span></span>
    * <span data-ttu-id="fa2cd-149">Selecione **Aplicação Q#**</span><span class="sxs-lookup"><span data-stu-id="fa2cd-149">Select **Q# Application**</span></span>
    * <span data-ttu-id="fa2cd-150">Selecione **Seguinte**</span><span class="sxs-lookup"><span data-stu-id="fa2cd-150">Select **Next**</span></span>
    * <span data-ttu-id="fa2cd-151">Escolha um nome e uma localização para a aplicação</span><span class="sxs-lookup"><span data-stu-id="fa2cd-151">Choose a name and location for your application</span></span>
    * <span data-ttu-id="fa2cd-152">Selecione **Criar**</span><span class="sxs-lookup"><span data-stu-id="fa2cd-152">Select **Create**</span></span>

1. <span data-ttu-id="fa2cd-153">Inspecione o projeto</span><span class="sxs-lookup"><span data-stu-id="fa2cd-153">Inspect the project</span></span>

    <span data-ttu-id="fa2cd-154">Deverá ver dois ficheiros criados: `Driver.cs`, que é a aplicação anfitriã C#; e `Operation.qs`, que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola.</span><span class="sxs-lookup"><span data-stu-id="fa2cd-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

1. <span data-ttu-id="fa2cd-155">Executar a aplicação</span><span class="sxs-lookup"><span data-stu-id="fa2cd-155">Run the application</span></span>

    * <span data-ttu-id="fa2cd-156">Selecione **Depurar** -> **Iniciar sem Depurar**</span><span class="sxs-lookup"><span data-stu-id="fa2cd-156">Select **Debug** -> **Start Without Debugging**</span></span>
    * <span data-ttu-id="fa2cd-157">Deverá ver o texto `Hello quantum world!` impresso numa janela da consola.</span><span class="sxs-lookup"><span data-stu-id="fa2cd-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

<span data-ttu-id="fa2cd-158">Agora você pode continuar o desenvolvimento do Quantum usando o Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fa2cd-158">You can now continue your quantum development using Visual Studio</span></span>

> [!NOTE]
> * <span data-ttu-id="fa2cd-159">Se tiver vários projetos numa solução do Visual Studio, todos os projetos contidos na solução têm de estar na mesma pasta que a solução ou numa das suas subpastas.</span><span class="sxs-lookup"><span data-stu-id="fa2cd-159">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="create-a-c-project-using-vs-code"></a><span data-ttu-id="fa2cd-160">Criar um C# projeto, usando vs Code</span><span class="sxs-lookup"><span data-stu-id="fa2cd-160">Create a C# project, using VS Code</span></span>

1. <span data-ttu-id="fa2cd-161">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="fa2cd-161">Pre-requisites</span></span>

    * <span data-ttu-id="fa2cd-162">O [Kit de desenvolvimento Quantum para vs Code](xref:microsoft.quantum.install#develop-with-c-using-visual-studio-code)</span><span class="sxs-lookup"><span data-stu-id="fa2cd-162">The [Quantum Development Kit for VS Code](xref:microsoft.quantum.install#develop-with-c-using-visual-studio-code)</span></span>

1. <span data-ttu-id="fa2cd-163">Crie um novo projeto:</span><span class="sxs-lookup"><span data-stu-id="fa2cd-163">Create a new project:</span></span>

    * <span data-ttu-id="fa2cd-164">Aceda a **Ver** -> **Paleta de Comandos**</span><span class="sxs-lookup"><span data-stu-id="fa2cd-164">Go to **View** -> **Command Palette**</span></span>
    * <span data-ttu-id="fa2cd-165">Selecione **Q #: criar novo projeto**</span><span class="sxs-lookup"><span data-stu-id="fa2cd-165">Select **Q#: Create New Project**</span></span>
    * <span data-ttu-id="fa2cd-166">Navegue para a localização no sistema de ficheiros onde quer criar a aplicação</span><span class="sxs-lookup"><span data-stu-id="fa2cd-166">Navigate to the location on the file system where you would like to create the application</span></span>
    * <span data-ttu-id="fa2cd-167">Clique no botão **Abrir novo projeto...** , após o projeto ser criado.</span><span class="sxs-lookup"><span data-stu-id="fa2cd-167">Click on the **Open new project...** button, once the project has been created</span></span>

1. <span data-ttu-id="fa2cd-168">Execute a aplicação:</span><span class="sxs-lookup"><span data-stu-id="fa2cd-168">Run the application:</span></span>

    * <span data-ttu-id="fa2cd-169">Aceda a **Depurar** -> **Iniciar sem Depurar**</span><span class="sxs-lookup"><span data-stu-id="fa2cd-169">Go to **Debug** -> **Start Without Debugging**</span></span>
    * <span data-ttu-id="fa2cd-170">Deverá ver o seguinte texto na janela de saída `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="fa2cd-170">You should see the following text in the output window `Hello quantum world!`</span></span>

<span data-ttu-id="fa2cd-171">Agora você pode continuar o desenvolvimento do Quantum usando Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="fa2cd-171">You can now continue your quantum development using Visual Studio Code.</span></span>

> [!NOTE]
> * <span data-ttu-id="fa2cd-172">As áreas de trabalho com várias pastas raiz não são atualmente suportadas pela extensão do Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="fa2cd-172">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="fa2cd-173">Se tiver vários projetos numa área de trabalho do VS Code, todos os projetos terão de estar na mesma pasta raiz.</span><span class="sxs-lookup"><span data-stu-id="fa2cd-173">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a><span data-ttu-id="fa2cd-174">Criar um C# projeto, usando a ferramenta de linha de comando `dotnet`</span><span class="sxs-lookup"><span data-stu-id="fa2cd-174">Create a C# project, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="fa2cd-175">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="fa2cd-175">Pre-requisites</span></span>

    * <span data-ttu-id="fa2cd-176">O [Kit de desenvolvimento Quantum para a linha de comando](xref:microsoft.quantum.install#develop-with-c-using-the-dotnet-command-line-tool)</span><span class="sxs-lookup"><span data-stu-id="fa2cd-176">The [Quantum Development Kit for the Command Line](xref:microsoft.quantum.install#develop-with-c-using-the-dotnet-command-line-tool)</span></span>

1. <span data-ttu-id="fa2cd-177">Criar uma nova aplicação</span><span class="sxs-lookup"><span data-stu-id="fa2cd-177">Create a new application</span></span>

    ```bash
    dotnet new console -lang Q# -o <project name>
    ```

1. <span data-ttu-id="fa2cd-178">Navegue para o novo diretório de aplicação</span><span class="sxs-lookup"><span data-stu-id="fa2cd-178">Navigate to the new application directory</span></span>

    ```bash
    cd <project name>
    ```

    <span data-ttu-id="fa2cd-179">Deverá ver que foram criados dois ficheiros, juntamente com os ficheiros de projeto da aplicação: um ficheiro Q# (`Operation.qs`) e um ficheiro de anfitrião C# (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="fa2cd-179">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

1. <span data-ttu-id="fa2cd-180">Executar a aplicação</span><span class="sxs-lookup"><span data-stu-id="fa2cd-180">Run the application</span></span>

    ```bash
    dotnet run
    ```

    <span data-ttu-id="fa2cd-181">Deverá ver o resultado seguinte: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="fa2cd-181">You should see the following output: `Hello quantum world!`</span></span>

<span data-ttu-id="fa2cd-182">Agora você continua o desenvolvimento do Quantum, usando as ferramentas de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="fa2cd-182">You now continue your quantum development, using command line tools.</span></span>

## <a name="whats-next"></a><span data-ttu-id="fa2cd-183">O que se segue?</span><span class="sxs-lookup"><span data-stu-id="fa2cd-183">What's next?</span></span>

<span data-ttu-id="fa2cd-184">Agora que você criou um projeto em seu ambiente preferido, você pode continuar o desenvolvimento do Quantum.</span><span class="sxs-lookup"><span data-stu-id="fa2cd-184">Now that you have created a project in your preferred environment, you can continue your quantum development.</span></span>
