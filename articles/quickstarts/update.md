---
title: Atualizar o Quantum Development Kit (QDK)
description: Descreve como atualizar os projetos Q# e o Microsoft Quantum Development kit para a versão atual.
author: bradben
ms.author: v-benbra
ms.date: 5/30/2020
ms.topic: quickstart
uid: microsoft.quantum.update
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1b5def3226bd073c878f8573aaddd757d733ec48
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858049"
---
# <a name="update-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="75fa6-103">Atualizar o Microsoft Quantum Development kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="75fa6-103">Update the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="75fa6-104">Saiba como atualizar o Microsoft Quantum Development kit (QDK) para a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="75fa6-104">Learn how to update the Microsoft Quantum Development Kit (QDK) to the latest version.</span></span>

<span data-ttu-id="75fa6-105">Este artigo pressupõe que já tem o QDK instalado.</span><span class="sxs-lookup"><span data-stu-id="75fa6-105">This article assumes that you already have the QDK installed.</span></span> <span data-ttu-id="75fa6-106">Se estiver a instalar pela primeira vez, veja o [guia de instalação](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="75fa6-106">If you are installing for the first time, then please refer to the [installation guide](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="75fa6-107">Recomendamos utilizar a última versão do QDK.</span><span class="sxs-lookup"><span data-stu-id="75fa6-107">We recommend keeping up to date with the latest QDK release.</span></span> <span data-ttu-id="75fa6-108">Para atualizar para a versão mais recente do QDK, siga este guia de atualização.</span><span class="sxs-lookup"><span data-stu-id="75fa6-108">Follow this update guide to upgrade to the most recent QDK version.</span></span> <span data-ttu-id="75fa6-109">O processo consiste em duas partes:</span><span class="sxs-lookup"><span data-stu-id="75fa6-109">The process consists of two parts:</span></span>
1. <span data-ttu-id="75fa6-110">Atualizar os ficheiros e projetos Q# já existentes para alinhar o código com eventuais sintaxes atualizadas.</span><span class="sxs-lookup"><span data-stu-id="75fa6-110">Updating your existing Q# files and projects to align your code with any updated syntax.</span></span>
2. <span data-ttu-id="75fa6-111">Atualizar o QDK propriamente dito para o ambiente de desenvolvimento que escolheu.</span><span class="sxs-lookup"><span data-stu-id="75fa6-111">Updating the QDK itself for your chosen development environment.</span></span>

## <a name="updating-no-locq-projects"></a><span data-ttu-id="75fa6-112">Atualizar os Projetos Q#</span><span class="sxs-lookup"><span data-stu-id="75fa6-112">Updating Q# Projects</span></span> 

<span data-ttu-id="75fa6-113">Independentemente de utilizar C# ou Python para alojar operações Q#, siga estas instruções para atualizar os seus projetos Q#.</span><span class="sxs-lookup"><span data-stu-id="75fa6-113">Regardless of whether you are using C# or Python to host Q# operations, follow these instructions to update your Q# projects.</span></span>

1. <span data-ttu-id="75fa6-114">Primeiro, verifique se tem a última versão do [SDK de .NET Core 3.1](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="75fa6-114">First, check that you have the latest version of the [.NET Core SDK 3.1](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="75fa6-115">Execute o seguinte comando na linha de comandos:</span><span class="sxs-lookup"><span data-stu-id="75fa6-115">Run the following command in the command prompt:</span></span>

    ```dotnetcli
    dotnet --version
    ```

    <span data-ttu-id="75fa6-116">Veja se a saída é `3.1.100` ou superior.</span><span class="sxs-lookup"><span data-stu-id="75fa6-116">Verify the output is `3.1.100` or higher.</span></span> <span data-ttu-id="75fa6-117">Se não for, instale a [versão mais recente](https://dotnet.microsoft.com/download) e verifique novamente.</span><span class="sxs-lookup"><span data-stu-id="75fa6-117">If not, install the [latest version](https://dotnet.microsoft.com/download) and check again.</span></span> <span data-ttu-id="75fa6-118">Depois, consoante a sua configuração (Visual Studio, Visual Studio Code ou diretamente na linha de comandos), siga as instruções abaixo.</span><span class="sxs-lookup"><span data-stu-id="75fa6-118">Then follow the instructions below depending on your setup (Visual Studio, Visual Studio Code, or directly from the command prompt).</span></span>

### <a name="update-no-locq-projects-in-visual-studio"></a><span data-ttu-id="75fa6-119">Atualizar projetos Q# no Visual Studio</span><span class="sxs-lookup"><span data-stu-id="75fa6-119">Update Q# projects in Visual Studio</span></span>
 
1. <span data-ttu-id="75fa6-120">Atualize para a versão mais recente do Visual Studio 2019; veja as instruções [aqui](https://docs.microsoft.com/visualstudio/install/update-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="75fa6-120">Update to the latest version of Visual Studio 2019, see [here](https://docs.microsoft.com/visualstudio/install/update-visual-studio) for instructions.</span></span>
2. <span data-ttu-id="75fa6-121">Abra a sua solução no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="75fa6-121">Open your solution in Visual Studio.</span></span>
3. <span data-ttu-id="75fa6-122">No menu, selecione **Build** (Compilar)  -> **Clean Solution** (Limpar Solução).</span><span class="sxs-lookup"><span data-stu-id="75fa6-122">From the menu, select **Build** -> **Clean Solution**.</span></span>
4. <span data-ttu-id="75fa6-123">Em cada ficheiro .csproj, atualize o framework de destino para `netcoreapp3.1` (ou `netstandard2.1`, se for um projeto de biblioteca).</span><span class="sxs-lookup"><span data-stu-id="75fa6-123">In each of your .csproj files, update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span>
    <span data-ttu-id="75fa6-124">Ou seja, edite as linhas do formulário:</span><span class="sxs-lookup"><span data-stu-id="75fa6-124">That is, edit lines of the form:</span></span>

    ```xml
    <TargetFramework>netcoreapp3.1</TargetFramework>
    ```

    <span data-ttu-id="75fa6-125">Pode obter mais detalhes sobre como especificar os frameworks de destino [aqui](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="75fa6-125">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

5. <span data-ttu-id="75fa6-126">Em cada ficheiro .csproj, defina o SDK com `Microsoft.Quantum.Sdk`, conforme indicado na linha abaixo.</span><span class="sxs-lookup"><span data-stu-id="75fa6-126">In each of the .csproj files, set the SDK to `Microsoft.Quantum.Sdk`, as indicated in the line below.</span></span> <span data-ttu-id="75fa6-127">Tenha em conta que o número da versão deve ser o último disponível. Para saber qual é, reveja as [notas de versão](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="75fa6-127">Please notice that the version number should be the latest available, and you can determine it by reviewing the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span>

    ```xml
    <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    ```

6. <span data-ttu-id="75fa6-128">Guarde e feche todos os ficheiros da solução.</span><span class="sxs-lookup"><span data-stu-id="75fa6-128">Save and close all files in your solution.</span></span>

7. <span data-ttu-id="75fa6-129">Selecione **Tools** (Ferramentas)  -> **Command Line** (Linha de Comandos)  -> **Developer Command Prompt** (Linha de Comandos de Programador).</span><span class="sxs-lookup"><span data-stu-id="75fa6-129">Select **Tools** -> **Command Line** -> **Developer Command Prompt**.</span></span> <span data-ttu-id="75fa6-130">Em alternativa, pode utilizar a consola do gestor de pacotes no Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="75fa6-130">Alternatively, you can use the package management console in Visual Studio.</span></span>

8. <span data-ttu-id="75fa6-131">Em cada projeto na solução, execute o comando seguinte para **remover** este pacote:</span><span class="sxs-lookup"><span data-stu-id="75fa6-131">For each project in the solution, run the following command to **remove** this package:</span></span>

    ```dotnetcli
    dotnet remove [project_name].csproj package Microsoft.Quantum.Development.Kit
    ```

   <span data-ttu-id="75fa6-132">Se os seus projetos utilizarem quaisquer outros pacotes do Microsoft.Quantum ou do Microsoft.Azure.Quantum packages (por exemplo, Microsoft.Quantum.Numerics), execute o comando **add** para os mesmos, de modo a atualizar a versão utilizada.</span><span class="sxs-lookup"><span data-stu-id="75fa6-132">If your projects use any other Microsoft.Quantum or Microsoft.Azure.Quantum packages (e.g. Microsoft.Quantum.Numerics), run the **add** command for these to update the version used.</span></span>

    ```dotnetcli
    dotnet add [project_name].csproj package [package_name]
    ```

9. <span data-ttu-id="75fa6-133">Escolha a linha de comandos e selecione **Build** (Compilar)  -> **Build Solution** (Compilar Solução) (*não* selecione Rebuild Solution [Recompilar Solução]).</span><span class="sxs-lookup"><span data-stu-id="75fa6-133">Close the command prompt and select **Build** -> **Build Solution** (do *not* select Rebuild Solution).</span></span>

<span data-ttu-id="75fa6-134">Agora, pode avançar para a [atualização da extensão QDK do Visual Studio](#update-visual-studio-qdk-extension).</span><span class="sxs-lookup"><span data-stu-id="75fa6-134">You can now skip ahead to [update your Visual Studio QDK extension](#update-visual-studio-qdk-extension).</span></span>


### <a name="update-no-locq-projects-in-visual-studio-code"></a><span data-ttu-id="75fa6-135">Atualizar projetos Q# no Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="75fa6-135">Update Q# projects in Visual Studio Code</span></span>

1. <span data-ttu-id="75fa6-136">No Visual Studio Code, abra a pasta que contém o projeto a atualizar.</span><span class="sxs-lookup"><span data-stu-id="75fa6-136">In Visual Studio Code, open the folder containing the project to update.</span></span>
2. <span data-ttu-id="75fa6-137">Selecione **Terminal** (Terminal) -> **New Terminal** (Novo Terminal).</span><span class="sxs-lookup"><span data-stu-id="75fa6-137">Select **Terminal** -> **New Terminal**.</span></span>
3. <span data-ttu-id="75fa6-138">Siga as instruções de atualização com a linha de comandos (diretamente abaixo).</span><span class="sxs-lookup"><span data-stu-id="75fa6-138">Follow the instructions for updating using the command prompt (directly below).</span></span>

### <a name="update-no-locq-projects-using-the-command-prompt"></a><span data-ttu-id="75fa6-139">Atualizar projetos Q# com a linha de comandos</span><span class="sxs-lookup"><span data-stu-id="75fa6-139">Update Q# projects using the command prompt</span></span>

1. <span data-ttu-id="75fa6-140">Navegue para a pasta que contém o ficheiro de projeto principal.</span><span class="sxs-lookup"><span data-stu-id="75fa6-140">Navigate to the folder containing your main project file.</span></span>

2. <span data-ttu-id="75fa6-141">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="75fa6-141">Run the following command:</span></span>

    ```dotnetcli
    dotnet clean [project_name].csproj
    ```

3. <span data-ttu-id="75fa6-142">Determine a versão atual do QDK.</span><span class="sxs-lookup"><span data-stu-id="75fa6-142">Determine the current version of the QDK.</span></span> <span data-ttu-id="75fa6-143">Para isso, reveja as [notas de versão](https://docs.microsoft.com/quantum/relnotes/).</span><span class="sxs-lookup"><span data-stu-id="75fa6-143">To find it, you can review the [release notes](https://docs.microsoft.com/quantum/relnotes/).</span></span> <span data-ttu-id="75fa6-144">A versão estará num formato semelhante a `0.12.20072031`.</span><span class="sxs-lookup"><span data-stu-id="75fa6-144">The version will be in a format similar to `0.12.20072031`.</span></span>

4. <span data-ttu-id="75fa6-145">Em cada ficheiro `.csproj`, percorra os passos abaixo:</span><span class="sxs-lookup"><span data-stu-id="75fa6-145">In each of your `.csproj` files, go through the following steps:</span></span>

    - <span data-ttu-id="75fa6-146">Atualize o framework de destino para `netcoreapp3.1` (ou `netstandard2.1`, se for um projeto de biblioteca).</span><span class="sxs-lookup"><span data-stu-id="75fa6-146">Update the target framework to `netcoreapp3.1` (or `netstandard2.1` if it is a library project).</span></span> <span data-ttu-id="75fa6-147">Ou seja, edite as linhas do formulário:</span><span class="sxs-lookup"><span data-stu-id="75fa6-147">That is, edit lines of the form:</span></span>

        ```xml
        <TargetFramework>netcoreapp3.1</TargetFramework>
        ```

        <span data-ttu-id="75fa6-148">Pode obter mais detalhes sobre como especificar os frameworks de destino [aqui](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="75fa6-148">You can find more details on specifying target frameworks [here](https://docs.microsoft.com/dotnet/standard/frameworks#how-to-specify-target-frameworks).</span></span>

    - <span data-ttu-id="75fa6-149">Substitua a referência ao SDK na definição do projeto.</span><span class="sxs-lookup"><span data-stu-id="75fa6-149">Replace the reference to the SDK in the project definition.</span></span> <span data-ttu-id="75fa6-150">Confirme que o número da versão corresponde ao valor determinado no **passo 3**.</span><span class="sxs-lookup"><span data-stu-id="75fa6-150">Make sure that the version number corresponds to the value determined in **step 3**.</span></span>

        ```xml
        <Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
        ```

    - <span data-ttu-id="75fa6-151">Se presente, remova a referência ao pacote `Microsoft.Quantum.Development.Kit`, que será especificada na seguinte entrada:</span><span class="sxs-lookup"><span data-stu-id="75fa6-151">Remove the reference to package `Microsoft.Quantum.Development.Kit` if present, which will be specified in the following entry:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.10.1910.3107" />
        ```

    - <span data-ttu-id="75fa6-152">Atualize a versão de todos os pacotes do Microsoft Quantum para a mais recente do QDK (determinada no **passo 3**).</span><span class="sxs-lookup"><span data-stu-id="75fa6-152">Update the version of the all the Microsoft Quantum packages to the most recently released version of the QDK (determined in **step 3**).</span></span> <span data-ttu-id="75fa6-153">Esses pacotes seguem os padrões de nomenclatura abaixo:</span><span class="sxs-lookup"><span data-stu-id="75fa6-153">Those packages are named with the following patterns:</span></span>

        ```
        Microsoft.Quantum.*
        Microsoft.Azure.Quantum.*
        ```
    
        <span data-ttu-id="75fa6-154">As referências aos pacotes têm o formato seguinte:</span><span class="sxs-lookup"><span data-stu-id="75fa6-154">References to packages have the following format:</span></span>

        ```xml
        <PackageReference Include="Microsoft.Quantum.Compiler" Version="0.12.20072031" />
        ```

    - <span data-ttu-id="75fa6-155">Guarde o ficheiro atualizado.</span><span class="sxs-lookup"><span data-stu-id="75fa6-155">Save the updated file.</span></span>

    - <span data-ttu-id="75fa6-156">Restaure as dependências do projeto da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="75fa6-156">Restore the dependencies of the project, by doing the following:</span></span>

        ```dotnetcli
        dotnet restore [project_name].csproj
        ```

4. <span data-ttu-id="75fa6-157">Navegue para a pasta que contém o projeto principal e execute:</span><span class="sxs-lookup"><span data-stu-id="75fa6-157">Navigate back to the folder containing your main project and run:</span></span>

    ```dotnetcli
    dotnet build [project_name].csproj
    ```

<span data-ttu-id="75fa6-158">Com os projetos Q# já atualizados, siga as instruções abaixo para atualizar o próprio QDK.</span><span class="sxs-lookup"><span data-stu-id="75fa6-158">With your Q# projects now updated, follow the instructions below to update the QDK itself.</span></span>

## <a name="updating-the-qdk"></a><span data-ttu-id="75fa6-159">Atualizar o QDK</span><span class="sxs-lookup"><span data-stu-id="75fa6-159">Updating the QDK</span></span>

<span data-ttu-id="75fa6-160">O processo de atualização do QDK varia de acordo com a linguagem e o ambiente de desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="75fa6-160">The process to update the QDK varies depending on your development language and environment.</span></span>
<span data-ttu-id="75fa6-161">Selecione o seu ambiente de desenvolvimento abaixo:</span><span class="sxs-lookup"><span data-stu-id="75fa6-161">Select your development environment below.</span></span>

* [<span data-ttu-id="75fa6-162">Python: atualizar o pacote `qsharp`</span><span class="sxs-lookup"><span data-stu-id="75fa6-162">Python: update the `qsharp` package</span></span>](#update-the-qsharp-python-package)
* [<span data-ttu-id="75fa6-163">Jupyter Notebook: atualizar o kernel do IQ#</span><span class="sxs-lookup"><span data-stu-id="75fa6-163">Jupyter Notebooks: update the IQ# kernel</span></span>](#update-the-iq-jupyter-kernel)
* [<span data-ttu-id="75fa6-164">Visual Studio: atualizar a extensão QDK</span><span class="sxs-lookup"><span data-stu-id="75fa6-164">Visual Studio: update the QDK extension</span></span>](#update-visual-studio-qdk-extension)
* [<span data-ttu-id="75fa6-165">VS Code: atualizar a extensão QDK</span><span class="sxs-lookup"><span data-stu-id="75fa6-165">VS Code: update the QDK extension</span></span>](#update-vs-code-qdk-extension)
* [<span data-ttu-id="75fa6-166">Linha de comandos e C#: atualizar modelos de projeto</span><span class="sxs-lookup"><span data-stu-id="75fa6-166">Command line and C#: update project templates</span></span>](#c-using-the-dotnet-command-line-tool)


### <a name="update-the-qsharp-python-package"></a><span data-ttu-id="75fa6-167">Atualize o pacote `qsharp` do Python</span><span class="sxs-lookup"><span data-stu-id="75fa6-167">Update the `qsharp` Python package</span></span>

<span data-ttu-id="75fa6-168">O procedimento de atualização depende se instalou originalmente com o conda ou o .NET CLI e o pip.</span><span class="sxs-lookup"><span data-stu-id="75fa6-168">The update procedure depends on whether you originally installed using conda or using the .NET CLI and pip.</span></span>

#### <a name="update-using-conda-recommended"></a>[<span data-ttu-id="75fa6-169">Atualize com o conda (recomendado)</span><span class="sxs-lookup"><span data-stu-id="75fa6-169">Update using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="75fa6-170">Ative o ambiente conda onde instalou o pacote `qsharp` e, em seguida, execute este comando para atualizá-lo:</span><span class="sxs-lookup"><span data-stu-id="75fa6-170">Activate the conda environment where you installed the `qsharp` package, and then run this command to update it:</span></span>

    ```
    conda update -c quantum-engineering qsharp
    ```

1. <span data-ttu-id="75fa6-171">Execute o seguinte comando a partir da localização dos ficheiros `.qs`:</span><span class="sxs-lookup"><span data-stu-id="75fa6-171">Run the following command from the location of your `.qs` files:</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="75fa6-172">Atualize com o .NET CLI e o pip (avançado)</span><span class="sxs-lookup"><span data-stu-id="75fa6-172">Update using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="75fa6-173">Atualize o kernel `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="75fa6-173">Update the `iqsharp` kernel</span></span> 

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="75fa6-174">Verifique a versão de `iqsharp`</span><span class="sxs-lookup"><span data-stu-id="75fa6-174">Verify the `iqsharp` version</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="75fa6-175">Deverá ver o resultado seguinte:</span><span class="sxs-lookup"><span data-stu-id="75fa6-175">You should see the following output:</span></span>

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    <span data-ttu-id="75fa6-176">Não se preocupe se a sua versão de `iqsharp` for superior.</span><span class="sxs-lookup"><span data-stu-id="75fa6-176">Don't worry if your `iqsharp` version is higher.</span></span> <span data-ttu-id="75fa6-177">Deve corresponder à [versão mais recente](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="75fa6-177">It should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

1. <span data-ttu-id="75fa6-178">Atualize o pacote `qsharp`:</span><span class="sxs-lookup"><span data-stu-id="75fa6-178">Update the `qsharp` package:</span></span>

    ```
    pip install qsharp --upgrade
    ```

1. <span data-ttu-id="75fa6-179">Verifique a versão de `qsharp`:</span><span class="sxs-lookup"><span data-stu-id="75fa6-179">Verify the `qsharp` version:</span></span>

    ```
    pip show qsharp
    ```

    <span data-ttu-id="75fa6-180">Deverá ver o resultado seguinte:</span><span class="sxs-lookup"><span data-stu-id="75fa6-180">You should see the following output:</span></span>

    ```
    Name: qsharp
    Version: 0.12.2007.2031
    Summary: Python client for Q#, a domain-specific quantum programming language
    ...
    ```

1. <span data-ttu-id="75fa6-181">Execute o seguinte comando a partir da localização dos ficheiros `.qs`:</span><span class="sxs-lookup"><span data-stu-id="75fa6-181">Run the following command from the location of your `.qs` files:</span></span>

    ```
    python -c "import qsharp; qsharp.reload()"
    ```

***

<span data-ttu-id="75fa6-182">Agora, pode utilizar o pacote `qsharp` do Python para executar os seus programas quânticos já existentes.</span><span class="sxs-lookup"><span data-stu-id="75fa6-182">You can now use the updated `qsharp` Python package to run your existing quantum programs.</span></span>

### <a name="update-the-ino-locq-jupyter-kernel"></a><span data-ttu-id="75fa6-183">Atualize o kernel do IQ# Jupyter</span><span class="sxs-lookup"><span data-stu-id="75fa6-183">Update the IQ# Jupyter kernel</span></span>

<span data-ttu-id="75fa6-184">O procedimento de atualização depende se instalou originalmente com o conda ou o .NET CLI e o pip.</span><span class="sxs-lookup"><span data-stu-id="75fa6-184">The update procedure depends on whether you originally installed using conda or using the .NET CLI and pip.</span></span>

#### <a name="update-using-conda-recommended"></a>[<span data-ttu-id="75fa6-185">Atualize com o conda (recomendado)</span><span class="sxs-lookup"><span data-stu-id="75fa6-185">Update using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="75fa6-186">Ative o ambiente conda onde instalou o pacote `qsharp` e, em seguida, execute este comando para atualizá-lo:</span><span class="sxs-lookup"><span data-stu-id="75fa6-186">Activate the conda environment where you installed the `qsharp` package, and then run this command to update it:</span></span>

    ```
    conda update -c quantum-engineering qsharp
    ```

1. <span data-ttu-id="75fa6-187">Execute o seguinte comando a partir de uma célula em cada Q# Jupyter Notebook existente:</span><span class="sxs-lookup"><span data-stu-id="75fa6-187">Run the following command from a cell in each of your existing Q# Jupyter Notebooks:</span></span>

    ```
    %workspace reload
    ```

#### <a name="update-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="75fa6-188">Atualize com o .NET CLI e o pip (avançado)</span><span class="sxs-lookup"><span data-stu-id="75fa6-188">Update using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="75fa6-189">Atualize o pacote `Microsoft.Quantum.IQSharp`:</span><span class="sxs-lookup"><span data-stu-id="75fa6-189">Update the `Microsoft.Quantum.IQSharp` package:</span></span>

    ```dotnetcli
    dotnet tool update -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="75fa6-190">Verifique a versão de `iqsharp`:</span><span class="sxs-lookup"><span data-stu-id="75fa6-190">Verify the `iqsharp` version:</span></span>

    ```dotnetcli
    dotnet iqsharp --version
    ```

    <span data-ttu-id="75fa6-191">A saída deve ser semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="75fa6-191">Your output should be similar to the following:</span></span>

    ```
    iqsharp: 0.12.20072031
    Jupyter Core: 1.4.0.0
    ```

    <span data-ttu-id="75fa6-192">Não se preocupe se a sua versão de `iqsharp` for superior.</span><span class="sxs-lookup"><span data-stu-id="75fa6-192">Don't worry if your `iqsharp` version is higher.</span></span> <span data-ttu-id="75fa6-193">Deve corresponder à [versão mais recente](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="75fa6-193">It should match the [latest release](xref:microsoft.quantum.relnotes).</span></span>

1. <span data-ttu-id="75fa6-194">Execute o seguinte comando a partir de uma célula em cada Q# Jupyter Notebook existente:</span><span class="sxs-lookup"><span data-stu-id="75fa6-194">Run the following command from a cell in each of your existing Q# Jupyter Notebooks:</span></span>

    ```
    %workspace reload
    ```

<span data-ttu-id="75fa6-195">\*\*_</span><span class="sxs-lookup"><span data-stu-id="75fa6-195">\*\*_</span></span>

<span data-ttu-id="75fa6-196">Agora, pode utilizar o kernel do IQ# atualizado para executar cada Q# Jupyter Notebook existente.</span><span class="sxs-lookup"><span data-stu-id="75fa6-196">You can now use the updated IQ# kernel to run your existing Q# Jupyter Notebooks.</span></span>

### <a name="update-visual-studio-qdk-extension"></a><span data-ttu-id="75fa6-197">Atualizar a extensão QDK do Visual Studio</span><span class="sxs-lookup"><span data-stu-id="75fa6-197">Update Visual Studio QDK extension</span></span>

1. <span data-ttu-id="75fa6-198">Atualizar a extensão Q# do Visual Studio</span><span class="sxs-lookup"><span data-stu-id="75fa6-198">Update the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="75fa6-199">O Visual Studio pede-lhe que aceite as atualizações à [extensão Quantum do Visual Studio](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span><span class="sxs-lookup"><span data-stu-id="75fa6-199">Visual Studio prompts you to accept updates to the [Quantum Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="75fa6-200">Aceite a atualização</span><span class="sxs-lookup"><span data-stu-id="75fa6-200">Accept the update</span></span>

    > [!NOTE]
    > <span data-ttu-id="75fa6-201">Os modelos de projetos são atualizados com a extensão</span><span class="sxs-lookup"><span data-stu-id="75fa6-201">The project templates are updated with the extension.</span></span> <span data-ttu-id="75fa6-202">e só se aplicam a projetos recém-criados.</span><span class="sxs-lookup"><span data-stu-id="75fa6-202">The updated templates apply to newly created projects only.</span></span> <span data-ttu-id="75fa6-203">O código dos projetos já existentes não é atualizado quando a extensão é atualizada.</span><span class="sxs-lookup"><span data-stu-id="75fa6-203">The code for your existing projects is not updated when the extension is updated.</span></span>

### <a name="update-vs-code-qdk-extension"></a><span data-ttu-id="75fa6-204">Atualizar a extensão QDK do VS Code</span><span class="sxs-lookup"><span data-stu-id="75fa6-204">Update VS Code QDK extension</span></span>

1. <span data-ttu-id="75fa6-205">Atualize a extensão Quantum do VS Code</span><span class="sxs-lookup"><span data-stu-id="75fa6-205">Update the Quantum VS Code extension</span></span>

    - <span data-ttu-id="75fa6-206">Reinicie o VS Code</span><span class="sxs-lookup"><span data-stu-id="75fa6-206">Restart VS Code</span></span>
    - <span data-ttu-id="75fa6-207">Navegar para o separador _ *Extensões*\*</span><span class="sxs-lookup"><span data-stu-id="75fa6-207">Navigate to the _ *Extensions*\* tab</span></span>
    - <span data-ttu-id="75fa6-208">Selecione a extensão **Microsoft Quantum Development Kit for Visual Studio Code**</span><span class="sxs-lookup"><span data-stu-id="75fa6-208">Select the **Microsoft Quantum Development Kit for Visual Studio Code** extension</span></span>
    - <span data-ttu-id="75fa6-209">Recarregue a extensão</span><span class="sxs-lookup"><span data-stu-id="75fa6-209">Reload the extension</span></span>

### <a name="c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="75fa6-210">C# com a ferramenta de linha de comandos `dotnet`</span><span class="sxs-lookup"><span data-stu-id="75fa6-210">C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="75fa6-211">Atualize os modelos de projetos quânticos para .NET</span><span class="sxs-lookup"><span data-stu-id="75fa6-211">Update the Quantum project templates for .NET</span></span>

    <span data-ttu-id="75fa6-212">Na linha de comandos:</span><span class="sxs-lookup"><span data-stu-id="75fa6-212">From the command prompt:</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

   <span data-ttu-id="75fa6-213">Em alternativa, se quiser utilizar os modelos da linha de comandos e já tiver a extensão QDK do VS Code instalada, pode atualizar os modelos de projeto a partir da própria extensão:</span><span class="sxs-lookup"><span data-stu-id="75fa6-213">Alternatively, if you intend to use the command-line templates, and already have the VS Code QDK extension installed, you can update the project templates from the extension itself:</span></span>

   - [<span data-ttu-id="75fa6-214">Atualizar a extensão QDK</span><span class="sxs-lookup"><span data-stu-id="75fa6-214">Update the QDK extension</span></span>](#update-vs-code-qdk-extension)
   - <span data-ttu-id="75fa6-215">No VS Code, vá para **Ver** -> **Paleta de Comandos**</span><span class="sxs-lookup"><span data-stu-id="75fa6-215">In VS Code, go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="75fa6-216">Selecione **Q#: Instalar modelos de projeto da linha de comandos**</span><span class="sxs-lookup"><span data-stu-id="75fa6-216">Select **Q#: Install command line project templates**</span></span>
   - <span data-ttu-id="75fa6-217">Ao fim de alguns segundos, deverá receber um pop-up com a mensagem "project templates installed successfully" ("modelos de projetos instalados com êxito")</span><span class="sxs-lookup"><span data-stu-id="75fa6-217">After a few seconds you should get a popup confirming "project templates installed successfully"</span></span>
