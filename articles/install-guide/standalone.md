---
title: Desenvolver com aplicações de linha de comando Q#
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 4311ebf9f72254485a20ba721ea2ce19163f4371
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630267"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="42abe-102">Desenvolver com aplicações de linha de comando Q#</span><span class="sxs-lookup"><span data-stu-id="42abe-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="42abe-103">Os programas Q# podem ser executados por si mesmos, sem um condutor numa língua hospedeira como C#, F#ou Python.</span><span class="sxs-lookup"><span data-stu-id="42abe-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="42abe-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="42abe-104">Prerequisites</span></span>

- [<span data-ttu-id="42abe-105">.NET Core SDK 3.1 ou mais tarde</span><span class="sxs-lookup"><span data-stu-id="42abe-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="42abe-106">Instalação</span><span class="sxs-lookup"><span data-stu-id="42abe-106">Installation</span></span>

<span data-ttu-id="42abe-107">Enquanto pode construir aplicações de linha de comando Q# em qualquer IDE, recomendamos a utilização do Código de Estúdio Visual (CÓDIGO VS) ou do Visual Studio IDE para as suas aplicações Q#.</span><span class="sxs-lookup"><span data-stu-id="42abe-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="42abe-108">O desenvolvimento nestas ferramentas proporciona acesso a uma funcionalidade rica.</span><span class="sxs-lookup"><span data-stu-id="42abe-108">Developing in these tools provides access to rich functionality.</span></span>

<span data-ttu-id="42abe-109">Para configurar o Código VS:</span><span class="sxs-lookup"><span data-stu-id="42abe-109">To configure VS Code:</span></span>

1. <span data-ttu-id="42abe-110">Descarregue e instale [o Código VS](https://code.visualstudio.com/download) (Windows, Linux e Mac).</span><span class="sxs-lookup"><span data-stu-id="42abe-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="42abe-111">Instale o [Microsoft QDK para o Código VS](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="42abe-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="42abe-112">Para configurar o Estúdio Visual:</span><span class="sxs-lookup"><span data-stu-id="42abe-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="42abe-113">Descarregue e instale [o Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 ou superior, com a carga de trabalho de desenvolvimento de plataformas cruzadas .NET Core ativada.</span><span class="sxs-lookup"><span data-stu-id="42abe-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="42abe-114">Faça o download e instale o [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span><span class="sxs-lookup"><span data-stu-id="42abe-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="42abe-115">Desenvolver com Q# usando o Código VS</span><span class="sxs-lookup"><span data-stu-id="42abe-115">Develop with Q# using VS Code</span></span>

<span data-ttu-id="42abe-116">Instale os modelos de projeto Q#:</span><span class="sxs-lookup"><span data-stu-id="42abe-116">Install the Q# project templates:</span></span>

1. <span data-ttu-id="42abe-117">Abrir código VS.</span><span class="sxs-lookup"><span data-stu-id="42abe-117">Open VS Code.</span></span>
2. <span data-ttu-id="42abe-118">Clique **na**  ->  **paleta de comando ver.**</span><span class="sxs-lookup"><span data-stu-id="42abe-118">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="42abe-119">Selecione **Q#: Instale modelos de projetos**.</span><span class="sxs-lookup"><span data-stu-id="42abe-119">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="42abe-120">Quando **os modelos do Projeto instalados com sucesso** forem apresentados com sucesso, o QDK está pronto a ser utilizado com as suas próprias aplicações e bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="42abe-120">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="42abe-121">Para criar um novo projeto:</span><span class="sxs-lookup"><span data-stu-id="42abe-121">To create a new project:</span></span>

1. <span data-ttu-id="42abe-122">Clique **em Ver Paleta**de  ->  **Comando** e selecione **Q#: Criar novo projeto**.</span><span class="sxs-lookup"><span data-stu-id="42abe-122">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="42abe-123">Clique **na aplicação de consola autónoma**.</span><span class="sxs-lookup"><span data-stu-id="42abe-123">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="42abe-124">Navegue até ao local para salvar o projeto e clique em **Criar Projeto.**</span><span class="sxs-lookup"><span data-stu-id="42abe-124">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="42abe-125">Quando o projeto for criado com sucesso, clique em **Abrir novo projeto...** no direito inferior.</span><span class="sxs-lookup"><span data-stu-id="42abe-125">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="42abe-126">Inspecionar o projeto.</span><span class="sxs-lookup"><span data-stu-id="42abe-126">Inspect the project.</span></span> <span data-ttu-id="42abe-127">Deve ver um ficheiro de origem chamado `Program.qs` , que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola.</span><span class="sxs-lookup"><span data-stu-id="42abe-127">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="42abe-128">Para executar a aplicação:</span><span class="sxs-lookup"><span data-stu-id="42abe-128">To run the application:</span></span>
1. <span data-ttu-id="42abe-129">Clique **em Terminal**Novo  ->  **Terminal**.</span><span class="sxs-lookup"><span data-stu-id="42abe-129">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="42abe-130">Na solicitação do terminal, `dotnet run` entre.</span><span class="sxs-lookup"><span data-stu-id="42abe-130">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="42abe-131">Deverá ver o seguinte texto na janela de saída `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="42abe-131">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="42abe-132">Os espaços de trabalho com várias pastas de raiz não são atualmente suportados pela extensão VS Code Q#.</span><span class="sxs-lookup"><span data-stu-id="42abe-132">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="42abe-133">Se tiver vários projetos numa área de trabalho do VS Code, todos os projetos terão de estar na mesma pasta raiz.</span><span class="sxs-lookup"><span data-stu-id="42abe-133">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="42abe-134">Desenvolver com Q# usando Visual Studio</span><span class="sxs-lookup"><span data-stu-id="42abe-134">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="42abe-135">Verifique a instalação do Visual Studio criando uma `Hello World` aplicação Q#.</span><span class="sxs-lookup"><span data-stu-id="42abe-135">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="42abe-136">Para criar uma nova aplicação Q#:</span><span class="sxs-lookup"><span data-stu-id="42abe-136">To create a new Q# application:</span></span>
1. <span data-ttu-id="42abe-137">Abra o Estúdio Visual e clique em **File**  ->  **New**  ->  **Project**.</span><span class="sxs-lookup"><span data-stu-id="42abe-137">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="42abe-138">Digite `Q#` a caixa de pesquisa, selecione **Q# Aplicação** e clique em **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="42abe-138">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="42abe-139">Introduza um nome e localização para a sua aplicação e clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="42abe-139">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="42abe-140">Inspecionar o projeto.</span><span class="sxs-lookup"><span data-stu-id="42abe-140">Inspect the project.</span></span> <span data-ttu-id="42abe-141">Deve ver um ficheiro de origem chamado `Program.qs` , que é um programa Q# que define uma operação simples para imprimir uma mensagem na consola.</span><span class="sxs-lookup"><span data-stu-id="42abe-141">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="42abe-142">Para executar a aplicação:</span><span class="sxs-lookup"><span data-stu-id="42abe-142">To run the application:</span></span>
1. <span data-ttu-id="42abe-143">Selecione **Debug**  ->  **Start Without Debugging**.</span><span class="sxs-lookup"><span data-stu-id="42abe-143">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="42abe-144">Deverá ver o texto `Hello quantum world!` impresso numa janela da consola.</span><span class="sxs-lookup"><span data-stu-id="42abe-144">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="42abe-145">Se tiver vários projetos dentro de uma solução Visual Studio, todos os projetos contidos na solução precisam estar na mesma pasta que a solução, ou numa das suas sub-pastas.</span><span class="sxs-lookup"><span data-stu-id="42abe-145">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  


## <a name="next-steps"></a><span data-ttu-id="42abe-146">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="42abe-146">Next steps</span></span>

<span data-ttu-id="42abe-147">Agora que instalou o Quantum Development Kit no ambiente pretendido, pode escrever e executar [o primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="42abe-147">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
