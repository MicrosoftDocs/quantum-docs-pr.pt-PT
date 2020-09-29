---
title: Desenvolver com aplicações Q#
description: Saiba como criar uma aplicação Q# executada na linha de comandos.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: 68f530d80e5c5f40dc2bcbb185879c3cb6f93f91
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834419"
---
# <a name="develop-with-no-locq-applications"></a><span data-ttu-id="87c3a-103">Desenvolver com aplicações Q#</span><span class="sxs-lookup"><span data-stu-id="87c3a-103">Develop with Q# applications</span></span>

<span data-ttu-id="87c3a-104">Siga as instruções no separador correspondente ao seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="87c3a-104">Follow the instructions at the tab corresponding to your environment.</span></span>

<span data-ttu-id="87c3a-105">Os programas Q# podem ser executados sozinhos, sem um controlador numa linguagem anfitriã, como C#, F# ou Python.</span><span class="sxs-lookup"><span data-stu-id="87c3a-105">Q# programs can run on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="87c3a-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="87c3a-106">Prerequisites</span></span>

- [<span data-ttu-id="87c3a-107">SDK de .NET Core 3.1 ou versão posterior</span><span class="sxs-lookup"><span data-stu-id="87c3a-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="87c3a-108">Instalação</span><span class="sxs-lookup"><span data-stu-id="87c3a-108">Installation</span></span>

<span data-ttu-id="87c3a-109">Embora possa criar aplicações Q# em qualquer IDE, recomendamos que utilize o Visual Studio Code (VS Code) ou o IDE do Visual Studio para desenvolver as suas aplicações Q# localmente.</span><span class="sxs-lookup"><span data-stu-id="87c3a-109">While you can build Q# applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your Q# applications locally.</span></span> <span data-ttu-id="87c3a-110">Para desenvolver na Cloud através do browser, recomendamos o Visual Studio Codespaces.</span><span class="sxs-lookup"><span data-stu-id="87c3a-110">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="87c3a-111">O desenvolvimento nestes ambientes inclui a funcionalidade avançada da extensão QDK, que inclui avisos, realce de sintaxe, modelos de projeto e muito mais.</span><span class="sxs-lookup"><span data-stu-id="87c3a-111">Developing in these environments includes the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

<span data-ttu-id="87c3a-112">Para configurar o VS Code:</span><span class="sxs-lookup"><span data-stu-id="87c3a-112">To configure VS Code:</span></span>

1. <span data-ttu-id="87c3a-113">Transfira e instale o [VS Code](https://code.visualstudio.com/download) (Windows, Linux e Mac).</span><span class="sxs-lookup"><span data-stu-id="87c3a-113">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="87c3a-114">Instale o [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="87c3a-114">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="87c3a-115">Para configurar o Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="87c3a-115">To configure Visual Studio:</span></span>

1. <span data-ttu-id="87c3a-116">Transfira e instale o [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 ou superior com a carga de trabalho de desenvolvimento multiplataforma .NET Core ativada.</span><span class="sxs-lookup"><span data-stu-id="87c3a-116">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="87c3a-117">Transfira e instale o [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="87c3a-117">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

<span data-ttu-id="87c3a-118">Para configurar o Visual Studio Codespaces:</span><span class="sxs-lookup"><span data-stu-id="87c3a-118">To configure Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="87c3a-119">Crie uma [conta do Azure](https://azure.microsoft.com/free/).</span><span class="sxs-lookup"><span data-stu-id="87c3a-119">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="87c3a-120">Crie um ambiente do Codespaces.</span><span class="sxs-lookup"><span data-stu-id="87c3a-120">Create a Codespaces environment.</span></span> <span data-ttu-id="87c3a-121">Siga o [guia de início rápido](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span><span class="sxs-lookup"><span data-stu-id="87c3a-121">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span></span> <span data-ttu-id="87c3a-122">Ao criar o Codespace, recomendamos que introduza `microsoft/Quantum` no campo "Git Repository" (Repositório do Git) para carregar as definições específicas do QDK.</span><span class="sxs-lookup"><span data-stu-id="87c3a-122">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="87c3a-123">Pode agora iniciar o seu novo ambiente e começar a desenvolver no browser através do [IDE da Cloud do VS Codespaces](https://online.visualstudio.com/environments).</span><span class="sxs-lookup"><span data-stu-id="87c3a-123">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="87c3a-124">Pode, em alternativa, utilizar a instalação local do VS Code e utilizar o Codespaces como [ambiente remoto](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span><span class="sxs-lookup"><span data-stu-id="87c3a-124">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>


<span data-ttu-id="87c3a-125">Para instalar o QDK para outro ambiente, introduza o seguinte na linha de comandos:</span><span class="sxs-lookup"><span data-stu-id="87c3a-125">To install the QDK for another environment, enter the following at the command prompt:</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-no-locq"></a><span data-ttu-id="87c3a-126">Programar com Q#</span><span class="sxs-lookup"><span data-stu-id="87c3a-126">Develop with Q#</span></span>

<span data-ttu-id="87c3a-127">Siga as instruções no separador correspondente ao seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="87c3a-127">Follow the instructions on the tab corresponding to your environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="87c3a-128">Código VS</span><span class="sxs-lookup"><span data-stu-id="87c3a-128">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="87c3a-129">Para criar um novo projeto:</span><span class="sxs-lookup"><span data-stu-id="87c3a-129">To create a new project:</span></span>

1. <span data-ttu-id="87c3a-130">Clique em **View** (Ver)  -> **Command Palette** (Paleta de Comandos) e selecione **Q#: Create New Project** (Criar Novo Projeto).</span><span class="sxs-lookup"><span data-stu-id="87c3a-130">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="87c3a-131">Clique em **Standalone console application** (Aplicação de consola autónoma).</span><span class="sxs-lookup"><span data-stu-id="87c3a-131">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="87c3a-132">Navegue para a localização para guardar o projeto e clique em **Create Project** (Criar Projeto).</span><span class="sxs-lookup"><span data-stu-id="87c3a-132">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="87c3a-133">Após a criação do projeto, clique em **Open new project...** (Abrir novo projeto...) no canto inferior direito.</span><span class="sxs-lookup"><span data-stu-id="87c3a-133">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="87c3a-134">Inspecione o projeto.</span><span class="sxs-lookup"><span data-stu-id="87c3a-134">Inspect the project.</span></span> <span data-ttu-id="87c3a-135">Deverá ver um ficheiro de origem com o nome `Program.qs`, que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola.</span><span class="sxs-lookup"><span data-stu-id="87c3a-135">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="87c3a-136">Para executar a aplicação:</span><span class="sxs-lookup"><span data-stu-id="87c3a-136">To run the application:</span></span>

1. <span data-ttu-id="87c3a-137">Clique em **Terminal** (Terminal) -> **New Terminal** (Novo Terminal).</span><span class="sxs-lookup"><span data-stu-id="87c3a-137">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="87c3a-138">Na mensagem do terminal, introduza `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="87c3a-138">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="87c3a-139">Deverá ver o seguinte texto na janela de saída `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="87c3a-139">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> <span data-ttu-id="87c3a-140">As áreas de trabalho com várias pastas raiz não são atualmente suportadas pela extensão Q# do Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="87c3a-140">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="87c3a-141">Se tiver vários projetos numa área de trabalho do VS Code, todos os projetos terão de estar na mesma pasta raiz.</span><span class="sxs-lookup"><span data-stu-id="87c3a-141">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="87c3a-142">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="87c3a-142">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="87c3a-143">Crie uma aplicação `Hello World` Q# para verificar a instalação do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="87c3a-143">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="87c3a-144">Para criar uma aplicação Q# nova:</span><span class="sxs-lookup"><span data-stu-id="87c3a-144">To create a new Q# application:</span></span>

1. <span data-ttu-id="87c3a-145">Abra o Visual Studio e clique em **File** (Ficheiro)  -> **New** (Novo)  -> **Project** (Projeto).</span><span class="sxs-lookup"><span data-stu-id="87c3a-145">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="87c3a-146">Escreva `Q#` na caixa de pesquisa, selecione **Q# Application (Aplicação Q#)**  e clique em **Next** (Seguinte).</span><span class="sxs-lookup"><span data-stu-id="87c3a-146">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="87c3a-147">Introduza um nome e uma localização para a aplicação e clique em **Create** (Criar).</span><span class="sxs-lookup"><span data-stu-id="87c3a-147">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="87c3a-148">Inspecione o projeto.</span><span class="sxs-lookup"><span data-stu-id="87c3a-148">Inspect the project.</span></span> <span data-ttu-id="87c3a-149">Deverá ver um ficheiro de origem com o nome `Program.qs`, que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola.</span><span class="sxs-lookup"><span data-stu-id="87c3a-149">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="87c3a-150">Para executar a aplicação:</span><span class="sxs-lookup"><span data-stu-id="87c3a-150">To run the application:</span></span>

1. <span data-ttu-id="87c3a-151">Selecione **Debug** (Depurar)  -> **Start Without Debugging** (Iniciar Sem Depuração).</span><span class="sxs-lookup"><span data-stu-id="87c3a-151">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="87c3a-152">Deverá ver o texto `Hello quantum world!` impresso numa janela da consola.</span><span class="sxs-lookup"><span data-stu-id="87c3a-152">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="87c3a-153">Se tiver vários projetos numa solução do Visual Studio, todos os projetos contidos na solução têm de estar na mesma pasta que a solução ou numa das subpastas.</span><span class="sxs-lookup"><span data-stu-id="87c3a-153">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-prompt"></a>[<span data-ttu-id="87c3a-154">Outros editores com a linha de comandos</span><span class="sxs-lookup"><span data-stu-id="87c3a-154">Other editors with the command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="87c3a-155">Crie uma aplicação `Hello World` Q# para verificar a sua instalação.</span><span class="sxs-lookup"><span data-stu-id="87c3a-155">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="87c3a-156">Instale os modelos de projeto.</span><span class="sxs-lookup"><span data-stu-id="87c3a-156">Install the project templates.</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. <span data-ttu-id="87c3a-157">Crie uma nova aplicação:</span><span class="sxs-lookup"><span data-stu-id="87c3a-157">Create a new application:</span></span>

    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. <span data-ttu-id="87c3a-158">Navegue para o diretório da aplicação:</span><span class="sxs-lookup"><span data-stu-id="87c3a-158">Navigate to the application directory:</span></span>

    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="87c3a-159">Este diretório deverá conter um ficheiro `Program.qs`, que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola.</span><span class="sxs-lookup"><span data-stu-id="87c3a-159">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="87c3a-160">Pode modificar este modelo com um editor de texto e substituí-lo pelas suas próprias aplicações quânticas.</span><span class="sxs-lookup"><span data-stu-id="87c3a-160">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="87c3a-161">Execute o programa:</span><span class="sxs-lookup"><span data-stu-id="87c3a-161">Run the program:</span></span>

    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="87c3a-162">Deverá ver o seguinte texto impresso: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="87c3a-162">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="87c3a-163">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="87c3a-163">Next steps</span></span>

<span data-ttu-id="87c3a-164">Agora que instalou o Quantum Development Kit no ambiente pretendido, pode escrever e executar [o primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="87c3a-164">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
