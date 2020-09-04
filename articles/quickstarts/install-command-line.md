---
title: Desenvolver com aplicações Q#
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: a630b2307f5d95321fb26f480d7a441ddba846fc
ms.sourcegitcommit: d6ac6f4345be0dd68f1bcd944f44b08e7a3cf346
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/02/2020
ms.locfileid: "89358263"
---
# <a name="develop-with-no-locq-applications"></a><span data-ttu-id="02a65-102">Desenvolver com aplicações Q#</span><span class="sxs-lookup"><span data-stu-id="02a65-102">Develop with Q# applications</span></span>

<span data-ttu-id="02a65-103">Os programas Q# podem ser executados sozinhos, sem um controlador numa linguagem anfitriã, como C#, F# ou Python.</span><span class="sxs-lookup"><span data-stu-id="02a65-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="02a65-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="02a65-104">Prerequisites</span></span>

- [<span data-ttu-id="02a65-105">SDK de .NET Core 3.1 ou versão posterior</span><span class="sxs-lookup"><span data-stu-id="02a65-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="02a65-106">Instalação</span><span class="sxs-lookup"><span data-stu-id="02a65-106">Installation</span></span>

<span data-ttu-id="02a65-107">Embora possa criar aplicações Q# em qualquer IDE, recomendamos que utilize o Visual Studio Code (VS Code) ou o IDE do Visual Studio para desenvolver as suas aplicações Q# localmente.</span><span class="sxs-lookup"><span data-stu-id="02a65-107">While you can build Q# applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your Q# applications locally.</span></span> <span data-ttu-id="02a65-108">Para desenvolver na Cloud através do browser, recomendamos o Visual Studio Codespaces.</span><span class="sxs-lookup"><span data-stu-id="02a65-108">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="02a65-109">O desenvolvimento nestes ambientes inclui a funcionalidade avançada da extensão QDK, que inclui avisos, realce de sintaxe, modelos de projeto e muito mais.</span><span class="sxs-lookup"><span data-stu-id="02a65-109">Developing in these environments includes the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

<span data-ttu-id="02a65-110">Para configurar o VS Code:</span><span class="sxs-lookup"><span data-stu-id="02a65-110">To configure VS Code:</span></span>

1. <span data-ttu-id="02a65-111">Transfira e instale o [VS Code](https://code.visualstudio.com/download) (Windows, Linux e Mac).</span><span class="sxs-lookup"><span data-stu-id="02a65-111">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="02a65-112">Instale o [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="02a65-112">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="02a65-113">Para configurar o Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="02a65-113">To configure Visual Studio:</span></span>

1. <span data-ttu-id="02a65-114">Transfira e instale o [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 ou superior com a carga de trabalho de desenvolvimento multiplataforma .NET Core ativada.</span><span class="sxs-lookup"><span data-stu-id="02a65-114">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="02a65-115">Transfira e instale o [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="02a65-115">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

<span data-ttu-id="02a65-116">Para configurar o Visual Studio Codespaces:</span><span class="sxs-lookup"><span data-stu-id="02a65-116">To configure Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="02a65-117">Crie uma [conta do Azure](https://azure.microsoft.com/free/).</span><span class="sxs-lookup"><span data-stu-id="02a65-117">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="02a65-118">Crie um ambiente do Codespaces.</span><span class="sxs-lookup"><span data-stu-id="02a65-118">Create a Codespaces environment.</span></span> <span data-ttu-id="02a65-119">Siga o [guia de início rápido](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span><span class="sxs-lookup"><span data-stu-id="02a65-119">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span></span> <span data-ttu-id="02a65-120">Ao criar o Codespace, recomendamos que introduza `microsoft/Quantum` no campo "Git Repository" (Repositório do Git) para carregar as definições específicas do QDK.</span><span class="sxs-lookup"><span data-stu-id="02a65-120">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="02a65-121">Pode agora iniciar o seu novo ambiente e começar a desenvolver no browser através do [IDE da Cloud do VS Codespaces](https://online.visualstudio.com/environments).</span><span class="sxs-lookup"><span data-stu-id="02a65-121">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="02a65-122">Pode, em alternativa, utilizar a instalação local do VS Code e utilizar o Codespaces como [ambiente remoto](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span><span class="sxs-lookup"><span data-stu-id="02a65-122">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>


<span data-ttu-id="02a65-123">Para instalar o QDK para outro ambiente, introduza na linha de comandos:</span><span class="sxs-lookup"><span data-stu-id="02a65-123">To install the QDK for another environment, enter at the command prompt:</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-no-locq"></a><span data-ttu-id="02a65-124">Programar com Q#</span><span class="sxs-lookup"><span data-stu-id="02a65-124">Develop with Q#</span></span>

<span data-ttu-id="02a65-125">Siga as instruções no separador correspondente ao seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="02a65-125">Follow the instructions at the tab corresponding to your environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="02a65-126">Código VS</span><span class="sxs-lookup"><span data-stu-id="02a65-126">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="02a65-127">Para criar um novo projeto:</span><span class="sxs-lookup"><span data-stu-id="02a65-127">To create a new project:</span></span>

1. <span data-ttu-id="02a65-128">Clique em **View** (Ver)  -> **Command Palette** (Paleta de Comandos) e selecione **Q#: Create New Project** (Criar Novo Projeto).</span><span class="sxs-lookup"><span data-stu-id="02a65-128">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="02a65-129">Clique em **Standalone console application** (Aplicação de consola autónoma).</span><span class="sxs-lookup"><span data-stu-id="02a65-129">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="02a65-130">Navegue para a localização para guardar o projeto e clique em **Create Project** (Criar Projeto).</span><span class="sxs-lookup"><span data-stu-id="02a65-130">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="02a65-131">Após a criação do projeto, clique em **Open new project...** (Abrir novo projeto...) no canto inferior direito.</span><span class="sxs-lookup"><span data-stu-id="02a65-131">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="02a65-132">Inspecione o projeto.</span><span class="sxs-lookup"><span data-stu-id="02a65-132">Inspect the project.</span></span> <span data-ttu-id="02a65-133">Deverá ver um ficheiro de origem com o nome `Program.qs`, que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola.</span><span class="sxs-lookup"><span data-stu-id="02a65-133">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="02a65-134">Para executar a aplicação:</span><span class="sxs-lookup"><span data-stu-id="02a65-134">To run the application:</span></span>
1. <span data-ttu-id="02a65-135">Clique em **Terminal** (Terminal) -> **New Terminal** (Novo Terminal).</span><span class="sxs-lookup"><span data-stu-id="02a65-135">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="02a65-136">Na mensagem do terminal, introduza `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="02a65-136">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="02a65-137">Deverá ver o seguinte texto na janela de saída `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="02a65-137">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="02a65-138">As áreas de trabalho com várias pastas raiz não são atualmente suportadas pela extensão Q# do Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="02a65-138">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="02a65-139">Se tiver vários projetos numa área de trabalho do VS Code, todos os projetos terão de estar na mesma pasta raiz.</span><span class="sxs-lookup"><span data-stu-id="02a65-139">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="02a65-140">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="02a65-140">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="02a65-141">Crie uma aplicação `Hello World` Q# para verificar a instalação do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="02a65-141">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="02a65-142">Para criar uma aplicação Q# nova:</span><span class="sxs-lookup"><span data-stu-id="02a65-142">To create a new Q# application:</span></span>
1. <span data-ttu-id="02a65-143">Abra o Visual Studio e clique em **File** (Ficheiro)  -> **New** (Novo)  -> **Project** (Projeto).</span><span class="sxs-lookup"><span data-stu-id="02a65-143">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="02a65-144">Escreva `Q#` na caixa de pesquisa, selecione **Q# Application (Aplicação Q#)**  e clique em **Next** (Seguinte).</span><span class="sxs-lookup"><span data-stu-id="02a65-144">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="02a65-145">Introduza um nome e uma localização para a aplicação e clique em **Create** (Criar).</span><span class="sxs-lookup"><span data-stu-id="02a65-145">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="02a65-146">Inspecione o projeto.</span><span class="sxs-lookup"><span data-stu-id="02a65-146">Inspect the project.</span></span> <span data-ttu-id="02a65-147">Deverá ver um ficheiro de origem com o nome `Program.qs`, que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola.</span><span class="sxs-lookup"><span data-stu-id="02a65-147">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="02a65-148">Para executar a aplicação:</span><span class="sxs-lookup"><span data-stu-id="02a65-148">To run the application:</span></span>
1. <span data-ttu-id="02a65-149">Selecione **Debug** (Depurar)  -> **Start Without Debugging** (Iniciar Sem Depuração).</span><span class="sxs-lookup"><span data-stu-id="02a65-149">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="02a65-150">Deverá ver o texto `Hello quantum world!` impresso numa janela da consola.</span><span class="sxs-lookup"><span data-stu-id="02a65-150">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="02a65-151">Se tiver vários projetos numa solução do Visual Studio, todos os projetos contidos na solução têm de estar na mesma pasta que a solução ou numa das subpastas.</span><span class="sxs-lookup"><span data-stu-id="02a65-151">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-prompt"></a>[<span data-ttu-id="02a65-152">Outros editores com a linha de comandos</span><span class="sxs-lookup"><span data-stu-id="02a65-152">Other editors with the command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="02a65-153">Crie uma aplicação `Hello World` Q# para verificar a sua instalação.</span><span class="sxs-lookup"><span data-stu-id="02a65-153">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="02a65-154">Instale os modelos de projeto.</span><span class="sxs-lookup"><span data-stu-id="02a65-154">Install the project templates.</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. <span data-ttu-id="02a65-155">Crie uma nova aplicação:</span><span class="sxs-lookup"><span data-stu-id="02a65-155">Create a new application:</span></span>
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. <span data-ttu-id="02a65-156">Navegue para o diretório da aplicação:</span><span class="sxs-lookup"><span data-stu-id="02a65-156">Navigate to the application directory:</span></span>
    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="02a65-157">Este diretório deverá conter um ficheiro `Program.qs`, que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola.</span><span class="sxs-lookup"><span data-stu-id="02a65-157">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="02a65-158">Pode modificar este modelo com um editor de texto e substituí-lo pelas suas próprias aplicações quânticas.</span><span class="sxs-lookup"><span data-stu-id="02a65-158">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="02a65-159">Execute o programa:</span><span class="sxs-lookup"><span data-stu-id="02a65-159">Run the program:</span></span>
    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="02a65-160">Deverá ver o seguinte texto impresso: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="02a65-160">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="02a65-161">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="02a65-161">Next steps</span></span>

<span data-ttu-id="02a65-162">Agora que instalou o Quantum Development Kit no ambiente pretendido, pode escrever e executar [o primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="02a65-162">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
