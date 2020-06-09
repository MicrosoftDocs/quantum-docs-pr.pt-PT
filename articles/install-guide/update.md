---
title: Atualizar o Kit de Desenvolvimento Quântico (QDK)
description: Descreve como atualizar os seus projetos Q# e o Microsoft Quantum Development Kit para a versão atual.
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.update
ms.openlocfilehash: 89db1a671767b0cc083a251918bbeeed2b39b883
ms.sourcegitcommit: c8ebc5d7d8581444754f5d7bfaca2f25601f1b14
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84578186"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="c1e62-103">Atualizar o Kit de Desenvolvimento Quântico da Microsoft (QDK)</span><span class="sxs-lookup"><span data-stu-id="c1e62-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="c1e62-104">Saiba como atualizar o Microsoft Quantum Development Kit (QDK) para a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="c1e62-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="c1e62-105">Este artigo pressupõe que já tem o QDK instalado.</span><span class="sxs-lookup"><span data-stu-id="c1e62-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="c1e62-106">Se estiver a instalar pela primeira vez, consulte o [guia de instalação](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="c1e62-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="c1e62-107">Recomendamos manter-nos atualizados com o mais recente lançamento do QDK.</span><span class="sxs-lookup"><span data-stu-id="c1e62-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="c1e62-108">Siga este guia de atualização para atualizar para a versão QDK mais recente.</span><span class="sxs-lookup"><span data-stu-id="c1e62-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="c1e62-109">O processo é composto por duas partes:</span><span class="sxs-lookup"><span data-stu-id="c1e62-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="c1e62-110">Atualizar os ficheiros e projetos Q# existentes para alinhar o seu código com qualquer sintaxe atualizada.</span><span class="sxs-lookup"><span data-stu-id="c1e62-110">Updating your existing Q# files and projects to align your code with any updated syntax.</span></span>
2. <span data-ttu-id="c1e62-111">Atualizar o próprio QDK para o seu ambiente de desenvolvimento escolhido.</span><span class="sxs-lookup"><span data-stu-id="c1e62-111">Updating the QDK itself for your chosen development environment.</span></span>

## <a name="updating-q-projects"></a><span data-ttu-id="c1e62-112">Atualizar projetos Q#</span><span class="sxs-lookup"><span data-stu-id="c1e62-112">Updating Q# Projects</span></span> 

<span data-ttu-id="c1e62-113">Independentemente de estar a utilizar C# ou Python para acolher operações Q#, siga estas instruções para atualizar os seus projetos Q#.</span><span class="sxs-lookup"><span data-stu-id="c1e62-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="c1e62-114">Em primeiro lugar, verifique se tem a versão mais recente do [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="c1e62-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="c1e62-115">Executar o seguinte comando na pronta de comando:</span><span class="sxs-lookup"><span data-stu-id="c1e62-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="c1e62-116">Verifique se a saída é `3.1.100` ou superior.</span><span class="sxs-lookup"><span data-stu-id="c1e62-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="c1e62-117">Caso contrário, instale a [versão mais recente](https://dotnet.microsoft.com/download) e verifique novamente.</span><span class="sxs-lookup"><span data-stu-id="c1e62-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="c1e62-118">Em seguida, siga as instruções abaixo, dependendo da sua configuração (Visual Studio, Visual Studio Code ou diretamente a linha de comando).</span><span class="sxs-lookup"><span data-stu-id="c1e62-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly the command line).</span></span>

### <a name="update-q-projects-in-visual-studio"></a><span data-ttu-id="c1e62-119">Atualizar projetos Q# em Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c1e62-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="c1e62-120">Atualização para a versão mais recente do Visual Studio 2019, consulte [aqui](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="c1e62-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019) for instructions.</span></span>
2. <span data-ttu-id="c1e62-121">Abra a sua solução no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c1e62-121">Open your solution in Visual Studio.</span></span>
3. <span data-ttu-id="c1e62-122">No menu, selecione **Build**  ->  **Clean Solution**.</span><span class="sxs-lookup"><span data-stu-id="c1e62-122">From the menu, select **Build** -> **Clean Solution**.</span></span>
4. <span data-ttu-id="c1e62-123">Em cada um dos seus ficheiros .csproj, atualize o quadro-alvo para `netcoreapp3.1` (ou `netstandard2.1` se é um projeto de biblioteca).</span><span class="sxs-lookup"><span data-stu-id="c1e62-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="c1e62-124">Ou seja, editar linhas do formulário:</span><span class="sxs-lookup"><span data-stu-id="c1e62-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="c1e62-125">Pode encontrar mais detalhes sobre a especificação dos quadros-alvo [aqui.](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)</span><span class="sxs-lookup"><span data-stu-id="c1e62-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

5. <span data-ttu-id="c1e62-126">Em cada um dos ficheiros .csproj, desajei o SDK, `Microsoft.Quantum.Sdk` como indicado na linha abaixo.</span><span class="sxs-lookup"><span data-stu-id="c1e62-126">In each of the .csproj files, set the SDK to `Microsoft.Quantum.Sdk`, as indicated in the line below.</span></span> <span data-ttu-id="c1e62-127">Por favor, note que o número da versão deve ser o mais recente disponível, e pode determiná-lo revendo as [notas de lançamento](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="c1e62-127">Please notice that the version number should be the latest available, and you can determine it by reviewing the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span>

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
    ```

6. <span data-ttu-id="c1e62-128">Guarde e feche todos os ficheiros da sua solução.</span><span class="sxs-lookup"><span data-stu-id="c1e62-128">Save and close all files in your solution.</span></span>

7. <span data-ttu-id="c1e62-129">Selecione **ferramentas**  ->  **comando**  ->  **de programador de**linha .</span><span class="sxs-lookup"><span data-stu-id="c1e62-129">Select **Tools** -> **Command Line** -> **Developer Command Prompt**.</span></span> <span data-ttu-id="c1e62-130">Em alternativa, pode utilizar a consola de gestão de pacotes no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c1e62-130">Alternatively, you can use the package management console in Visual Studio.</span></span>

8. <span data-ttu-id="c1e62-131">Para cada projeto na solução, executar o seguinte comando para **remover** este pacote:</span><span class="sxs-lookup"><span data-stu-id="c1e62-131">For each project in the solution, run the following command to **remove** this package:</span></span>

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="c1e62-132">Se os seus projetos utilizarem quaisquer outros pacotes Microsoft.Quantum ou Microsoft.Azure.Quantum (por exemplo, Microsoft.Quantum.Nummerics), executar o comando **de adicionar** para estes atualizarem a versão utilizada.</span><span class="sxs-lookup"><span data-stu-id="c1e62-132">If your projects use any other Microsoft.Quantum or Microsoft.Azure.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the **add** command for these to update the version used.</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. <span data-ttu-id="c1e62-133">Feche a solicitação de comando e selecione **a**  ->  **solução** Build Build *(não* selecione a Solução de Reconstrução).</span><span class="sxs-lookup"><span data-stu-id="c1e62-133">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution).</span></span>

<span data-ttu-id="c1e62-134">Pode agora antecipar-se para [atualizar a extensão QDK do Seu Estúdio Visual](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="c1e62-134">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-q-projects-in-visual-studio-code"></a><span data-ttu-id="c1e62-135">Atualizar projetos Q# em Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c1e62-135">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="c1e62-136">No Código do Estúdio Visual, abra a pasta que contém o projeto para atualizar.</span><span class="sxs-lookup"><span data-stu-id="c1e62-136">In Visual Studio Code, open the folder containing the project to update.</span></span>
2. <span data-ttu-id="c1e62-137">Selecione **Terminal**  ->  **Novo Terminal**Terminal .</span><span class="sxs-lookup"><span data-stu-id="c1e62-137">Select **Terminal** -> **New Terminal**.</span></span>
3. <span data-ttu-id="c1e62-138">Siga as instruções de atualização utilizando a linha de comando (diretamente abaixo).</span><span class="sxs-lookup"><span data-stu-id="c1e62-138">Follow the instructions for updating using the command line (directly below).</span></span>

### <a name="update-q-projects-using-the-command-line"></a><span data-ttu-id="c1e62-139">Atualizar projetos Q# usando a linha de comando</span><span class="sxs-lookup"><span data-stu-id="c1e62-139">Update Q# projects using the command line</span></span>

1. <span data-ttu-id="c1e62-140">Navegue para a pasta que contém o seu ficheiro principal do projeto.</span><span class="sxs-lookup"><span data-stu-id="c1e62-140">Navigate to the folder containing your main project file.</span></span>

2. <span data-ttu-id="c1e62-141">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="c1e62-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="c1e62-142">Determine a versão atual do QDK.</span><span class="sxs-lookup"><span data-stu-id="c1e62-142">Determine the current version of the QDK.</span></span> <span data-ttu-id="c1e62-143">Para encontrá-lo, pode rever as [notas de lançamento.](https://docs.microsoft.com/quantum/relnotes/)</span><span class="sxs-lookup"><span data-stu-id="c1e62-143">To find it, you can review the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span> <span data-ttu-id="c1e62-144">A versão será num formato semelhante a `0.11.2006.207` .</span><span class="sxs-lookup"><span data-stu-id="c1e62-144">The version will be in a format similar to `0.11.2006.207`.</span></span>

4. <span data-ttu-id="c1e62-145">Em cada um dos seus `.csproj` ficheiros, ver os seguintes passos:</span><span class="sxs-lookup"><span data-stu-id="c1e62-145">In each of your `.csproj` files, go through the following steps:</span></span>

    - <span data-ttu-id="c1e62-146">Atualizar o quadro-alvo para `netcoreapp3.1` (ou `netstandard2.1` se é um projeto de biblioteca).</span><span class="sxs-lookup"><span data-stu-id="c1e62-146">Update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span> <span data-ttu-id="c1e62-147">Ou seja, editar linhas do formulário:</span><span class="sxs-lookup"><span data-stu-id="c1e62-147">That is, edit lines of the form:</span></span>

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        <span data-ttu-id="c1e62-148">Pode encontrar mais detalhes sobre a especificação dos quadros-alvo [aqui.](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks)</span><span class="sxs-lookup"><span data-stu-id="c1e62-148">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

    - <span data-ttu-id="c1e62-149">Substitua a referência ao SDK na definição do projeto.</span><span class="sxs-lookup"><span data-stu-id="c1e62-149">Replace the reference to the SDK in the project definition.</span></span> <span data-ttu-id="c1e62-150">Certifique-se de que o número da versão corresponde ao valor determinado no **passo 3**.</span><span class="sxs-lookup"><span data-stu-id="c1e62-150">Make sure that the version number corresponds to the value determined in **step 3**.</span></span>

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.11.2006.207">
        ```

    - <span data-ttu-id="c1e62-151">Remova a referência à embalagem `Microsoft.Quantum.Development.Kit` se estiver presente, que será especificada na seguinte rubrica:</span><span class="sxs-lookup"><span data-stu-id="c1e62-151">Remove the reference to package `Microsoft.Quantum.Development.Kit` if present, which will be specified in the following entry:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - <span data-ttu-id="c1e62-152">Atualize a versão de todos os pacotes Da Microsoft Quantum para a versão mais recente do QDK (determinada no **passo 3).**</span><span class="sxs-lookup"><span data-stu-id="c1e62-152">Update the version of the all the Microsoft Quantum packages to the most recently released version of the QDK (determined in **step 3**).</span></span> <span data-ttu-id="c1e62-153">Estes pacotes têm o nome dos seguintes padrões:</span><span class="sxs-lookup"><span data-stu-id="c1e62-153">Those packages are named with the following patterns:</span></span>

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        <span data-ttu-id="c1e62-154">As referências aos pacotes têm o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="c1e62-154">References to packages have the following format:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.11.2006.207" />
        ```

    - <span data-ttu-id="c1e62-155">Guarde o ficheiro atualizado.</span><span class="sxs-lookup"><span data-stu-id="c1e62-155">Save the updated file.</span></span>

    - <span data-ttu-id="c1e62-156">Restaurar as dependências do projeto, fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c1e62-156">Restore the dependencies of the project, by doing the following:</span></span>

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. <span data-ttu-id="c1e62-157">Volte para a pasta que contém o seu projeto principal e corra:</span><span class="sxs-lookup"><span data-stu-id="c1e62-157">Navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="c1e62-158">Com os seus projetos Q# agora atualizados, siga as instruções abaixo para atualizar o próprio QDK.</span><span class="sxs-lookup"><span data-stu-id="c1e62-158">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="c1e62-159">Atualizar o QDK</span><span class="sxs-lookup"><span data-stu-id="c1e62-159">Updating the QDK</span></span>

<span data-ttu-id="c1e62-160">O processo de atualização do QDK varia consoante a sua linguagem e ambiente de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="c1e62-160">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="c1e62-161">Selecione o seu ambiente de desenvolvimento abaixo.</span><span class="sxs-lookup"><span data-stu-id="c1e62-161">Select your development environment below.</span></span>

* [<span data-ttu-id="c1e62-162">Python: atualize a extensão IQ#</span><span class="sxs-lookup"><span data-stu-id="c1e62-162">Python: update the IQ# extension</span></span>](#update-iq-for-python)
* [<span data-ttu-id="c1e62-163">Jupyter Notebooks: atualize a extensão do QI#</span><span class="sxs-lookup"><span data-stu-id="c1e62-163">Jupyter Notebooks: update the IQ# extension</span></span>](#update-iq-for-jupyter-notebooks)
* [<span data-ttu-id="c1e62-164">Visual Studio: atualize a extensão QDK</span><span class="sxs-lookup"><span data-stu-id="c1e62-164">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="c1e62-165">Código VS: atualizar a extensão QDK</span><span class="sxs-lookup"><span data-stu-id="c1e62-165">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="c1e62-166">Linha de comando e C#: atualizar modelos de projeto</span><span class="sxs-lookup"><span data-stu-id="c1e62-166">Command-line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-iq-for-python"></a><span data-ttu-id="c1e62-167">Atualização IQ# para Python</span><span class="sxs-lookup"><span data-stu-id="c1e62-167">Update IQ# for Python</span></span>

1. <span data-ttu-id="c1e62-168">Atualizar o `iqsharp` núcleo</span><span class="sxs-lookup"><span data-stu-id="c1e62-168">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="c1e62-169">Verifique a `iqsharp` versão</span><span class="sxs-lookup"><span data-stu-id="c1e62-169">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="c1e62-170">Deverá ver o resultado seguinte:</span><span class="sxs-lookup"><span data-stu-id="c1e62-170">You should see the following output:</span></span>

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="c1e62-171">Não se preocupe se a sua `iqsharp` versão for maior, deverá corresponder ao [último lançamento](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="c1e62-171">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="c1e62-172">Atualizar o `qsharp` pacote</span><span class="sxs-lookup"><span data-stu-id="c1e62-172">Update the `qsharp` package</span></span>

    ```
    pip install qsharp --upgrade
    ```

4. <span data-ttu-id="c1e62-173">Verifique a `qsharp` versão</span><span class="sxs-lookup"><span data-stu-id="c1e62-173">Verify the `qsharp` version</span></span>

    ```
    pip show qsharp
    ```

    <span data-ttu-id="c1e62-174">Deverá ver o resultado seguinte:</span><span class="sxs-lookup"><span data-stu-id="c1e62-174">You should see the following output:</span></span>

    ```
    Name: qsharp
    Version: 0.10.1912.501
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

5. <span data-ttu-id="c1e62-175">Executar o seguinte comando a partir da localização dos seus `.qs` ficheiros</span><span class="sxs-lookup"><span data-stu-id="c1e62-175">Run the following command from the location of your `.qs` files</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

6. <span data-ttu-id="c1e62-176">Agora pode utilizar a versão QDK atualizada para executar os seus programas quânticos existentes.</span><span class="sxs-lookup"><span data-stu-id="c1e62-176">You can now use the updated QDK version to run your existing quantum programs.</span></span>

### <a name="update-iq-for-jupyter-notebooks"></a><span data-ttu-id="c1e62-177">Atualização QI# para Cadernos Jupyter</span><span class="sxs-lookup"><span data-stu-id="c1e62-177">Update IQ# for Jupyter Notebooks</span></span>

1. <span data-ttu-id="c1e62-178">Atualizar o `iqsharp` núcleo</span><span class="sxs-lookup"><span data-stu-id="c1e62-178">Update the `iqsharp` kernel</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

2. <span data-ttu-id="c1e62-179">Verifique a `iqsharp` versão</span><span class="sxs-lookup"><span data-stu-id="c1e62-179">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="c1e62-180">A sua saída deve ser semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="c1e62-180">Your output should be similar to the following:</span></span>

    ```
    iqsharp: 0.10.1912.501
    Jupyter Core: 1.2.20112.0
    ```

    <span data-ttu-id="c1e62-181">Não se preocupe se a sua `iqsharp` versão for maior, deverá corresponder ao [último lançamento](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="c1e62-181">Don't worry if your `iqsharp` version is higher, it should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

3. <span data-ttu-id="c1e62-182">Executar o seguinte comando a partir de uma célula no seu Caderno Jupyter:</span><span class="sxs-lookup"><span data-stu-id="c1e62-182">Run the following command from a cell in your Jupyter Notebook:</span></span>

    ```
    %workspace reload
    ```

4. <span data-ttu-id="c1e62-183">Agora pode abrir um caderno Jupyter existente e executá-lo com o QDK atualizado.</span><span class="sxs-lookup"><span data-stu-id="c1e62-183">You can now open an existing Jupyter notebook and run it with the updated QDK.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="c1e62-184">Atualizar extensão QDK do Estúdio Visual</span><span class="sxs-lookup"><span data-stu-id="c1e62-184">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="c1e62-185">Atualizar a extensão do Estúdio Visual Q#</span><span class="sxs-lookup"><span data-stu-id="c1e62-185">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="c1e62-186">Visual Studio pede-lhe para aceitar atualizações para a [extensão](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) do Quantum Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c1e62-186">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="c1e62-187">Aceite a atualização</span><span class="sxs-lookup"><span data-stu-id="c1e62-187">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="c1e62-188">Os modelos do projeto são atualizados com a extensão.</span><span class="sxs-lookup"><span data-stu-id="c1e62-188">The project templates are updated with the extension.</span></span> <span data-ttu-id="c1e62-189">Os modelos atualizados aplicam-se apenas a projetos recém-criados.</span><span class="sxs-lookup"><span data-stu-id="c1e62-189">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="c1e62-190">O código para os seus projetos existentes não é atualizado quando a extensão é atualizada.</span><span class="sxs-lookup"><span data-stu-id="c1e62-190">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="c1e62-191">Atualização extensão QDK do código VS</span><span class="sxs-lookup"><span data-stu-id="c1e62-191">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="c1e62-192">Atualizar a extensão do Código VS Quântico</span><span class="sxs-lookup"><span data-stu-id="c1e62-192">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="c1e62-193">Reiniciar código VS</span><span class="sxs-lookup"><span data-stu-id="c1e62-193">Restart VS Code</span></span>
    - <span data-ttu-id="c1e62-194">Navegue para o **separador Extensões**</span><span class="sxs-lookup"><span data-stu-id="c1e62-194">Navigate to the **Extensions** tab</span></span>
    - <span data-ttu-id="c1e62-195">Selecione o **Kit de Desenvolvimento Quântico da Microsoft para** extensão visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="c1e62-195">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="c1e62-196">Recarregar a extensão</span><span class="sxs-lookup"><span data-stu-id="c1e62-196">Reload the extension</span></span>

2. <span data-ttu-id="c1e62-197">Atualize os modelos de projeto quântico:</span><span class="sxs-lookup"><span data-stu-id="c1e62-197">Update the Quantum project templates:</span></span>

   - <span data-ttu-id="c1e62-198">Ir para **ver paleta**  ->  **de comando**</span><span class="sxs-lookup"><span data-stu-id="c1e62-198">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="c1e62-199">Selecione **Q#: Instale modelos de projeto**</span><span class="sxs-lookup"><span data-stu-id="c1e62-199">Select **Q#: Install project templates**</span></span>
   - <span data-ttu-id="c1e62-200">Após alguns segundos, você deve obter um popup confirmando "modelos de projeto instalados com sucesso"</span><span class="sxs-lookup"><span data-stu-id="c1e62-200">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="c1e62-201">C#, utilizando a `dotnet` ferramenta de linha de comando</span><span class="sxs-lookup"><span data-stu-id="c1e62-201">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="c1e62-202">Atualize os modelos de projeto quântico para .NET</span><span class="sxs-lookup"><span data-stu-id="c1e62-202">Update the Quantum project templates for .NET</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```
