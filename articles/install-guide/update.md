---
title: Saiba como atualizar o Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: ebf1f15d65a12c921cd3f04e4111d463d1060f8e
ms.sourcegitcommit: c93fea5980d1d46fbda1e7c7153831b9337134bf
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73463292"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="a939a-102">Atualizar o Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="a939a-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="a939a-103">Saiba como atualizar o Microsoft Quantum Development Kit (QDK) para a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="a939a-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="a939a-104">Este artigo pressupõe que você já tenha o QDK instalado.</span><span class="sxs-lookup"><span data-stu-id="a939a-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="a939a-105">Se você estiver instalando o pela primeira vez, consulte o guia de [instalação](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="a939a-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>


## <a name="updating-q-projects"></a><span data-ttu-id="a939a-106">Atualizando projetos de Q #</span><span class="sxs-lookup"><span data-stu-id="a939a-106">Updating Q# Projects</span></span> 

1. <span data-ttu-id="a939a-107">Primeiro, instale a versão mais recente do [SDK do .NET Core 3,0](https://dotnet.microsoft.com/download) e execute o seguinte comando no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="a939a-107">First, install the latest version of the [.NET Core SDK 3.0](https://dotnet.microsoft.com/download) and run the following command in the command prompt:</span></span>
```bash
dotnet --version
```
 <span data-ttu-id="a939a-108">Verifique se a saída é 3.0.100 ou superior e siga as instruções abaixo, dependendo da sua configuração.</span><span class="sxs-lookup"><span data-stu-id="a939a-108">Verify the output is 3.0.100 or higher, then follow the instructions below depending on your setup.</span></span>

### <a name="in-visual-studio"></a><span data-ttu-id="a939a-109">No Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a939a-109">In Visual Studio</span></span>
 
 1. <span data-ttu-id="a939a-110">Atualize para a versão mais recente do Visual Studio 2019, consulte [aqui](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) para obter instruções</span><span class="sxs-lookup"><span data-stu-id="a939a-110">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
 2. <span data-ttu-id="a939a-111">Abra sua solução no Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a939a-111">Open your solution in Visual Studio</span></span>
 3. <span data-ttu-id="a939a-112">No menu, selecione criar > solução de limpeza</span><span class="sxs-lookup"><span data-stu-id="a939a-112">From the menu, select Build > Clean Solution</span></span> 
 4. <span data-ttu-id="a939a-113">[Atualize a estrutura de destino](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework) em cada um dos seus arquivos. csproj para o netcoreapp 3.0 (ou o netstandard 2.1 se for um projeto de biblioteca)</span><span class="sxs-lookup"><span data-stu-id="a939a-113">[Update the target framework](https://docs.microsoft.com/visualstudio/ide/visual-studio-multi-targeting-overview?view=vs-2019#change-the-target-framework) in each of your .csproj files to netcoreapp3.0 (or netstandard2.1 if it is a library project)</span></span>
 5. <span data-ttu-id="a939a-114">Salvar e fechar todos os arquivos em sua solução</span><span class="sxs-lookup"><span data-stu-id="a939a-114">Save and close all files in your solution</span></span>
 6. <span data-ttu-id="a939a-115">Selecione Ferramentas > > de linha de comando Prompt de Comando do Desenvolvedor</span><span class="sxs-lookup"><span data-stu-id="a939a-115">Select Tools > Command Line > Developer Command Prompt</span></span>
 7. <span data-ttu-id="a939a-116">Para cada projeto na solução, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a939a-116">For each project in the solution, run the following command:</span></span>
 ```bash
 dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
 ```
<span data-ttu-id="a939a-117">Se seus projetos usarem outros pacotes do Microsoft. Quantum, execute o comando para eles também.</span><span class="sxs-lookup"><span data-stu-id="a939a-117">If your projects use any other Microsoft.Quantum packages, run the command for these too.</span></span> 
 8. <span data-ttu-id="a939a-118">Feche o prompt de comando e selecione Compilar > Compilar solução ( *não selecione* recompilar solução, pois a recompilação falhará inicialmente)</span><span class="sxs-lookup"><span data-stu-id="a939a-118">Close the command prompt and select Build > Build Solution (do *not* select Rebuild Solution, as rebuilding will initially fail)</span></span>

### <a name="in-visual-studio-code"></a><span data-ttu-id="a939a-119">Em Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a939a-119">In Visual Studio Code</span></span>

1. <span data-ttu-id="a939a-120">Em Visual Studio Code, abra a pasta que contém o projeto a ser atualizado</span><span class="sxs-lookup"><span data-stu-id="a939a-120">In Visual Studio Code, open the folder containing the project to update</span></span>
1. <span data-ttu-id="a939a-121">Selecionar Terminal > novo terminal</span><span class="sxs-lookup"><span data-stu-id="a939a-121">Select Terminal > New Terminal</span></span>
1. <span data-ttu-id="a939a-122">Siga as instruções para atualizar usando a linha de comando</span><span class="sxs-lookup"><span data-stu-id="a939a-122">Follow the instructions for updating using the command line</span></span>

### <a name="using-the-command-line"></a><span data-ttu-id="a939a-123">Usando a linha de comando</span><span class="sxs-lookup"><span data-stu-id="a939a-123">Using the command line</span></span>

1. <span data-ttu-id="a939a-124">Navegue até a pasta que contém o arquivo de projeto</span><span class="sxs-lookup"><span data-stu-id="a939a-124">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="a939a-125">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a939a-125">Run the following command:</span></span>
```bash
dotnet clean [project_name].csproj
```

3. <span data-ttu-id="a939a-126">[Atualize a estrutura de destino](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) em cada um dos seus arquivos. csproj para o netcoreapp 3.0 (ou o netstandard 2.1 se for um projeto de biblioteca)</span><span class="sxs-lookup"><span data-stu-id="a939a-126">[Update the target framework](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks) in each of your .csproj files to netcoreapp3.0 (or netstandard2.1 if it is a library project)</span></span>
4. <span data-ttu-id="a939a-127">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a939a-127">Run the following command:</span></span>
```bash
dotnet add package Microsoft.Quantum.Development.Kit
```
<span data-ttu-id="a939a-128">Se seu projeto usar qualquer outro pacote do Microsoft. Quantum, execute o comando para eles também.</span><span class="sxs-lookup"><span data-stu-id="a939a-128">if your project uses any other Microsoft.Quantum packages, run the command for these too.</span></span>

5. <span data-ttu-id="a939a-129">Salvar e fechar todos os arquivos</span><span class="sxs-lookup"><span data-stu-id="a939a-129">Save and close all files</span></span>
6. <span data-ttu-id="a939a-130">Repita a 1-4 para cada dependência do projeto e, em seguida, navegue de volta para a pasta que contém o projeto principal e execute:</span><span class="sxs-lookup"><span data-stu-id="a939a-130">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>
```bash
dotnet build [project_name].csproj
```

## <a name="update-iq-for-python"></a><span data-ttu-id="a939a-131">Atualizar IQ # para Python</span><span class="sxs-lookup"><span data-stu-id="a939a-131">Update IQ# for Python</span></span>

1. <span data-ttu-id="a939a-132">Atualizar o kernel `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="a939a-132">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="a939a-133">Verificar a versão do `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="a939a-133">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="a939a-134">Deverá ver o resultado seguinte:</span><span class="sxs-lookup"><span data-stu-id="a939a-134">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```

1. <span data-ttu-id="a939a-135">Atualizar o pacote de `qsharp`</span><span class="sxs-lookup"><span data-stu-id="a939a-135">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="a939a-136">Verificar a versão do `qsharp`</span><span class="sxs-lookup"><span data-stu-id="a939a-136">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="a939a-137">Deverá ver o resultado seguinte:</span><span class="sxs-lookup"><span data-stu-id="a939a-137">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1911.307
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```
1. <span data-ttu-id="a939a-138">Execute o seguinte comando no local de seus arquivos de `.qs`</span><span class="sxs-lookup"><span data-stu-id="a939a-138">Run the following command from the location of your `.qs` files</span></span>
    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

1. <span data-ttu-id="a939a-139">Agora você pode usar a versão atualizada do QDK para executar seus programas de Quantum existentes.</span><span class="sxs-lookup"><span data-stu-id="a939a-139">You can now use the updated QDK version to run your existing quantum programs.</span></span>

## <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="a939a-140">Atualizar IQ # para notebooks Jupyter</span><span class="sxs-lookup"><span data-stu-id="a939a-140">Update IQ# for Jupyter notebooks</span></span>

1. <span data-ttu-id="a939a-141">Atualizar o kernel `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="a939a-141">Update the `iqsharp` kernel</span></span>

    ```bash
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="a939a-142">Verificar a versão do `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="a939a-142">Verify the `iqsharp` version</span></span>

    ```bash
    dotnet iqsharp --version
    ```

    <span data-ttu-id="a939a-143">Deverá ver o resultado seguinte:</span><span class="sxs-lookup"><span data-stu-id="a939a-143">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1911.307
    Jupyter Core: 1.2.20112.0
    ```
1. <span data-ttu-id="a939a-144">Execute o seguinte comando de uma célula no seu Jupyter Notebook:</span><span class="sxs-lookup"><span data-stu-id="a939a-144">Run the following command from a cell in your Jupyter Notebook:</span></span>
    ```
    %workspace reload
    ```

1. <span data-ttu-id="a939a-145">Agora você pode abrir um bloco de anotações do Jupyter existente e executá-lo com o QDK atualizado.</span><span class="sxs-lookup"><span data-stu-id="a939a-145">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

## <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="a939a-146">Atualizar a extensão QDK do Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a939a-146">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="a939a-147">Atualizar a extensão do Q # Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a939a-147">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="a939a-148">O Visual Studio solicita que você aceite atualizações para a [extensão Quantum do Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="a939a-148">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="a939a-149">Aceitar a atualização</span><span class="sxs-lookup"><span data-stu-id="a939a-149">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="a939a-150">Os modelos de projeto são atualizados com a extensão.</span><span class="sxs-lookup"><span data-stu-id="a939a-150">The project templates are updated with the extension.</span></span> <span data-ttu-id="a939a-151">Os modelos atualizados se aplicam apenas a projetos recém-criados.</span><span class="sxs-lookup"><span data-stu-id="a939a-151">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="a939a-152">O código para seus projetos existentes não é atualizado quando a extensão é atualizada.</span><span class="sxs-lookup"><span data-stu-id="a939a-152">The code for your existing projects is not updated when the extension is updated.</span></span>

## <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="a939a-153">Atualizar VS Code extensão QDK</span><span class="sxs-lookup"><span data-stu-id="a939a-153">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="a939a-154">Atualizar a extensão de VS Code Quantum</span><span class="sxs-lookup"><span data-stu-id="a939a-154">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="a939a-155">Reiniciar VS Code</span><span class="sxs-lookup"><span data-stu-id="a939a-155">Restart VS Code</span></span>
    - <span data-ttu-id="a939a-156">Navegue até a guia **extensões**</span><span class="sxs-lookup"><span data-stu-id="a939a-156">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="a939a-157">Selecione o **Microsoft Quantum Development Kit para Visual Studio Code** extensão</span><span class="sxs-lookup"><span data-stu-id="a939a-157">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="a939a-158">Recarregar a extensão</span><span class="sxs-lookup"><span data-stu-id="a939a-158">Reload the extension</span></span>

1. <span data-ttu-id="a939a-159">Atualize os modelos de projeto Quantum:</span><span class="sxs-lookup"><span data-stu-id="a939a-159">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="a939a-160">Aceda a **Ver** -> **Paleta de Comandos**</span><span class="sxs-lookup"><span data-stu-id="a939a-160">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="a939a-161">Selecione **Q #: instalar modelos de projeto**</span><span class="sxs-lookup"><span data-stu-id="a939a-161">Select **Q#: Install project templates**</span></span>

## <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="a939a-162">C#, usando a ferramenta de linha de comando `dotnet`</span><span class="sxs-lookup"><span data-stu-id="a939a-162">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="a939a-163">Atualizar os modelos de projeto Quantum para .NET</span><span class="sxs-lookup"><span data-stu-id="a939a-163">Update the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a><span data-ttu-id="a939a-164">O que se segue?</span><span class="sxs-lookup"><span data-stu-id="a939a-164">What's next?</span></span>

<span data-ttu-id="a939a-165">Agora que você atualizou o kit de desenvolvimento Quantum em seu ambiente preferido, você pode continuar a desenvolver e executar seus programas Quantum.</span><span class="sxs-lookup"><span data-stu-id="a939a-165">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="a939a-166">Se você ainda não escreveu um programa, você pode começar com [seu primeiro programa Quantum](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="a939a-166">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
