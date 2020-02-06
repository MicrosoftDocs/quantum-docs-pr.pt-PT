---
title: Saiba como atualizar o Kit de Desenvolvimento Quântico da Microsoft (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: f19285ae0e008b3460d06430a236f098d716e268
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036326"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="385db-102">Atualizar o Kit de Desenvolvimento Quântico da Microsoft (QDK)</span><span class="sxs-lookup"><span data-stu-id="385db-102">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="385db-103">Saiba como atualizar o Microsoft Quantum Development Kit (QDK) para a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="385db-103">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="385db-104">Este artigo assume que já tem o QDK instalado.</span><span class="sxs-lookup"><span data-stu-id="385db-104">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="385db-105">Se estiver a instalar pela primeira vez, consulte o guia de [instalação](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="385db-105">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="385db-106">Recomendamos que se mantenha atualizado com o mais recente lançamento qDK.</span><span class="sxs-lookup"><span data-stu-id="385db-106">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="385db-107">Siga este guia de atualização para atualizar para a versão QDK mais recente.</span><span class="sxs-lookup"><span data-stu-id="385db-107">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="385db-108">O processo consiste em duas partes:</span><span class="sxs-lookup"><span data-stu-id="385db-108">The process consists of two parts:</span></span>
1. <span data-ttu-id="385db-109">atualizando os seus ficheiros e projetos Q# existentes para alinhar o seu código com qualquer sintaxe atualizada</span><span class="sxs-lookup"><span data-stu-id="385db-109">updating your existing Q# files and projects to align your code with any updated syntax</span></span>
2. <span data-ttu-id="385db-110">atualizando o próprio QDK para o seu ambiente de desenvolvimento escolhido</span><span class="sxs-lookup"><span data-stu-id="385db-110">updating the QDK itself for your chosen development environment</span></span> 

## <a name="updating-q-projects"></a><span data-ttu-id="385db-111">Atualizar projetos Q#</span><span class="sxs-lookup"><span data-stu-id="385db-111">Updating Q# Projects</span></span> 

<span data-ttu-id="385db-112">Independentemente de estar a C# usar ou python para acolher operações q#, siga estas instruções para atualizar os seus projetos Q#.</span><span class="sxs-lookup"><span data-stu-id="385db-112">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="385db-113">Primeiro, verifique se tem a versão mais recente do [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="385db-113">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="385db-114">Executar o seguinte comando no pedido de comando:</span><span class="sxs-lookup"><span data-stu-id="385db-114">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="385db-115">Verifique se a saída é `3.1.100` ou superior.</span><span class="sxs-lookup"><span data-stu-id="385db-115">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="385db-116">Caso contrário, instale a [versão mais recente](https://dotnet.microsoft.com/download) e verifique novamente.</span><span class="sxs-lookup"><span data-stu-id="385db-116">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="385db-117">Em seguida, siga as instruções abaixo, dependendo da sua configuração (Visual Studio, Visual Studio Code ou diretamente a linha de comando).</span><span class="sxs-lookup"><span data-stu-id="385db-117">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="385db-118">Atualizar projetos Q# no Estúdio Visual</span><span class="sxs-lookup"><span data-stu-id="385db-118">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="385db-119">Atualização para a versão mais recente do Visual Studio 2019, consulte [aqui](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) as instruções</span><span class="sxs-lookup"><span data-stu-id="385db-119">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions</span></span>
2. <span data-ttu-id="385db-120">Abra a sua solução no Estúdio Visual</span><span class="sxs-lookup"><span data-stu-id="385db-120">Open your solution in Visual Studio</span></span>
3. <span data-ttu-id="385db-121">No menu, selecione **Build** -> **Clean Solution**</span><span class="sxs-lookup"><span data-stu-id="385db-121">From the menu, select **Build** -> **Clean Solution**</span></span>
4. <span data-ttu-id="385db-122">Em cada um dos seus ficheiros .csproj, atualize o quadro-alvo para `netcoreapp3.0` (ou `netstandard2.1` se for um projeto de biblioteca).</span><span class="sxs-lookup"><span data-stu-id="385db-122">In each of your .csproj files, update the target framework to `netcoreapp3.0` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="385db-123">Ou seja, editar linhas do formulário:</span><span class="sxs-lookup"><span data-stu-id="385db-123">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```

    <span data-ttu-id="385db-124">Pode encontrar mais detalhes sobre a especificação dos quadros-alvo [aqui](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="385db-124">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
5. <span data-ttu-id="385db-125">Guarde e feche todos os ficheiros da sua solução</span><span class="sxs-lookup"><span data-stu-id="385db-125">Save and close all files in your solution</span></span>
6. <span data-ttu-id="385db-126">**Selecione ferramentas** -> linha de **comando** -> comando **do desenvolvedor**</span><span class="sxs-lookup"><span data-stu-id="385db-126">Select **Tools** -> **Command Line** -> **Developer Command Prompt**</span></span>
7. <span data-ttu-id="385db-127">Para cada projeto na solução, executar o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="385db-127">For each project in the solution, run the following command:</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="385db-128">Se os seus projetos utilizarem outros pacotes Microsoft.Quantum (por exemplo, Microsoft.Quantum.Numerics), execute o comando para estes também.</span><span class="sxs-lookup"><span data-stu-id="385db-128">If your projects use any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
8. <span data-ttu-id="385db-129">Feche o pedido de comando e selecione **Build** -> **Build Solution** *(não* selecione Rebuild Solution)</span><span class="sxs-lookup"><span data-stu-id="385db-129">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution)</span></span>

<span data-ttu-id="385db-130">Agora pode saltar para a frente para [atualizar a extensão QDK do Estúdio Visual](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="385db-130">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="385db-131">Atualizar projetos Q# no Código do Estúdio Visual</span><span class="sxs-lookup"><span data-stu-id="385db-131">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="385db-132">No Código do Estúdio Visual, abra a pasta contendo o projeto para atualizar</span><span class="sxs-lookup"><span data-stu-id="385db-132">In Visual Studio Code, open the folder containing the project to update</span></span>
2. <span data-ttu-id="385db-133">Selecione **terminal** -> **novo terminal**</span><span class="sxs-lookup"><span data-stu-id="385db-133">Select **Terminal** -> **New Terminal**</span></span>
3. <span data-ttu-id="385db-134">Siga as instruções de atualização utilizando a linha de comando (diretamente abaixo)</span><span class="sxs-lookup"><span data-stu-id="385db-134">Follow the instructions for updating using the command line (directly below)</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="385db-135">Atualizar projetos Q# usando a linha de comando</span><span class="sxs-lookup"><span data-stu-id="385db-135">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="385db-136">Navegue para a pasta que contém o seu ficheiro de projeto</span><span class="sxs-lookup"><span data-stu-id="385db-136">Navigate to the folder containing your project file</span></span>
2. <span data-ttu-id="385db-137">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="385db-137">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="385db-138">Em cada um dos seus ficheiros .csproj, atualize o quadro-alvo para `netcoreapp3.0` (ou `netstandard2.1` se for um projeto de biblioteca).</span><span class="sxs-lookup"><span data-stu-id="385db-138">In each of your .csproj files, update the target framework to `netcoreapp3.0` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="385db-139">Ou seja, editar linhas do formulário:</span><span class="sxs-lookup"><span data-stu-id="385db-139">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.0</TargetFramework>
    ```

    <span data-ttu-id="385db-140">Pode encontrar mais detalhes sobre a especificação dos quadros-alvo [aqui](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="385db-140">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>
4. <span data-ttu-id="385db-141">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="385db-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet add package Microsoft.Quantum.Development.Kit
    ```

    <span data-ttu-id="385db-142">Se o seu projeto utilizar outros pacotes Microsoft.Quantum (por exemplo, Microsoft.Quantum.Numerics), execute o comando para estes também.</span><span class="sxs-lookup"><span data-stu-id="385db-142">If your project uses any other Microsoft.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the command for these too.</span></span>
5. <span data-ttu-id="385db-143">Guarde e feche todos os ficheiros.</span><span class="sxs-lookup"><span data-stu-id="385db-143">Save and close all files.</span></span>
6. <span data-ttu-id="385db-144">Repita 1-4 para cada dependência do projeto, depois navegue de volta para a pasta que contém o seu projeto principal e executar:</span><span class="sxs-lookup"><span data-stu-id="385db-144">Repeat 1-4 for each project dependency, then navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="385db-145">Com os seus projetos Q# agora atualizados, siga as instruções abaixo para atualizar o próprio QDK.</span><span class="sxs-lookup"><span data-stu-id="385db-145">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="385db-146">Atualizar o QDK</span><span class="sxs-lookup"><span data-stu-id="385db-146">Updating the QDK</span></span>

<span data-ttu-id="385db-147">O processo de atualização do QDK varia consoante a sua linguagem e ambiente de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="385db-147">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="385db-148">Selecione o seu ambiente de desenvolvimento abaixo.</span><span class="sxs-lookup"><span data-stu-id="385db-148">Select your development environment below.</span></span>

* [<span data-ttu-id="385db-149">Python: atualizar a extensão IQ#</span><span class="sxs-lookup"><span data-stu-id="385db-149">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="385db-150">Cadernos Jupyter: atualizar a extensão IQ#</span><span class="sxs-lookup"><span data-stu-id="385db-150">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="385db-151">Estúdio Visual: atualizar a extensão QDK</span><span class="sxs-lookup"><span data-stu-id="385db-151">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="385db-152">Código VS: atualizar a extensão QDK</span><span class="sxs-lookup"><span data-stu-id="385db-152">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="385db-153">Linha de C#comando e : modelos de projeto de atualização</span><span class="sxs-lookup"><span data-stu-id="385db-153">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="385db-154">Atualização IQ# para Python</span><span class="sxs-lookup"><span data-stu-id="385db-154">Update IQ# for Python</span></span>

1. <span data-ttu-id="385db-155">Atualize o núcleo de `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="385db-155">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="385db-156">Verifique a versão `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="385db-156">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="385db-157">Deverá ver o resultado seguinte:</span><span class="sxs-lookup"><span data-stu-id="385db-157">You should see the following output:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="385db-158">Não se preocupe se a sua versão `iqsharp` for maior, deverá corresponder ao [lançamento mais recente](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="385db-158">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="385db-159">Atualizar o pacote `qsharp`</span><span class="sxs-lookup"><span data-stu-id="385db-159">Update the `qsharp` package</span></span>

    ```bash
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="385db-160">Verifique a versão `qsharp`</span><span class="sxs-lookup"><span data-stu-id="385db-160">Verify the `qsharp` version</span></span>

    ```bash
    pip show qsharp
    ```

    <span data-ttu-id="385db-161">Deverá ver o resultado seguinte:</span><span class="sxs-lookup"><span data-stu-id="385db-161">You should see the following output:</span></span>

    ```bash
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="385db-162">Execute o seguinte comando a partir da localização dos seus ficheiros `.qs`</span><span class="sxs-lookup"><span data-stu-id="385db-162">Run the following command from the location of your `.qs` files</span></span>

    ```bash
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="385db-163">Agora pode usar a versão QDK atualizada para executar os seus programas quânticos existentes.</span><span class="sxs-lookup"><span data-stu-id="385db-163">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="385db-164">Atualização IQ# para Cadernos Jupyter</span><span class="sxs-lookup"><span data-stu-id="385db-164">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="385db-165">Atualize o núcleo de `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="385db-165">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="385db-166">Verifique a versão `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="385db-166">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="385db-167">A sua saída deve ser semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="385db-167">Your output should be similar to the following:</span></span>

    ```bash
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="385db-168">Não se preocupe se a sua versão `iqsharp` for maior, deverá corresponder ao [lançamento mais recente](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="385db-168">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="385db-169">Execute o seguinte comando a partir de uma célula no seu Caderno Jupyter:</span><span class="sxs-lookup"><span data-stu-id="385db-169">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="385db-170">Agora pode abrir um caderno Jupyter existente e executá-lo com o QDK atualizado.</span><span class="sxs-lookup"><span data-stu-id="385db-170">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="385db-171">Atualizar extensão QDK do Estúdio Visual</span><span class="sxs-lookup"><span data-stu-id="385db-171">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="385db-172">Atualizar a extensão q# Estúdio Visual</span><span class="sxs-lookup"><span data-stu-id="385db-172">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="385db-173">Visual Studio pede-lhe para aceitar atualizações para a [extensão do Quantum Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="385db-173">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="385db-174">Aceite a atualização</span><span class="sxs-lookup"><span data-stu-id="385db-174">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="385db-175">Os modelos do projeto são atualizados com a extensão.</span><span class="sxs-lookup"><span data-stu-id="385db-175">The project templates are updated with the extension.</span></span> <span data-ttu-id="385db-176">Os modelos atualizados aplicam-se apenas a projetos recém-criados.</span><span class="sxs-lookup"><span data-stu-id="385db-176">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="385db-177">O código para os seus projetos existentes não é atualizado quando a extensão é atualizada.</span><span class="sxs-lookup"><span data-stu-id="385db-177">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="385db-178">Atualizar extensão qDK código VS</span><span class="sxs-lookup"><span data-stu-id="385db-178">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="385db-179">Atualizar a extensão do Código Vs Quântico</span><span class="sxs-lookup"><span data-stu-id="385db-179">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="385db-180">Reiniciar código VS</span><span class="sxs-lookup"><span data-stu-id="385db-180">Restart VS Code</span></span>
    - <span data-ttu-id="385db-181">Navegue para o separador **Extensões**</span><span class="sxs-lookup"><span data-stu-id="385db-181">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="385db-182">Selecione o Kit de **Desenvolvimento Quântico da Microsoft para** extensão do Código do Estúdio Visual</span><span class="sxs-lookup"><span data-stu-id="385db-182">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="385db-183">Recarregar a extensão</span><span class="sxs-lookup"><span data-stu-id="385db-183">Reload the extension</span></span>

2. <span data-ttu-id="385db-184">Atualizar os modelos do projeto Quantum:</span><span class="sxs-lookup"><span data-stu-id="385db-184">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="385db-185">Aceda a **Ver** -> **Paleta de Comandos**</span><span class="sxs-lookup"><span data-stu-id="385db-185">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="385db-186">Selecione **Q#: Instale modelos de projeto**</span><span class="sxs-lookup"><span data-stu-id="385db-186">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="385db-187">Após alguns segundos deve obter um popup confirmando "modelos de projeto instalados com sucesso"</span><span class="sxs-lookup"><span data-stu-id="385db-187">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="385db-188">C#, utilizando a ferramenta `dotnet` linha de comando</span><span class="sxs-lookup"><span data-stu-id="385db-188">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="385db-189">Atualizar os modelos de projeto quantum para .NET</span><span class="sxs-lookup"><span data-stu-id="385db-189">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

## <a name="whats-next"></a><span data-ttu-id="385db-190">Passos seguintes?</span><span class="sxs-lookup"><span data-stu-id="385db-190">What's next?</span></span>

<span data-ttu-id="385db-191">Agora que atualizou o Kit de Desenvolvimento Quântico no seu ambiente preferido, pode continuar a desenvolver e executar os seus programas quânticos.</span><span class="sxs-lookup"><span data-stu-id="385db-191">Now that you have updated the Quantum Development Kit in your preferred environment, you can continue to develop and run your quantum programs.</span></span> <span data-ttu-id="385db-192">Se ainda não escreveu um programa, pode começar com [o seu primeiro programa quântico.](xref:microsoft.quantum.write-program)</span><span class="sxs-lookup"><span data-stu-id="385db-192">If you have not written a program yet, you can get started with [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
