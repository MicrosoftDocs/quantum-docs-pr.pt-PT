---
title: Desenvolver com aplicações Q# num IDE
description: Saiba como criar uma aplicação Q# executada na linha de comandos.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: quickstart
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3e4f1e97477ecb0547b1586b1c7603c8a9954584
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844324"
---
# <a name="develop-with-no-locq-applications-in-an-ide"></a><span data-ttu-id="4967a-103">Desenvolver com aplicações Q# num IDE</span><span class="sxs-lookup"><span data-stu-id="4967a-103">Develop with Q# applications in an IDE</span></span>

<span data-ttu-id="4967a-104">Os programas Q# podem ser executados sozinhos, sem um controlador numa linguagem anfitriã, como C#, F# ou Python.</span><span class="sxs-lookup"><span data-stu-id="4967a-104">Q# programs can run on their own, without a driver in a host language like C#, F#, or Python.</span></span> <span data-ttu-id="4967a-105">Pode desenvolver aplicações Q# no Visual Studio Code (VS Code), Visual Studio, Visual Studio Codespaces ou em qualquer editor/IDE e executar aplicações a partir da consola .NET.</span><span class="sxs-lookup"><span data-stu-id="4967a-105">You can develop Q# applications in Visual Studio Code (VS Code), Visual Studio, Visual Studio Codespaces, or with any editor/IDE and run applications from the .NET console.</span></span> 

## <a name="prerequisites-for-all-environments"></a><span data-ttu-id="4967a-106">Pré-requisitos para todos os ambientes</span><span class="sxs-lookup"><span data-stu-id="4967a-106">Prerequisites for all environments</span></span>

- [<span data-ttu-id="4967a-107">SDK de .NET Core 3.1 ou versão posterior</span><span class="sxs-lookup"><span data-stu-id="4967a-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="4967a-108">Instalação</span><span class="sxs-lookup"><span data-stu-id="4967a-108">Installation</span></span>

<span data-ttu-id="4967a-109">Embora possa criar aplicações Q# em qualquer IDE, recomendamos que utilize o Visual Studio Code (VS Code) ou o IDE do Visual Studio para desenvolver as suas aplicações Q# localmente.</span><span class="sxs-lookup"><span data-stu-id="4967a-109">While you can build Q# applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your Q# applications locally.</span></span> <span data-ttu-id="4967a-110">Para desenvolver na Cloud através do browser, recomendamos o Visual Studio Codespaces.</span><span class="sxs-lookup"><span data-stu-id="4967a-110">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="4967a-111">O desenvolvimento nestes ambientes tira partido da funcionalidade avançada da extensão QDK, que inclui avisos, realce de sintaxe, modelos de projeto e muito mais.</span><span class="sxs-lookup"><span data-stu-id="4967a-111">Developing in these environments leverages the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

### <a name="to-configure-for-vs-code"></a><span data-ttu-id="4967a-112">Para configurar para o VS Code:</span><span class="sxs-lookup"><span data-stu-id="4967a-112">To configure for VS Code:</span></span>

1. <span data-ttu-id="4967a-113">Transfira e instale o [VS Code](https://code.visualstudio.com/download) (Windows, Linux e Mac).</span><span class="sxs-lookup"><span data-stu-id="4967a-113">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="4967a-114">Instale o [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="4967a-114">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

### <a name="to-configure-for-visual-studio"></a><span data-ttu-id="4967a-115">Para configurar para o Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="4967a-115">To configure for Visual Studio:</span></span>

1. <span data-ttu-id="4967a-116">Transfira e instale o [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 ou superior com a carga de trabalho de desenvolvimento multiplataforma .NET Core ativada.</span><span class="sxs-lookup"><span data-stu-id="4967a-116">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="4967a-117">Transfira e instale o [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="4967a-117">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

### <a name="to-configure-for-another-environment"></a><span data-ttu-id="4967a-118">Para configurar para outro ambiente:</span><span class="sxs-lookup"><span data-stu-id="4967a-118">To configure for another environment:</span></span> 

1. <span data-ttu-id="4967a-119">Introduza o seguinte na linha de comandos</span><span class="sxs-lookup"><span data-stu-id="4967a-119">Enter the following at the command prompt</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

### <a name="to-configure-for-visual-studio-codespaces"></a><span data-ttu-id="4967a-120">Para configurar para o Visual Studio Codespaces:</span><span class="sxs-lookup"><span data-stu-id="4967a-120">To configure for Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="4967a-121">Crie uma [conta do Azure](https://azure.microsoft.com/free/).</span><span class="sxs-lookup"><span data-stu-id="4967a-121">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="4967a-122">Crie um ambiente do Codespaces.</span><span class="sxs-lookup"><span data-stu-id="4967a-122">Create a Codespaces environment.</span></span> <span data-ttu-id="4967a-123">Siga o [guia de início rápido](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span><span class="sxs-lookup"><span data-stu-id="4967a-123">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span></span> <span data-ttu-id="4967a-124">Ao criar o Codespace, recomendamos que introduza `microsoft/Quantum` no campo "Git Repository" (Repositório do Git) para carregar as definições específicas do QDK.</span><span class="sxs-lookup"><span data-stu-id="4967a-124">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="4967a-125">Pode agora iniciar o seu novo ambiente e começar a desenvolver no browser através do [IDE da Cloud do VS Codespaces](https://online.visualstudio.com/environments).</span><span class="sxs-lookup"><span data-stu-id="4967a-125">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="4967a-126">Pode, em alternativa, utilizar a instalação local do VS Code e utilizar o Codespaces como [ambiente remoto](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span><span class="sxs-lookup"><span data-stu-id="4967a-126">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>

## <a name="develop-with-no-locq"></a><span data-ttu-id="4967a-127">Programar com Q#</span><span class="sxs-lookup"><span data-stu-id="4967a-127">Develop with Q#</span></span>

<span data-ttu-id="4967a-128">Siga as instruções no separador correspondente ao seu ambiente de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="4967a-128">Follow the instructions on the tab corresponding to your development environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="4967a-129">Código VS</span><span class="sxs-lookup"><span data-stu-id="4967a-129">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="4967a-130">Para criar um novo projeto:</span><span class="sxs-lookup"><span data-stu-id="4967a-130">To create a new project:</span></span>

1. <span data-ttu-id="4967a-131">Clique em **View** (Ver)  -> **Command Palette** (Paleta de Comandos) e selecione **Q#: Create New Project** (Criar Novo Projeto).</span><span class="sxs-lookup"><span data-stu-id="4967a-131">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="4967a-132">Clique em **Standalone console application** (Aplicação de consola autónoma).</span><span class="sxs-lookup"><span data-stu-id="4967a-132">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="4967a-133">Navegue até à localização para guardar o projeto.</span><span class="sxs-lookup"><span data-stu-id="4967a-133">Navigate to the location to save the project.</span></span> <span data-ttu-id="4967a-134">Introduza o nome do projeto e clique em **Criar Projeto**.</span><span class="sxs-lookup"><span data-stu-id="4967a-134">Enter the project name and click **Create Project**.</span></span>
4. <span data-ttu-id="4967a-135">Após a criação do projeto, clique em **Open new project...** (Abrir novo projeto...) no canto inferior direito.</span><span class="sxs-lookup"><span data-stu-id="4967a-135">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="4967a-136">Inspecione o projeto.</span><span class="sxs-lookup"><span data-stu-id="4967a-136">Inspect the project.</span></span> <span data-ttu-id="4967a-137">Deverá ver um ficheiro de origem com o nome `Program.qs`, que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola.</span><span class="sxs-lookup"><span data-stu-id="4967a-137">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="4967a-138">Para executar a aplicação:</span><span class="sxs-lookup"><span data-stu-id="4967a-138">To run the application:</span></span>

1. <span data-ttu-id="4967a-139">Clique em **Terminal** (Terminal) -> **New Terminal** (Novo Terminal).</span><span class="sxs-lookup"><span data-stu-id="4967a-139">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="4967a-140">Na mensagem do terminal, introduza `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="4967a-140">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="4967a-141">Deverá ver o seguinte texto na janela de saída `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="4967a-141">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> <span data-ttu-id="4967a-142">As áreas de trabalho com várias pastas raiz não são atualmente suportadas pela extensão Q# do Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="4967a-142">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="4967a-143">Se tiver vários projetos numa área de trabalho do VS Code, todos os projetos terão de estar na mesma pasta raiz.</span><span class="sxs-lookup"><span data-stu-id="4967a-143">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="4967a-144">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4967a-144">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="4967a-145">Crie uma aplicação `Hello World` Q# para verificar a instalação do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4967a-145">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="4967a-146">Para criar uma aplicação Q# nova:</span><span class="sxs-lookup"><span data-stu-id="4967a-146">To create a new Q# application:</span></span>

1. <span data-ttu-id="4967a-147">Abra o Visual Studio e clique em **File** (Ficheiro)  -> **New** (Novo)  -> **Project** (Projeto).</span><span class="sxs-lookup"><span data-stu-id="4967a-147">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="4967a-148">Escreva `Q#` na caixa de pesquisa, selecione **Q# Application (Aplicação Q#)**  e clique em **Next** (Seguinte).</span><span class="sxs-lookup"><span data-stu-id="4967a-148">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="4967a-149">Introduza um nome e uma localização para a aplicação e clique em **Create** (Criar).</span><span class="sxs-lookup"><span data-stu-id="4967a-149">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="4967a-150">Inspecione o projeto.</span><span class="sxs-lookup"><span data-stu-id="4967a-150">Inspect the project.</span></span> <span data-ttu-id="4967a-151">Deverá ver um ficheiro de origem com o nome `Program.qs`, que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola.</span><span class="sxs-lookup"><span data-stu-id="4967a-151">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="4967a-152">Para executar a aplicação:</span><span class="sxs-lookup"><span data-stu-id="4967a-152">To run the application:</span></span>

1. <span data-ttu-id="4967a-153">Selecione **Debug** (Depurar)  -> **Start Without Debugging** (Iniciar Sem Depuração).</span><span class="sxs-lookup"><span data-stu-id="4967a-153">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="4967a-154">Deverá ver o texto `Hello quantum world!` impresso numa janela da consola.</span><span class="sxs-lookup"><span data-stu-id="4967a-154">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="4967a-155">Se tiver vários projetos numa solução do Visual Studio, todos os projetos contidos na solução têm de estar na mesma pasta que a solução ou numa das subpastas.</span><span class="sxs-lookup"><span data-stu-id="4967a-155">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-prompt"></a>[<span data-ttu-id="4967a-156">Outros editores com a linha de comandos</span><span class="sxs-lookup"><span data-stu-id="4967a-156">Other editors with the command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="4967a-157">Crie uma aplicação `Hello World` Q# para verificar a sua instalação.</span><span class="sxs-lookup"><span data-stu-id="4967a-157">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="4967a-158">Crie uma nova aplicação:</span><span class="sxs-lookup"><span data-stu-id="4967a-158">Create a new application:</span></span>

    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. <span data-ttu-id="4967a-159">Navegue para o diretório da aplicação:</span><span class="sxs-lookup"><span data-stu-id="4967a-159">Navigate to the application directory:</span></span>

    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="4967a-160">Este diretório deverá conter um ficheiro `Program.qs`, que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola.</span><span class="sxs-lookup"><span data-stu-id="4967a-160">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="4967a-161">Pode modificar este modelo com um editor de texto e substituí-lo pelas suas próprias aplicações quânticas.</span><span class="sxs-lookup"><span data-stu-id="4967a-161">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="4967a-162">Execute o programa:</span><span class="sxs-lookup"><span data-stu-id="4967a-162">Run the program:</span></span>

    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="4967a-163">Deverá ver o seguinte texto impresso: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="4967a-163">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="4967a-164">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="4967a-164">Next steps</span></span>

<span data-ttu-id="4967a-165">Agora que instalou o Quantum Development Kit no ambiente pretendido, pode escrever e executar [o primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="4967a-165">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
