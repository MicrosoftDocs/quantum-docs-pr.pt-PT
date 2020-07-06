---
title: Programar com aplicações de linha de comandos Q#
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 15015d1673f47faf5a13dde516f834916b4319d6
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884276"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="cb0b0-102">Programar com aplicações de linha de comandos Q#</span><span class="sxs-lookup"><span data-stu-id="cb0b0-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="cb0b0-103">Os programas Q# podem ser executados sozinhos, sem um controlador numa linguagem anfitriã, como C#, F# ou Python.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cb0b0-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="cb0b0-104">Prerequisites</span></span>

- [<span data-ttu-id="cb0b0-105">SDK de .NET Core 3.1 ou versão posterior</span><span class="sxs-lookup"><span data-stu-id="cb0b0-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="cb0b0-106">Instalação</span><span class="sxs-lookup"><span data-stu-id="cb0b0-106">Installation</span></span>

<span data-ttu-id="cb0b0-107">Embora possa compilar aplicações de linha de comandos Q# em qualquer IDE, recomendamos utilizar o Visual Studio Code (VS Code) ou o Visual Studio IDE para as suas aplicações Q#.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="cb0b0-108">O desenvolvimento nestes ambientes inclui a funcionalidade avançada da extensão QDK, que inclui avisos, realce de sintaxe, modelos de projeto e muito mais.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-108">Developing in these environments includes the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span>

<span data-ttu-id="cb0b0-109">Para configurar o VS Code:</span><span class="sxs-lookup"><span data-stu-id="cb0b0-109">To configure VS Code:</span></span>

1. <span data-ttu-id="cb0b0-110">Transfira e instale o [VS Code](https://code.visualstudio.com/download) (Windows, Linux e Mac).</span><span class="sxs-lookup"><span data-stu-id="cb0b0-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="cb0b0-111">Instale o [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="cb0b0-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="cb0b0-112">Para configurar o Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="cb0b0-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="cb0b0-113">Transfira e instale o [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 ou superior com a carga de trabalho de desenvolvimento multiplataforma .NET Core ativada.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="cb0b0-114">Transfira e instale o [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="cb0b0-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

<span data-ttu-id="cb0b0-115">Para instalar o QDK para outro ambiente, introduza na linha de comandos:</span><span class="sxs-lookup"><span data-stu-id="cb0b0-115">To install the QDK for another environment, enter in the command line:</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-q"></a><span data-ttu-id="cb0b0-116">Programar com Q#</span><span class="sxs-lookup"><span data-stu-id="cb0b0-116">Develop with Q#</span></span>

<span data-ttu-id="cb0b0-117">Siga as instruções no separador correspondente ao seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-117">Follow the instructions at the tab corresponding to your environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="cb0b0-118">Código VS</span><span class="sxs-lookup"><span data-stu-id="cb0b0-118">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="cb0b0-119">Instale os modelos de projeto Q#:</span><span class="sxs-lookup"><span data-stu-id="cb0b0-119">Install the Q# project templates:</span></span>

1. <span data-ttu-id="cb0b0-120">Abra o VS Code.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-120">Open VS Code.</span></span>
2. <span data-ttu-id="cb0b0-121">Clique em **View** (Ver)  -> **Command Palette** (Paleta de Comandos).</span><span class="sxs-lookup"><span data-stu-id="cb0b0-121">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="cb0b0-122">Selecione **Q#: Install project templates** (Q#: Instalar modelos de projetos).</span><span class="sxs-lookup"><span data-stu-id="cb0b0-122">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="cb0b0-123">Quando for apresentada a mensagem **Project templates installed successfully** (Modelos de projetos instalados com êxito), o QDK estará pronto para utilização com as suas próprias aplicações e bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-123">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="cb0b0-124">Para criar um novo projeto:</span><span class="sxs-lookup"><span data-stu-id="cb0b0-124">To create a new project:</span></span>

1. <span data-ttu-id="cb0b0-125">Clique em **View** (Ver)  -> **Command Palette** (Paleta de Comandos) e selecione **Q#: Create New Project** (Criar Novo Projeto).</span><span class="sxs-lookup"><span data-stu-id="cb0b0-125">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="cb0b0-126">Clique em **Standalone console application** (Aplicação de consola autónoma).</span><span class="sxs-lookup"><span data-stu-id="cb0b0-126">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="cb0b0-127">Navegue para a localização para guardar o projeto e clique em **Create Project** (Criar Projeto).</span><span class="sxs-lookup"><span data-stu-id="cb0b0-127">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="cb0b0-128">Após a criação do projeto, clique em **Open new project...** (Abrir novo projeto...) no canto inferior direito.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-128">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="cb0b0-129">Inspecione o projeto.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-129">Inspect the project.</span></span> <span data-ttu-id="cb0b0-130">Deverá ver um ficheiro de origem com o nome `Program.qs`, que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-130">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="cb0b0-131">Para executar a aplicação:</span><span class="sxs-lookup"><span data-stu-id="cb0b0-131">To run the application:</span></span>
1. <span data-ttu-id="cb0b0-132">Clique em **Terminal** (Terminal) -> **New Terminal** (Novo Terminal).</span><span class="sxs-lookup"><span data-stu-id="cb0b0-132">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="cb0b0-133">Na mensagem do terminal, introduza `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-133">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="cb0b0-134">Deverá ver o seguinte texto na janela de saída `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="cb0b0-134">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="cb0b0-135">As áreas de trabalho com várias pastas raiz não são atualmente suportadas pela extensão Q# do Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-135">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="cb0b0-136">Se tiver vários projetos numa área de trabalho do VS Code, todos os projetos terão de estar na mesma pasta raiz.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-136">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="cb0b0-137">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cb0b0-137">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="cb0b0-138">Crie uma aplicação `Hello World` Q# para verificar a instalação do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-138">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="cb0b0-139">Para criar uma aplicação Q# nova:</span><span class="sxs-lookup"><span data-stu-id="cb0b0-139">To create a new Q# application:</span></span>
1. <span data-ttu-id="cb0b0-140">Abra o Visual Studio e clique em **File** (Ficheiro)  -> **New** (Novo)  -> **Project** (Projeto).</span><span class="sxs-lookup"><span data-stu-id="cb0b0-140">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="cb0b0-141">Escreva `Q#` na caixa de pesquisa, selecione **Q# Application** (Aplicação Q#) e clique em **Next** (Seguinte).</span><span class="sxs-lookup"><span data-stu-id="cb0b0-141">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="cb0b0-142">Introduza um nome e uma localização para a aplicação e clique em **Create** (Criar).</span><span class="sxs-lookup"><span data-stu-id="cb0b0-142">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="cb0b0-143">Inspecione o projeto.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-143">Inspect the project.</span></span> <span data-ttu-id="cb0b0-144">Deverá ver um ficheiro de origem com o nome `Program.qs`, que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-144">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="cb0b0-145">Para executar a aplicação:</span><span class="sxs-lookup"><span data-stu-id="cb0b0-145">To run the application:</span></span>
1. <span data-ttu-id="cb0b0-146">Selecione **Debug** (Depurar)  -> **Start Without Debugging** (Iniciar Sem Depuração).</span><span class="sxs-lookup"><span data-stu-id="cb0b0-146">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="cb0b0-147">Deverá ver o texto `Hello quantum world!` impresso numa janela da consola.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-147">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="cb0b0-148">Se tiver vários projetos numa solução do Visual Studio, todos os projetos contidos na solução têm de estar na mesma pasta que a solução ou numa das subpastas.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-148">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-line"></a>[<span data-ttu-id="cb0b0-149">Outros editores com a linha de comandos</span><span class="sxs-lookup"><span data-stu-id="cb0b0-149">Other editors with the command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="cb0b0-150">Crie uma aplicação `Hello World` Q# para verificar a sua instalação.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-150">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="cb0b0-151">Crie uma nova aplicação:</span><span class="sxs-lookup"><span data-stu-id="cb0b0-151">Create a new application:</span></span>
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

2. <span data-ttu-id="cb0b0-152">Navegue para o diretório da aplicação:</span><span class="sxs-lookup"><span data-stu-id="cb0b0-152">Navigate to the application directory:</span></span>
    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="cb0b0-153">Este diretório deverá conter um ficheiro `Program.qs`, que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-153">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="cb0b0-154">Pode modificar este modelo com um editor de texto e substituí-lo pelas suas próprias aplicações quânticas.</span><span class="sxs-lookup"><span data-stu-id="cb0b0-154">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

3. <span data-ttu-id="cb0b0-155">Execute o programa:</span><span class="sxs-lookup"><span data-stu-id="cb0b0-155">Run the program:</span></span>
    ```dotnetcli
    dotnet run
    ```

4. <span data-ttu-id="cb0b0-156">Deverá ver o seguinte texto impresso: `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="cb0b0-156">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="cb0b0-157">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="cb0b0-157">Next steps</span></span>

<span data-ttu-id="cb0b0-158">Agora que instalou o Quantum Development Kit no ambiente pretendido, pode escrever e executar [o primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="cb0b0-158">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
