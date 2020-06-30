---
title: Programar com aplicações de linha de comandos Q#
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 4311ebf9f72254485a20ba721ea2ce19163f4371
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274191"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="e710c-102">Programar com aplicações de linha de comandos Q#</span><span class="sxs-lookup"><span data-stu-id="e710c-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="e710c-103">Os programas Q# podem ser executados sozinhos, sem um controlador numa linguagem anfitriã, como C#, F# ou Python.</span><span class="sxs-lookup"><span data-stu-id="e710c-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e710c-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="e710c-104">Prerequisites</span></span>

- [<span data-ttu-id="e710c-105">SDK de .NET Core 3.1 ou versão posterior</span><span class="sxs-lookup"><span data-stu-id="e710c-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="e710c-106">Instalação</span><span class="sxs-lookup"><span data-stu-id="e710c-106">Installation</span></span>

<span data-ttu-id="e710c-107">Embora possa compilar aplicações de linha de comandos Q# em qualquer IDE, recomendamos utilizar o Visual Studio Code (VS Code) ou o Visual Studio IDE para as suas aplicações Q#.</span><span class="sxs-lookup"><span data-stu-id="e710c-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="e710c-108">O desenvolvimento com estas ferramentas proporciona acesso a funcionalidades ricas.</span><span class="sxs-lookup"><span data-stu-id="e710c-108">Developing in these tools provides access to rich functionality.</span></span>

<span data-ttu-id="e710c-109">Para configurar o VS Code:</span><span class="sxs-lookup"><span data-stu-id="e710c-109">To configure VS Code:</span></span>

1. <span data-ttu-id="e710c-110">Transfira e instale o [VS Code](https://code.visualstudio.com/download) (Windows, Linux e Mac).</span><span class="sxs-lookup"><span data-stu-id="e710c-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="e710c-111">Instale o [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="e710c-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="e710c-112">Para configurar o Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="e710c-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="e710c-113">Transfira e instale o [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 ou superior com a carga de trabalho de desenvolvimento multiplataforma .NET Core ativada.</span><span class="sxs-lookup"><span data-stu-id="e710c-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="e710c-114">Transfira e instale o [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="e710c-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="e710c-115">Utilizar o VS Code para desenvolver com Q#</span><span class="sxs-lookup"><span data-stu-id="e710c-115">Develop with Q# using VS Code</span></span>

<span data-ttu-id="e710c-116">Instale os modelos de projeto Q#:</span><span class="sxs-lookup"><span data-stu-id="e710c-116">Install the Q# project templates:</span></span>

1. <span data-ttu-id="e710c-117">Abra o VS Code.</span><span class="sxs-lookup"><span data-stu-id="e710c-117">Open VS Code.</span></span>
2. <span data-ttu-id="e710c-118">Clique em **View** (Ver)  -> **Command Palette** (Paleta de Comandos).</span><span class="sxs-lookup"><span data-stu-id="e710c-118">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="e710c-119">Selecione **Q#: Install project templates** (Q#: Instalar modelos de projetos).</span><span class="sxs-lookup"><span data-stu-id="e710c-119">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="e710c-120">Quando for apresentada a mensagem **Project templates installed successfully** (Modelos de projetos instalados com êxito), o QDK estará pronto para utilização com as suas próprias aplicações e bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="e710c-120">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="e710c-121">Para criar um novo projeto:</span><span class="sxs-lookup"><span data-stu-id="e710c-121">To create a new project:</span></span>

1. <span data-ttu-id="e710c-122">Clique em **View** (Ver)  -> **Command Palette** (Paleta de Comandos) e selecione **Q#: Create New Project** (Criar Novo Projeto).</span><span class="sxs-lookup"><span data-stu-id="e710c-122">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="e710c-123">Clique em **Standalone console application** (Aplicação de consola autónoma).</span><span class="sxs-lookup"><span data-stu-id="e710c-123">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="e710c-124">Navegue para a localização para guardar o projeto e clique em **Create Project** (Criar Projeto).</span><span class="sxs-lookup"><span data-stu-id="e710c-124">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="e710c-125">Após a criação do projeto, clique em **Open new project...** (Abrir novo projeto...) no canto inferior direito.</span><span class="sxs-lookup"><span data-stu-id="e710c-125">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="e710c-126">Inspecione o projeto.</span><span class="sxs-lookup"><span data-stu-id="e710c-126">Inspect the project.</span></span> <span data-ttu-id="e710c-127">Deverá ver um ficheiro de origem com o nome `Program.qs`, que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola.</span><span class="sxs-lookup"><span data-stu-id="e710c-127">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="e710c-128">Para executar a aplicação:</span><span class="sxs-lookup"><span data-stu-id="e710c-128">To run the application:</span></span>
1. <span data-ttu-id="e710c-129">Clique em **Terminal** (Terminal) -> **New Terminal** (Novo Terminal).</span><span class="sxs-lookup"><span data-stu-id="e710c-129">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="e710c-130">Na mensagem do terminal, introduza `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="e710c-130">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="e710c-131">Deverá ver o seguinte texto na janela de saída `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="e710c-131">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="e710c-132">As áreas de trabalho com várias pastas raiz não são atualmente suportadas pela extensão Q# do Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="e710c-132">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="e710c-133">Se tiver vários projetos numa área de trabalho do VS Code, todos os projetos terão de estar na mesma pasta raiz.</span><span class="sxs-lookup"><span data-stu-id="e710c-133">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="e710c-134">Utilizar o visual Studio para desenvolver com Q#</span><span class="sxs-lookup"><span data-stu-id="e710c-134">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="e710c-135">Crie uma aplicação `Hello World` Q# para verificar a instalação do Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e710c-135">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="e710c-136">Para criar uma aplicação Q# nova:</span><span class="sxs-lookup"><span data-stu-id="e710c-136">To create a new Q# application:</span></span>
1. <span data-ttu-id="e710c-137">Abra o Visual Studio e clique em **File** (Ficheiro)  -> **New** (Novo)  -> **Project** (Projeto).</span><span class="sxs-lookup"><span data-stu-id="e710c-137">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="e710c-138">Escreva `Q#` na caixa de pesquisa, selecione **Q# Application** (Aplicação Q#) e clique em **Next** (Seguinte).</span><span class="sxs-lookup"><span data-stu-id="e710c-138">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="e710c-139">Introduza um nome e uma localização para a aplicação e clique em **Create** (Criar).</span><span class="sxs-lookup"><span data-stu-id="e710c-139">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="e710c-140">Inspecione o projeto.</span><span class="sxs-lookup"><span data-stu-id="e710c-140">Inspect the project.</span></span> <span data-ttu-id="e710c-141">Deverá ver um ficheiro de origem com o nome `Program.qs`, que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola.</span><span class="sxs-lookup"><span data-stu-id="e710c-141">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="e710c-142">Para executar a aplicação:</span><span class="sxs-lookup"><span data-stu-id="e710c-142">To run the application:</span></span>
1. <span data-ttu-id="e710c-143">Selecione **Debug** (Depurar)  -> **Start Without Debugging** (Iniciar Sem Depuração).</span><span class="sxs-lookup"><span data-stu-id="e710c-143">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="e710c-144">Deverá ver o texto `Hello quantum world!` impresso numa janela da consola.</span><span class="sxs-lookup"><span data-stu-id="e710c-144">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="e710c-145">Se tiver vários projetos numa solução do Visual Studio, todos os projetos contidos na solução têm de estar na mesma pasta que a solução ou numa das subpastas.</span><span class="sxs-lookup"><span data-stu-id="e710c-145">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  


## <a name="next-steps"></a><span data-ttu-id="e710c-146">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="e710c-146">Next steps</span></span>

<span data-ttu-id="e710c-147">Agora que instalou o Quantum Development Kit no ambiente pretendido, pode escrever e executar [o primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="e710c-147">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
