---
title: Saiba como atualizar o Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: fc430a77f88878437e662c5b54507f70f3c6e020
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185856"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="d74a4-102">Atualizar o Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="d74a4-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="d74a4-103">Saiba como atualizar o Microsoft Quantum Development Kit (QDK) para a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="d74a4-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="d74a4-104">Este artigo pressupõe que você já tenha o QDK instalado.</span><span class="sxs-lookup"><span data-stu-id="d74a4-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="d74a4-105">Se você estiver instalando o pela primeira vez, consulte o guia de [instalação](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="d74a4-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="d74a4-106">As etapas de atualização dependem do ambiente de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="d74a4-106">The update steps depend on your development environment.</span></span> <span data-ttu-id="d74a4-107">Escolha seu ambiente nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="d74a4-107">Choose your environment from the following sections.</span></span>

## <a name="python"></a><span data-ttu-id="d74a4-108">Python</span><span class="sxs-lookup"><span data-stu-id="d74a4-108">Python</span></span>

1. <span data-ttu-id="d74a4-109">Atualizar o kernel `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="d74a4-109">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="d74a4-110">Verificar a versão do `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="d74a4-110">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="d74a4-111">Deverá ver o resultado seguinte:</span><span class="sxs-lookup"><span data-stu-id="d74a4-111">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. <span data-ttu-id="d74a4-112">Atualizar o pacote de `qsharp`</span><span class="sxs-lookup"><span data-stu-id="d74a4-112">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="d74a4-113">Verificar a versão do `qsharp`</span><span class="sxs-lookup"><span data-stu-id="d74a4-113">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="d74a4-114">Deverá ver o resultado seguinte:</span><span class="sxs-lookup"><span data-stu-id="d74a4-114">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.9.1909.3002
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. <span data-ttu-id="d74a4-115">Agora você pode usar a versão atualizada do QDK para executar seus programas de Quantum existentes.</span><span class="sxs-lookup"><span data-stu-id="d74a4-115">You can now use the updated QDK version to run your existing quantum programs.</span></span>

## <a name="jupyter-notebooks"></a><span data-ttu-id="d74a4-116">Jupyter Notebooks</span><span class="sxs-lookup"><span data-stu-id="d74a4-116">Jupyter notebooks</span></span>

1. <span data-ttu-id="d74a4-117">Atualizar o kernel `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="d74a4-117">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="d74a4-118">Verificar a versão do `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="d74a4-118">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="d74a4-119">Deverá ver o resultado seguinte:</span><span class="sxs-lookup"><span data-stu-id="d74a4-119">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.9.1909.3002
    Jupyter Core: 1.1.18837.0
    ```

1. <span data-ttu-id="d74a4-120">Agora você pode abrir um bloco de anotações do Jupyter existente e executá-lo com o QDK atualizado.</span><span class="sxs-lookup"><span data-stu-id="d74a4-120">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

## <a name="c-on-windows-using-visual-studio"></a><span data-ttu-id="d74a4-121">C#no Windows, usando o Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d74a4-121">C# on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="d74a4-122">Atualizar a extensão do Q # Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d74a4-122">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="d74a4-123">O Visual Studio solicita que você aceite atualizações para a [extensão Quantum do Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="d74a4-123">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="d74a4-124">Aceitar a atualização</span><span class="sxs-lookup"><span data-stu-id="d74a4-124">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="d74a4-125">Os modelos de projeto são atualizados com a extensão.</span><span class="sxs-lookup"><span data-stu-id="d74a4-125">The project templates are updated with the extension.</span></span> <span data-ttu-id="d74a4-126">Os modelos atualizados se aplicam apenas a projetos recém-criados.</span><span class="sxs-lookup"><span data-stu-id="d74a4-126">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="d74a4-127">O código para seus projetos existentes não é atualizado quando a extensão é atualizada.</span><span class="sxs-lookup"><span data-stu-id="d74a4-127">The code for your existing projects is not updated when the extension is updated.</span></span>

1. <span data-ttu-id="d74a4-128">Atualizar os pacotes QDK</span><span class="sxs-lookup"><span data-stu-id="d74a4-128">Update the QDK packages</span></span>

    - <span data-ttu-id="d74a4-129">Abrir um aplicativo existente</span><span class="sxs-lookup"><span data-stu-id="d74a4-129">Open an existing application</span></span>
    - <span data-ttu-id="d74a4-130">Selecione **dependências** no Gerenciador de soluções</span><span class="sxs-lookup"><span data-stu-id="d74a4-130">Select **Dependencies** in the Solution Explorer</span></span>
    - <span data-ttu-id="d74a4-131">Selecione **gerenciar pacotes NuGet**</span><span class="sxs-lookup"><span data-stu-id="d74a4-131">Select **Manage NuGet Packages**</span></span>
    - <span data-ttu-id="d74a4-132">Atualizar os pacotes do **Microsoft. Quantum** para a versão mais recente</span><span class="sxs-lookup"><span data-stu-id="d74a4-132">Update the **Microsoft.Quantum** packages to the latest version</span></span>

1. <span data-ttu-id="d74a4-133">Agora você pode executar seu aplicativo com o QDK mais recente.</span><span class="sxs-lookup"><span data-stu-id="d74a4-133">You can now run your application with the latest QDK.</span></span>

## <a name="c-using-vs-code"></a><span data-ttu-id="d74a4-134">C#, usando VS Code</span><span class="sxs-lookup"><span data-stu-id="d74a4-134">C#, using VS Code</span></span>

1. <span data-ttu-id="d74a4-135">Atualizar a extensão de VS Code Quantum</span><span class="sxs-lookup"><span data-stu-id="d74a4-135">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="d74a4-136">Reiniciar VS Code</span><span class="sxs-lookup"><span data-stu-id="d74a4-136">Restart VS Code</span></span>
    - <span data-ttu-id="d74a4-137">Navegue até a guia **extensões**</span><span class="sxs-lookup"><span data-stu-id="d74a4-137">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="d74a4-138">Selecione o **Microsoft Quantum Development Kit para Visual Studio Code** extensão</span><span class="sxs-lookup"><span data-stu-id="d74a4-138">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="d74a4-139">Recarregar a extensão</span><span class="sxs-lookup"><span data-stu-id="d74a4-139">Reload the extension</span></span>

1. <span data-ttu-id="d74a4-140">Atualize os modelos de projeto Quantum:</span><span class="sxs-lookup"><span data-stu-id="d74a4-140">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="d74a4-141">Ir para **exibição** -> **paleta de comandos**</span><span class="sxs-lookup"><span data-stu-id="d74a4-141">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="d74a4-142">Selecione **Q #: instalar modelos de projeto**</span><span class="sxs-lookup"><span data-stu-id="d74a4-142">Select **Q#: Install project templates**</span></span>

1. <span data-ttu-id="d74a4-143">Abrir um aplicativo existente no VS Code</span><span class="sxs-lookup"><span data-stu-id="d74a4-143">Open an existing application in VS Code</span></span>

   - <span data-ttu-id="d74a4-144">Editar o arquivo. csproj para adicionar as novas versões de pacote</span><span class="sxs-lookup"><span data-stu-id="d74a4-144">Edit the .csproj file to add the new package versions</span></span>

    ```xml
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.9.1909.3002" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.9.1909.3002" />
    </ItemGroup>
    ```

    <span data-ttu-id="d74a4-145">Se você usar outros pacotes de `Microsoft.Quantum`, atualize-os também.</span><span class="sxs-lookup"><span data-stu-id="d74a4-145">If you use other `Microsoft.Quantum` packages, update these too.</span></span>

1. <span data-ttu-id="d74a4-146">Agora você pode executar seu aplicativo com o QDK atualizado</span><span class="sxs-lookup"><span data-stu-id="d74a4-146">You can now run your application with the updated QDK</span></span>

## <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="d74a4-147">C#, usando a ferramenta de linha de comando `dotnet`</span><span class="sxs-lookup"><span data-stu-id="d74a4-147">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="d74a4-148">Atualizar os modelos de projeto Quantum para .NET</span><span class="sxs-lookup"><span data-stu-id="d74a4-148">Update the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. <span data-ttu-id="d74a4-149">Atualizar e executar um aplicativo existente</span><span class="sxs-lookup"><span data-stu-id="d74a4-149">Update and run an existing application</span></span>

    - <span data-ttu-id="d74a4-150">Atualizar as versões do pacote QDK em seu aplicativo</span><span class="sxs-lookup"><span data-stu-id="d74a4-150">Update the QDK package versions in your application</span></span>

        ```bash
        dotnet add package Microsoft.Quantum.Development.Kit
        dotnet add package Microsoft.Quantum.Standard
        ```

        <span data-ttu-id="d74a4-151">Se seu aplicativo usar qualquer outro pacote de `Microsoft.Quantum`, atualize-o também.</span><span class="sxs-lookup"><span data-stu-id="d74a4-151">If your application uses any other `Microsoft.Quantum` packages, update these too.</span></span>

    - <span data-ttu-id="d74a4-152">Executar a aplicação</span><span class="sxs-lookup"><span data-stu-id="d74a4-152">Run the application</span></span>

        ```bash
        dotnet run
        ```

    - <span data-ttu-id="d74a4-153">Seu aplicativo será executado com as novas versões de pacote</span><span class="sxs-lookup"><span data-stu-id="d74a4-153">Your application will run with the new package versions</span></span>

## <a name="whats-next"></a><span data-ttu-id="d74a4-154">O que se segue?</span><span class="sxs-lookup"><span data-stu-id="d74a4-154">What's next?</span></span>

<span data-ttu-id="d74a4-155">Agora que você atualizou o kit de desenvolvimento Quantum em seu ambiente preferido, você pode continuar a desenvolver e executar seus programas Quantum.</span><span class="sxs-lookup"><span data-stu-id="d74a4-155">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="d74a4-156">Se você ainda não escreveu um programa, você pode começar com [seu primeiro programa Quantum](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="d74a4-156">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
