---
title: Execute programas Q# sem condutor e uma língua anfitriã
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e83acaf10af952da06abf4737ad2ec91f1cf1b8e
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/01/2020
ms.locfileid: "82706806"
---
# <a name="q-command-line-applications"></a><span data-ttu-id="205fa-102">Q# Aplicações da Linha de Comando</span><span class="sxs-lookup"><span data-stu-id="205fa-102">Q# Command Line Applications</span></span>

<span data-ttu-id="205fa-103">Os programas Q# podem ser executados por conta própria, sem um condutor numa língua anfitriã como C#, F#, ou Python.</span><span class="sxs-lookup"><span data-stu-id="205fa-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="205fa-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="205fa-104">Pre-requisites</span></span>

- [<span data-ttu-id="205fa-105">.NET Core SDK 3.1 ou posterior</span><span class="sxs-lookup"><span data-stu-id="205fa-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="205fa-106">Instalação</span><span class="sxs-lookup"><span data-stu-id="205fa-106">Installation</span></span>

<span data-ttu-id="205fa-107">Embora possa construir aplicações de linha de comando Q# em qualquer IDE, recomendamos vivamente a utilização de Código de Estúdio Visual (Código VS) ou Estúdio Visual IDE para as suas aplicações Q#.</span><span class="sxs-lookup"><span data-stu-id="205fa-107">While you can build Q# command line applications in any IDE, we highly recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="205fa-108">Ao utilizar o VS Code ou o Visual Studio e a extensão qDK Visual Studio Code, você tem acesso a funcionalidades mais ricas.</span><span class="sxs-lookup"><span data-stu-id="205fa-108">By using VS Code or Visual Studio and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

- <span data-ttu-id="205fa-109">Instalar [código VS](https://code.visualstudio.com/download) (Windows, Linux e Mac)</span><span class="sxs-lookup"><span data-stu-id="205fa-109">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
- <span data-ttu-id="205fa-110">Instale a [extensão QDK para o Código VS](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) OU</span><span class="sxs-lookup"><span data-stu-id="205fa-110">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) OR</span></span>
- <span data-ttu-id="205fa-111">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, com a carga de trabalho de desenvolvimento para várias plataformas .NET Core ativada</span><span class="sxs-lookup"><span data-stu-id="205fa-111">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>
- <span data-ttu-id="205fa-112">Descarregue e instale a [extensão do Estúdio Visual](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="205fa-112">Download and install the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="205fa-113">Desenvolver com Q# usando o Código VS</span><span class="sxs-lookup"><span data-stu-id="205fa-113">Develop with Q# using VS Code</span></span>

<span data-ttu-id="205fa-114">Instalar os modelos de projeto Quantum:</span><span class="sxs-lookup"><span data-stu-id="205fa-114">Install the Quantum project templates:</span></span>

- <span data-ttu-id="205fa-115">Ir **ver** -> **paleta** de comando</span><span class="sxs-lookup"><span data-stu-id="205fa-115">Go to **View** -> **Command Palette**</span></span>
- <span data-ttu-id="205fa-116">Selecione **Q#: Instale modelos de projeto**</span><span class="sxs-lookup"><span data-stu-id="205fa-116">Select **Q#: Install project templates**</span></span>

<span data-ttu-id="205fa-117">Agora, tem o Quantum Development Kit instalado e pronto para utilizar nas aplicações e bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="205fa-117">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>
- <span data-ttu-id="205fa-118">Crie um novo projeto:</span><span class="sxs-lookup"><span data-stu-id="205fa-118">Create a new project:</span></span>
  - <span data-ttu-id="205fa-119">Ir **ver** -> **paleta** de comando</span><span class="sxs-lookup"><span data-stu-id="205fa-119">Go to **View** -> **Command Palette**</span></span>
  - <span data-ttu-id="205fa-120">Selecione **Q#: Criar novo projeto**</span><span class="sxs-lookup"><span data-stu-id="205fa-120">Select **Q#: Create New Project**</span></span>
  - <span data-ttu-id="205fa-121">Selecione **aplicação** de consola autónoma</span><span class="sxs-lookup"><span data-stu-id="205fa-121">Select **Standalone console application**</span></span>
  - <span data-ttu-id="205fa-122">Navegue para a localização no sistema de ficheiros onde quer criar a aplicação</span><span class="sxs-lookup"><span data-stu-id="205fa-122">Navigate to the location on the file system where you would like to create the application</span></span>
  - <span data-ttu-id="205fa-123">Clique no botão **Abrir novo projeto...**, após o projeto ser criado.</span><span class="sxs-lookup"><span data-stu-id="205fa-123">Click on the **Open new project...** button, once the project has been created</span></span>
        
- <span data-ttu-id="205fa-124">Inspecione o projeto</span><span class="sxs-lookup"><span data-stu-id="205fa-124">Inspect the project</span></span>
  - <span data-ttu-id="205fa-125">Deve ver que um `Program.qs` ficheiro chamado criado, que é um programa Q# que define uma simples operação para imprimir uma mensagem para a consola.</span><span class="sxs-lookup"><span data-stu-id="205fa-125">You should see that a file called `Program.qs` created, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

- <span data-ttu-id="205fa-126">Execute a aplicação:</span><span class="sxs-lookup"><span data-stu-id="205fa-126">Run the application:</span></span>
  - <span data-ttu-id="205fa-127">Ir para **terminal** -> **novo terminal novo**</span><span class="sxs-lookup"><span data-stu-id="205fa-127">Go to **Terminal** -> **New Terminal**</span></span>
  - <span data-ttu-id="205fa-128">Entrar`dotnet run`</span><span class="sxs-lookup"><span data-stu-id="205fa-128">Enter `dotnet run`</span></span>
  - <span data-ttu-id="205fa-129">Deverá ver o seguinte texto na janela de saída `Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="205fa-129">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> * <span data-ttu-id="205fa-130">As áreas de trabalho com várias pastas raiz não são atualmente suportadas pela extensão do Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="205fa-130">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="205fa-131">Se tiver vários projetos numa área de trabalho do VS Code, todos os projetos terão de estar na mesma pasta raiz.</span><span class="sxs-lookup"><span data-stu-id="205fa-131">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="205fa-132">Desenvolver com Q# usando o Estúdio Visual</span><span class="sxs-lookup"><span data-stu-id="205fa-132">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="205fa-133">Verificar a instalação ao criar uma aplicação `Hello World`</span><span class="sxs-lookup"><span data-stu-id="205fa-133">Verify the installation by creating a `Hello World` application</span></span>

- <span data-ttu-id="205fa-134">Crie uma nova aplicação Q#</span><span class="sxs-lookup"><span data-stu-id="205fa-134">Create a new Q# application</span></span>
  - <span data-ttu-id="205fa-135">Ir para **Arquivar** -> **Novo** -> **Projeto**</span><span class="sxs-lookup"><span data-stu-id="205fa-135">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="205fa-136">Escreva `Q#` na caixa de pesquisa</span><span class="sxs-lookup"><span data-stu-id="205fa-136">Type `Q#` in the search box</span></span>
  - <span data-ttu-id="205fa-137">Selecione **Aplicação Q#**</span><span class="sxs-lookup"><span data-stu-id="205fa-137">Select **Q# Application**</span></span>
  - <span data-ttu-id="205fa-138">Selecione **Next**</span><span class="sxs-lookup"><span data-stu-id="205fa-138">Select **Next**</span></span>
  - <span data-ttu-id="205fa-139">Escolha um nome e uma localização para a aplicação</span><span class="sxs-lookup"><span data-stu-id="205fa-139">Choose a name and location for your application</span></span>
  - <span data-ttu-id="205fa-140">Selecione **Criar**</span><span class="sxs-lookup"><span data-stu-id="205fa-140">Select **Create**</span></span>

- <span data-ttu-id="205fa-141">Inspecione o projeto</span><span class="sxs-lookup"><span data-stu-id="205fa-141">Inspect the project</span></span>
  - <span data-ttu-id="205fa-142">Deve ver que foi `Program.qs` criado um ficheiro chamado, que é um programa Q# que define uma simples operação para imprimir uma mensagem para a consola.</span><span class="sxs-lookup"><span data-stu-id="205fa-142">You should see that a file called `Program.qs` has been created, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

- <span data-ttu-id="205fa-143">Executar a aplicação</span><span class="sxs-lookup"><span data-stu-id="205fa-143">Run the application</span></span>
  - <span data-ttu-id="205fa-144">Selecione **Debug** -> **Start Without Debugging**</span><span class="sxs-lookup"><span data-stu-id="205fa-144">Select **Debug** -> **Start Without Debugging**</span></span>
  - <span data-ttu-id="205fa-145">Deverá ver o texto `Hello quantum world!` impresso numa janela da consola.</span><span class="sxs-lookup"><span data-stu-id="205fa-145">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="205fa-146">Se tiver vários projetos numa solução do Visual Studio, todos os projetos contidos na solução têm de estar na mesma pasta que a solução ou numa das suas subpastas.</span><span class="sxs-lookup"><span data-stu-id="205fa-146">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  


## <a name="whats-next"></a><span data-ttu-id="205fa-147">Passos seguintes?</span><span class="sxs-lookup"><span data-stu-id="205fa-147">What's next?</span></span>

<span data-ttu-id="205fa-148">Agora que instalou o Quantum Development Kit no ambiente pretendido, pode escrever e executar [o primeiro programa quântico](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="205fa-148">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
