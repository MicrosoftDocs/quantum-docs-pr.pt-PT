---
title: Desenvolver com Q# +C#
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 1fd829c684502092bb7491b0f46b5f690320c941
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831023"
---
# <a name="develop-with-q--c"></a><span data-ttu-id="34bb5-102">Desenvolver com Q# +C#</span><span class="sxs-lookup"><span data-stu-id="34bb5-102">Develop with Q# + C#</span></span>

<span data-ttu-id="34bb5-103">Instale o QDK para desenvolver C# programas de anfitriões para ligar para as operações Q#.</span><span class="sxs-lookup"><span data-stu-id="34bb5-103">Install the QDK to develop C# host programs to call Q# operations.</span></span>

<span data-ttu-id="34bb5-104">Q# é construído para brincar bem com C#.NET idiomas -- especificamente .</span><span class="sxs-lookup"><span data-stu-id="34bb5-104">Q# is built to play well with .NET languages--specifically C#.</span></span> <span data-ttu-id="34bb5-105">Você pode trabalhar com este emparelhamento dentro de diferentes ambientes de desenvolvimento:</span><span class="sxs-lookup"><span data-stu-id="34bb5-105">You can work with this pairing inside different development environments:</span></span>

- [<span data-ttu-id="34bb5-106">Q# C# + usando o Estúdio Visual (Windows)</span><span class="sxs-lookup"><span data-stu-id="34bb5-106">Q# + C# using Visual Studio (Windows)</span></span>](#VS)
- [<span data-ttu-id="34bb5-107">Q# C# + usando código de estúdio visual (Windows, Linux e Mac)</span><span class="sxs-lookup"><span data-stu-id="34bb5-107">Q# + C# using Visual Studio Code (Windows, Linux and Mac)</span></span>](#VSC)
- [<span data-ttu-id="34bb5-108">Q # C# + usando a ferramenta de linha de comando `dotnet`</span><span class="sxs-lookup"><span data-stu-id="34bb5-108">Q# + C# using the `dotnet` command-line tool</span></span>](#command)

## <span data-ttu-id="34bb5-109">Desenvolver com Q# + C# usando o Visual Studio<a name="VS"></a></span><span class="sxs-lookup"><span data-stu-id="34bb5-109">Develop with Q# + C# using Visual Studio <a name="VS"></a></span></span>

<span data-ttu-id="34bb5-110">O Visual Studio oferece um ambiente rico para desenvolver programas Q#.</span><span class="sxs-lookup"><span data-stu-id="34bb5-110">Visual Studio offers a rich environment for developing Q# programs.</span></span> <span data-ttu-id="34bb5-111">A extensão Q# Visual Studio contém modelos para ficheiros e projetos Q# bem como realce de sintaxe, conclusão de código e suporte intelliSense.</span><span class="sxs-lookup"><span data-stu-id="34bb5-111">The Q# Visual Studio extension contains templates for Q# files and projects as well as syntax highlighting, code completion and IntelliSense support.</span></span>


1. <span data-ttu-id="34bb5-112">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="34bb5-112">Pre-requisites</span></span>

    - <span data-ttu-id="34bb5-113">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, com a carga de trabalho de desenvolvimento para várias plataformas .NET Core ativada</span><span class="sxs-lookup"><span data-stu-id="34bb5-113">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="34bb5-114">Instalar a extensão do Visual Studio Q#</span><span class="sxs-lookup"><span data-stu-id="34bb5-114">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="34bb5-115">Descarregue e instale a [extensão do Estúdio Visual](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="34bb5-115">Download and install the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>

1. <span data-ttu-id="34bb5-116">Verificar a instalação ao criar uma aplicação `Hello World`</span><span class="sxs-lookup"><span data-stu-id="34bb5-116">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="34bb5-117">Crie uma nova aplicação Q#</span><span class="sxs-lookup"><span data-stu-id="34bb5-117">Create a new Q# application</span></span>

        - <span data-ttu-id="34bb5-118">Aceda a **Ficheiro** -> **Novo** -> **Projeto**</span><span class="sxs-lookup"><span data-stu-id="34bb5-118">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="34bb5-119">Escreva `Q#` na caixa de pesquisa</span><span class="sxs-lookup"><span data-stu-id="34bb5-119">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="34bb5-120">Selecione **Aplicação Q#**</span><span class="sxs-lookup"><span data-stu-id="34bb5-120">Select **Q# Application**</span></span>
        - <span data-ttu-id="34bb5-121">Selecione **Seguinte**</span><span class="sxs-lookup"><span data-stu-id="34bb5-121">Select **Next**</span></span>
        - <span data-ttu-id="34bb5-122">Escolha um nome e uma localização para a aplicação</span><span class="sxs-lookup"><span data-stu-id="34bb5-122">Choose a name and location for your application</span></span>
        - <span data-ttu-id="34bb5-123">Selecione **Criar**</span><span class="sxs-lookup"><span data-stu-id="34bb5-123">Select **Create**</span></span>

    - <span data-ttu-id="34bb5-124">Inspecione o projeto</span><span class="sxs-lookup"><span data-stu-id="34bb5-124">Inspect the project</span></span>

        <span data-ttu-id="34bb5-125">Deverá ver dois ficheiros criados: `Driver.cs`, que é a aplicação anfitriã C#; e `Operation.qs`, que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola.</span><span class="sxs-lookup"><span data-stu-id="34bb5-125">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="34bb5-126">Executar a aplicação</span><span class="sxs-lookup"><span data-stu-id="34bb5-126">Run the application</span></span>

        - <span data-ttu-id="34bb5-127">Selecione **Depurar** -> **Iniciar sem Depurar**</span><span class="sxs-lookup"><span data-stu-id="34bb5-127">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="34bb5-128">Deverá ver o texto `Hello quantum world!` impresso numa janela da consola.</span><span class="sxs-lookup"><span data-stu-id="34bb5-128">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="34bb5-129">Se tiver vários projetos numa solução do Visual Studio, todos os projetos contidos na solução têm de estar na mesma pasta que a solução ou numa das suas subpastas.</span><span class="sxs-lookup"><span data-stu-id="34bb5-129">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <span data-ttu-id="34bb5-130">Desenvolver com Q# + C# usando código de estúdio visual<a name="VSC"></a></span><span class="sxs-lookup"><span data-stu-id="34bb5-130">Develop with Q# + C# using Visual Studio Code <a name="VSC"></a></span></span>

<span data-ttu-id="34bb5-131">O Visual Studio Code (VS Code) oferece um ambiente rico para desenvolver programas Q# no Windows, Linux e Mac.</span><span class="sxs-lookup"><span data-stu-id="34bb5-131">Visual Studio Code (VS Code) offers a rich environment for developing Q# programs on Windows, Linux and Mac.</span></span>  <span data-ttu-id="34bb5-132">A extensão do Código Q# VS inclui suporte para destaque de sintaxe Q#, conclusão de código e snippets de código Q#</span><span class="sxs-lookup"><span data-stu-id="34bb5-132">The Q# VS Code extension includes support for Q# syntax highlighting, code completion, and Q# code snippets.</span></span>

1. <span data-ttu-id="34bb5-133">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="34bb5-133">Pre-requisites</span></span>

   - [<span data-ttu-id="34bb5-134">Código VS</span><span class="sxs-lookup"><span data-stu-id="34bb5-134">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="34bb5-135">.NET Core SDK 3.1 ou posterior</span><span class="sxs-lookup"><span data-stu-id="34bb5-135">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="34bb5-136">Instalar a extensão do VS Code Quantum</span><span class="sxs-lookup"><span data-stu-id="34bb5-136">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="34bb5-137">Instale a [extensão do VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span><span class="sxs-lookup"><span data-stu-id="34bb5-137">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="34bb5-138">Instalar os modelos de projeto Quantum:</span><span class="sxs-lookup"><span data-stu-id="34bb5-138">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="34bb5-139">Aceda a **Ver** -> **Paleta de Comandos**</span><span class="sxs-lookup"><span data-stu-id="34bb5-139">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="34bb5-140">Selecione **Q#: Instale modelos de projeto**</span><span class="sxs-lookup"><span data-stu-id="34bb5-140">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="34bb5-141">Agora, tem o Quantum Development Kit instalado e pronto para utilizar nas aplicações e bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="34bb5-141">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="34bb5-142">Verificar a instalação ao criar uma aplicação `Hello World`</span><span class="sxs-lookup"><span data-stu-id="34bb5-142">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="34bb5-143">Crie um novo projeto:</span><span class="sxs-lookup"><span data-stu-id="34bb5-143">Create a new project:</span></span>

        - <span data-ttu-id="34bb5-144">Aceda a **Ver** -> **Paleta de Comandos**</span><span class="sxs-lookup"><span data-stu-id="34bb5-144">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="34bb5-145">Selecione **Q#: Criar novo projeto**</span><span class="sxs-lookup"><span data-stu-id="34bb5-145">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="34bb5-146">Selecione **aplicação** de consola autónoma</span><span class="sxs-lookup"><span data-stu-id="34bb5-146">Select **Standalone console application**</span></span>
        - <span data-ttu-id="34bb5-147">Navegue para a localização no sistema de ficheiros onde quer criar a aplicação</span><span class="sxs-lookup"><span data-stu-id="34bb5-147">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="34bb5-148">Clique no botão **Abrir novo projeto...** , após o projeto ser criado.</span><span class="sxs-lookup"><span data-stu-id="34bb5-148">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="34bb5-149">Se ainda não tiver C# a extensão do Código VS instalada, aparecerá um pop-up.</span><span class="sxs-lookup"><span data-stu-id="34bb5-149">If you don't already have the C# extension for VS Code installed, a pop-up will appear.</span></span> <span data-ttu-id="34bb5-150">Instale a extensão.</span><span class="sxs-lookup"><span data-stu-id="34bb5-150">Install the extension.</span></span> 

    - <span data-ttu-id="34bb5-151">Execute a aplicação:</span><span class="sxs-lookup"><span data-stu-id="34bb5-151">Run the application:</span></span>

        - <span data-ttu-id="34bb5-152">Ir ao **Terminal** -> **Novo Terminal**</span><span class="sxs-lookup"><span data-stu-id="34bb5-152">Go to **Terminal** -> **New Terminal**</span></span>
        - <span data-ttu-id="34bb5-153">Insira `dotnet run`</span><span class="sxs-lookup"><span data-stu-id="34bb5-153">Enter `dotnet run`</span></span>
        - <span data-ttu-id="34bb5-154">Deverá ver o seguinte texto na janela de saída `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="34bb5-154">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> * <span data-ttu-id="34bb5-155">As áreas de trabalho com várias pastas raiz não são atualmente suportadas pela extensão do Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="34bb5-155">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="34bb5-156">Se tiver vários projetos numa área de trabalho do VS Code, todos os projetos terão de estar na mesma pasta raiz.</span><span class="sxs-lookup"><span data-stu-id="34bb5-156">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <span data-ttu-id="34bb5-157">Desenvolver com Q# + C# utilizando a ferramenta de linha de comando `dotnet`<a name="command"></a></span><span class="sxs-lookup"><span data-stu-id="34bb5-157">Develop with Q# + C# using the `dotnet` command-line tool <a name="command"></a></span></span>

<span data-ttu-id="34bb5-158">Como é óbvio, também pode criar e executar programas Q# a partir da linha de comandos ao simplesmente instalar o SDK de .NET Core e os modelos de projeto do QDK.</span><span class="sxs-lookup"><span data-stu-id="34bb5-158">Of course, you can also build and run Q# programs from the command line by simply installing the .NET Core SDK and the QDK project templates.</span></span> 

1. <span data-ttu-id="34bb5-159">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="34bb5-159">Pre-requisites</span></span>

    - [<span data-ttu-id="34bb5-160">.NET Core SDK 3.1 ou posterior</span><span class="sxs-lookup"><span data-stu-id="34bb5-160">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="34bb5-161">Instalar os modelos de projeto Quantum para .NET</span><span class="sxs-lookup"><span data-stu-id="34bb5-161">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="34bb5-162">Agora, tem o Quantum Development Kit instalado e pronto para utilizar nas aplicações e bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="34bb5-162">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="34bb5-163">Verificar a instalação ao criar uma aplicação `Hello World`</span><span class="sxs-lookup"><span data-stu-id="34bb5-163">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="34bb5-164">Criar uma nova aplicação</span><span class="sxs-lookup"><span data-stu-id="34bb5-164">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="34bb5-165">Navegue para o novo diretório de aplicação</span><span class="sxs-lookup"><span data-stu-id="34bb5-165">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="34bb5-166">Deverá ver que foram criados dois ficheiros, juntamente com os ficheiros de projeto da aplicação: um ficheiro Q# (`Operation.qs`) e um ficheiro de anfitrião C# (`Driver.cs`).</span><span class="sxs-lookup"><span data-stu-id="34bb5-166">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="34bb5-167">Executar a aplicação</span><span class="sxs-lookup"><span data-stu-id="34bb5-167">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="34bb5-168">Deverá ver o resultado seguinte: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="34bb5-168">You should see the following output: `Hello quantum world!`</span></span>

    
## <a name="whats-next"></a><span data-ttu-id="34bb5-169">O que se segue?</span><span class="sxs-lookup"><span data-stu-id="34bb5-169">What's next?</span></span>

<span data-ttu-id="34bb5-170">Agora que instalou o Quantum Development Kit no ambiente pretendido, pode escrever e executar [o primeiro programa quântico](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="34bb5-170">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
