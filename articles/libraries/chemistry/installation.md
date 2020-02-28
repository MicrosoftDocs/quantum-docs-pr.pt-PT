---
title: Microsoft Q# Instalação e Validação da Biblioteca de Química
description: Aprenda a instalar a biblioteca de química Quantum da Microsoft e use-a com a plataforma de química computacional NWChem.
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: 48bf7bc980e238e622053f5c2bdd09604c572596
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907363"
---
# <a name="chemistry-library-installation-and-validation"></a><span data-ttu-id="5b53e-103">Instalação e Validação da Biblioteca química</span><span class="sxs-lookup"><span data-stu-id="5b53e-103">Chemistry Library Installation and Validation</span></span>

<span data-ttu-id="5b53e-104">O Kit de Desenvolvimento Quântico fornece suporte para aplicações de química quântica através do pacote [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) NuGet.</span><span class="sxs-lookup"><span data-stu-id="5b53e-104">The Quantum Development Kit provides support for quantum chemistry applications through the [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) NuGet package.</span></span>
<span data-ttu-id="5b53e-105">Tal como acontece com outros pacotes NuGet, é simples adicionar a biblioteca de química ao seu projeto.</span><span class="sxs-lookup"><span data-stu-id="5b53e-105">As with other NuGet packages, it's straightforward to add the chemistry library to your project.</span></span>

<span data-ttu-id="5b53e-106">**Estúdio Visual 2019:** Se estiver a usar o Visual Studio 2019, pode adicionar os pacotes de química quântica utilizando o NuGet Package Manager.</span><span class="sxs-lookup"><span data-stu-id="5b53e-106">**Visual Studio 2019:** If you are using Visual Studio 2019, you can add the quantum chemistry packages by using the NuGet Package Manager.</span></span>
<span data-ttu-id="5b53e-107">Para abrir o Gestor de Pacotes, clique no projeto que gostaria de adicionar a biblioteca de química e selecionar "Gerir pacotes NuGet...", como na imagem abaixo.</span><span class="sxs-lookup"><span data-stu-id="5b53e-107">To open the Package Manager, right-click on the project you'd like to add the chemistry library to and select "Manage NuGet Packages...," as in the screenshot below.</span></span>

![Utilização do NuGet Package Manager no Visual Studio 2019](~/media/vs2017-nuget-manage-packages.png)

<span data-ttu-id="5b53e-109">A partir do separador Browse, procure o nome de pacote "Microsoft.Quantum.Chemistry".</span><span class="sxs-lookup"><span data-stu-id="5b53e-109">From the Browse tab, search for the package name "Microsoft.Quantum.Chemistry."</span></span>

> [!NOTE]
> <span data-ttu-id="5b53e-110">Certifique-se de marcar "Incluir pré-lançamento".</span><span class="sxs-lookup"><span data-stu-id="5b53e-110">Make sure to tick "Include prerelease."</span></span>

![Incluir caixa de verificação pré-lançamento](~/media/vs2017-nuget-package-search.png)

<span data-ttu-id="5b53e-112">Isto listará os pacotes disponíveis para download.</span><span class="sxs-lookup"><span data-stu-id="5b53e-112">This will list the packages available for download.</span></span>
<span data-ttu-id="5b53e-113">Clique no "Microsoft.Quantum.Chemistry on the left-handpane, select the latest pré-release version on the right-hand pane" e clique em "Instalar":</span><span class="sxs-lookup"><span data-stu-id="5b53e-113">Click on the "Microsoft.Quantum.Chemistry on the left-hand pane, select the latest pre-release version on the right-hand pane, and click "Install":</span></span>

![Instale o mais recente pacote Microsoft.Quantum.Chemistry](~/media/vs2017-nuget-select-chem.png)

<span data-ttu-id="5b53e-115">Para mais detalhes, consulte o [guia UI do Gestor](https://docs.microsoft.com/nuget/tools/package-manager-ui)de Pacotes.</span><span class="sxs-lookup"><span data-stu-id="5b53e-115">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="5b53e-116">Em alternativa, pode utilizar a Consola de Gestor de Pacotes para adicionar a biblioteca de química quântica ao seu projeto com uma interface de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="5b53e-116">Alternatively, you can use the Package Manager Console to add the quantum chemistry library to your project with a command line interface.</span></span>

![Utilize a consola gestora de pacotes a partir da linha de comando](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="5b53e-118">A partir da consola gestora de pacotes, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5b53e-118">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Chemistry
```

<span data-ttu-id="5b53e-119">Para mais detalhes, consulte o guia de [consolas do Gestor](https://docs.microsoft.com/nuget/tools/package-manager-console)de Pacotes .</span><span class="sxs-lookup"><span data-stu-id="5b53e-119">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="5b53e-120">**Linha de comando ou Código** de Estúdio Visual: Utilizando a linha de comando por si só ou dentro do Código visual do Estúdio, pode utilizar o comando `dotnet` para adicionar referência ao pacote NuGet ao seu projeto:</span><span class="sxs-lookup"><span data-stu-id="5b53e-120">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Chemistry
```

## <a name="verifying-your-installation"></a><span data-ttu-id="5b53e-121">Verificação da sua instalação</span><span class="sxs-lookup"><span data-stu-id="5b53e-121">Verifying Your Installation</span></span> 

<span data-ttu-id="5b53e-122">Tal como o resto do Kit de Desenvolvimento Quântico, a biblioteca de química quântica vem com uma série de amostras totalmente documentadas para ajudá-lo a levantar-se e a funcionar rapidamente.</span><span class="sxs-lookup"><span data-stu-id="5b53e-122">Like the rest of the Quantum Development Kit, the quantum chemistry library comes with a number of fully documented samples to help you get up and running quickly.</span></span>
<span data-ttu-id="5b53e-123">Para testar a sua instalação utilizando estas amostras, clone o [repositório de amostras principais](https://github.com/Microsoft/Quantum)e, em seguida, execute uma das amostras.</span><span class="sxs-lookup"><span data-stu-id="5b53e-123">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum), then run one of the samples.</span></span>  <span data-ttu-id="5b53e-124">Por exemplo, executar a amostra [`MolecularHydrogen`:](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen)</span><span class="sxs-lookup"><span data-stu-id="5b53e-124">For example, to run the [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/chemistry/MolecularHydrogen
dotnet run
```

<span data-ttu-id="5b53e-125">Para verificar a instalação da biblioteca de química quântica utilizando o Microsoft Visual Studio após a clonagem do repositório:</span><span class="sxs-lookup"><span data-stu-id="5b53e-125">To verify the installation of the quantum chemistry library using Microsoft Visual Studio after cloning the repository:</span></span>
    1. <span data-ttu-id="5b53e-126">Abra a solução ChemistrySamples.sLN na pasta Chemistry.</span><span class="sxs-lookup"><span data-stu-id="5b53e-126">Open the ChemistrySamples.sln solution in the Chemistry folder.</span></span>  
    2. <span data-ttu-id="5b53e-127">Selecione Amostras/1.</span><span class="sxs-lookup"><span data-stu-id="5b53e-127">Select Samples/1.</span></span> <span data-ttu-id="5b53e-128">Moléculas Simples/MolecularHydrogen como o projeto StartUp.</span><span class="sxs-lookup"><span data-stu-id="5b53e-128">Simple Molecules/MolecularHydrogen as the StartUp project.</span></span>
    3. <span data-ttu-id="5b53e-129">Pressione F5 para executar a demonstração molecular de estimativa da fase quântica do hidrogénio.</span><span class="sxs-lookup"><span data-stu-id="5b53e-129">Press F5 to run the molecular Hydrogen quantum phase estimation demo.</span></span>

<span data-ttu-id="5b53e-130">Consulte [a obtenção de estimativas](xref:microsoft.quantum.chemistry.examples.energyestimate) de nível de energia para obter mais informações sobre a estimativa dos valores dos níveis de energia.</span><span class="sxs-lookup"><span data-stu-id="5b53e-130">See [Obtaining energy level estimates](xref:microsoft.quantum.chemistry.examples.energyestimate) for more information on estimating the values of energy levels.</span></span>   


## <a name="using-the-quantum-development-kit-with-nwchem"></a><span data-ttu-id="5b53e-131">Usando o Kit de Desenvolvimento Quântico com NWChem</span><span class="sxs-lookup"><span data-stu-id="5b53e-131">Using the Quantum Development Kit with NWChem</span></span> ##

<span data-ttu-id="5b53e-132">A amostra MolecularHydrogen utiliza dados de entrada molecular que são configurados manualmente.</span><span class="sxs-lookup"><span data-stu-id="5b53e-132">The MolecularHydrogen sample uses molecular input data that is manually configured.</span></span>  <span data-ttu-id="5b53e-133">Embora isto seja bom para pequenos exemplos, a química quântica em escala requer hamiltonianos com milhões ou biliões de mandatos.</span><span class="sxs-lookup"><span data-stu-id="5b53e-133">While this is fine for small examples, quantum chemistry at scale require Hamiltonians with millions or billions of terms.</span></span> <span data-ttu-id="5b53e-134">Tais hamiltonianos, gerados por pacotes de química computacional escalável são demasiado grandes para serem importados à mão.</span><span class="sxs-lookup"><span data-stu-id="5b53e-134">Such Hamiltonians, generated by scalable computational chemistry packages are too large to import by hand.</span></span> 

<span data-ttu-id="5b53e-135">A biblioteca de química quântica para o Kit de Desenvolvimento Quântico foi projetada para funcionar bem com pacotes de química computacional, mais notavelmente a plataforma de química computacional [**NWChem**](http://www.nwchem-sw.org/) desenvolvida pelo Laboratório de Ciências Moleculares Ambientais (EMSL) no Laboratório Nacional do Noroeste do Pacífico.</span><span class="sxs-lookup"><span data-stu-id="5b53e-135">The quantum chemistry library for the Quantum Development Kit is designed to work well with computational chemistry packages, most notably the [**NWChem**](http://www.nwchem-sw.org/) computational chemistry platform developed by the Environmental Molecular Sciences Laboratory (EMSL) at Pacific Northwest National Laboratory.</span></span>
<span data-ttu-id="5b53e-136">Em particular, o pacote `Microsoft.Quantum.Chemistry` fornece ferramentas para carregar casos de problemas de simulação de química quântica representados no esquema de [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), também suportado para exportação por versões recentes da NWChem.</span><span class="sxs-lookup"><span data-stu-id="5b53e-136">In particular, the `Microsoft.Quantum.Chemistry` package provides tools for loading instances of quantum chemistry simulation problems represented in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), also supported for export by recent versions of NWChem.</span></span>

<span data-ttu-id="5b53e-137">Para se levantar e funcionar usando a NWChem juntamente com o Kit de Desenvolvimento Quântico, sugerimos um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="5b53e-137">To get up and running using NWChem together with the Quantum Development Kit, we suggest one of the following methods:</span></span>
- <span data-ttu-id="5b53e-138">Começar a utilizar ficheiros Broombridge existentes fornecidos com as amostras em [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML).</span><span class="sxs-lookup"><span data-stu-id="5b53e-138">Get started using existing Broombridge files provided with the samples at [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML).</span></span>
- <span data-ttu-id="5b53e-139">Utilize o [emslômico](https://arrows.emsl.pnnl.gov/api/qsharp_chem) de setas para o Kit de Desenvolvimento Quântico da Microsoft, que é um frontend baseado na web para a NWChem, para gerar novos ficheiros de entrada molecular formados em Broombridge.</span><span class="sxs-lookup"><span data-stu-id="5b53e-139">Use the [EMSL Arrows Builder for the Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) which is a web-based frontend to NWChem, to generate new Broombridge-formated molecular input files.</span></span>  
- <span data-ttu-id="5b53e-140">Use a [imagem Docker](https://hub.docker.com/r/nwchemorg/nwchem-qc/) fornecida pela PNNL para executar NWChem, ou</span><span class="sxs-lookup"><span data-stu-id="5b53e-140">Use the [Docker image](https://hub.docker.com/r/nwchemorg/nwchem-qc/) provided by PNNL to run NWChem, or</span></span>
- <span data-ttu-id="5b53e-141">[Compile a NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) para a sua plataforma.</span><span class="sxs-lookup"><span data-stu-id="5b53e-141">[Compile NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) for your platform.</span></span>

<span data-ttu-id="5b53e-142">Consulte [o End-to-End com](xref:microsoft.quantum.chemistry.examples.endtoend) a NWChem para obter mais informações sobre como trabalhar com a NWChem para modelos químicos para analisar com a biblioteca de química Quantum Developmen Kit.</span><span class="sxs-lookup"><span data-stu-id="5b53e-142">See [End-to-end with NWChem](xref:microsoft.quantum.chemistry.examples.endtoend) for more information on how to work with NWChem to chemical models to analyze with the Quantum Developmen Kit chemistry library.</span></span>

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a><span data-ttu-id="5b53e-143">Começar a usar ficheiros Broombridge fornecidos com as amostras</span><span class="sxs-lookup"><span data-stu-id="5b53e-143">Getting started using Broombridge files provided with the samples</span></span>

<span data-ttu-id="5b53e-144">A pasta [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) no repositório de amostras do kit de desenvolvimento quântico contém ficheiros de dados de moléculas formados por Broombridge.</span><span class="sxs-lookup"><span data-stu-id="5b53e-144">The [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) folder in the Quantum Development Kit Samples repository contains Broombridge-formated molecule data files.</span></span>  

<span data-ttu-id="5b53e-145">Como um exemplo simples, use a amostra da biblioteca de química, [GetGateCount](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/GetGateCount) para carregar o Hamiltonian a partir de um dos ficheiros broombridge e executar estimativas de porta de algorigthms de simulação quântica:</span><span class="sxs-lookup"><span data-stu-id="5b53e-145">As a simple example, use the chemistry library sample, [GetGateCount](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/GetGateCount) to load the Hamiltonian from one of Broombridge files and perform gate estimates of quantum simulation algorigthms:</span></span>

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

<span data-ttu-id="5b53e-146">Veja [o Loading a Hamiltonian do arquivo](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) para obter mais informações sobre como inserir moléculas representadas pelo esquema de Broombridge.</span><span class="sxs-lookup"><span data-stu-id="5b53e-146">See [Loading a Hamiltonian from file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) for more information on how to input molecules represented by the Broombridge schema.</span></span>  

<span data-ttu-id="5b53e-147">Ver [Obtenção de recursos conta para](xref:microsoft.quantum.chemistry.examples.resourcecounts) obter mais informações sobre a estimativa de recursos.</span><span class="sxs-lookup"><span data-stu-id="5b53e-147">See [Obtaining resource counts](xref:microsoft.quantum.chemistry.examples.resourcecounts) for more information on resource estimation.</span></span>  

### <a name="getting-started-using-the-emsl-arrows-builder"></a><span data-ttu-id="5b53e-148">Começar a usar o construtor de setas EMSL</span><span class="sxs-lookup"><span data-stu-id="5b53e-148">Getting started using the EMSL Arrows Builder</span></span>

<span data-ttu-id="5b53e-149">EmSL Arrows é uma ferramenta que usa BASES de dados computacionais NWChem e químicas para gerar dados de moléculas.</span><span class="sxs-lookup"><span data-stu-id="5b53e-149">EMSL Arrows is a tool that uses NWChem and chemical computational databases to generate molecule data.</span></span>  <span data-ttu-id="5b53e-150">[O EMSL Arrows Builder para o Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) de Desenvolvimento Quântico da Microsoft permite-lhe entrar no seu modelo usando vários construtores de modelos moleculares e gerar o ficheiro de dados de Broombridge para ser usado pelo Kit de Desenvolvimento Quântico.</span><span class="sxs-lookup"><span data-stu-id="5b53e-150">[EMSL Arrows Builder for the Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) allows you to enter your model using multiple molecular model builders and generate the Broombridge datafile to be used by the Quantum Development Kit.</span></span>  

<span data-ttu-id="5b53e-151">A partir da página EMSL, clique no separador ['Instuctions'] e siga as instruções ['Exemplos Simples' para gerar ficheiros Broombridge.</span><span class="sxs-lookup"><span data-stu-id="5b53e-151">From the EMSL page, click on the ['Instuctions'] tab, and follow the ['Simple Examples'] instructions to generate Broombridge files.</span></span>  <span data-ttu-id="5b53e-152">Em seguida, tente executar o ['GetGateCount'] para ver as estimativas de recursos quânticos para estas moléculas.</span><span class="sxs-lookup"><span data-stu-id="5b53e-152">Then try running the ['GetGateCount'] to see the quantum resource estimates for these molecules.</span></span>

### <a name="installing-nwchem-from-source"></a><span data-ttu-id="5b53e-153">Instalação NWChem a partir da Fonte</span><span class="sxs-lookup"><span data-stu-id="5b53e-153">Installing NWChem from Source</span></span>

<span data-ttu-id="5b53e-154">Instruções completas sobre como instalar a NWChem a partir da fonte [são fornecidas pela PNNL](http://www.nwchem-sw.org/index.php/Compiling_NWChem).</span><span class="sxs-lookup"><span data-stu-id="5b53e-154">Full instructions on how to install NWChem from source [are provided by PNNL](http://www.nwchem-sw.org/index.php/Compiling_NWChem).</span></span>

> [!TIP]
> <span data-ttu-id="5b53e-155">Se desejar utilizar o NWChem a partir do Windows 10, o Subsistema Windows para O Linux é uma excelente opção.</span><span class="sxs-lookup"><span data-stu-id="5b53e-155">If you wish to use NWChem from Windows 10, the Windows Subsystem for Linux is a great option.</span></span>
> <span data-ttu-id="5b53e-156">Depois de ter instalado [ubuntu 18.04 LTS para Windows,](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab)faça `ubuntu18.04` do seu terminal favorito e siga as instruções acima para instalar a NWChem a partir da fonte.</span><span class="sxs-lookup"><span data-stu-id="5b53e-156">Once you have installed [Ubuntu 18.04 LTS for Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab), run `ubuntu18.04` from your favorite terminal and follow the instructions above to install NWChem from source.</span></span>

<span data-ttu-id="5b53e-157">Uma vez compilado o NWChem de origem, pode executar o `yaml_driver` script fornecido com NWChem para produzir rapidamente casos de Broombridge a partir de decks de entrada NWChem:</span><span class="sxs-lookup"><span data-stu-id="5b53e-157">Once you have compiled NWChem from source, you can run the `yaml_driver` script provided with NWChem to quickly produce Broombridge instances from NWChem input decks:</span></span>

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

<span data-ttu-id="5b53e-158">Este comando criará um novo ficheiro `input.yaml` no formato Broombridge dentro do seu diretório atual.</span><span class="sxs-lookup"><span data-stu-id="5b53e-158">This command will create a new `input.yaml` file in the Broombridge format within your current directory.</span></span>

### <a name="using-nwchem-with-docker"></a><span data-ttu-id="5b53e-159">Usando NWChem com Docker</span><span class="sxs-lookup"><span data-stu-id="5b53e-159">Using NWChem with Docker</span></span>

<span data-ttu-id="5b53e-160">Imagens pré-construídas para utilização da NWChem estão disponíveis através da plataforma cruzada via [Docker Hub](https://hub.docker.com).</span><span class="sxs-lookup"><span data-stu-id="5b53e-160">Pre-built images for using NWChem are available cross-platform via [Docker Hub](https://hub.docker.com).</span></span>
<span data-ttu-id="5b53e-161">Para começar, siga as instruções de instalação do Docker para a sua plataforma:</span><span class="sxs-lookup"><span data-stu-id="5b53e-161">To get started, follow the Docker installation instructions for your platform:</span></span>

- [<span data-ttu-id="5b53e-162">Instalar Docker para Ubuntu</span><span class="sxs-lookup"><span data-stu-id="5b53e-162">Install Docker for Ubuntu</span></span>](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [<span data-ttu-id="5b53e-163">Instalar Docker para macOS</span><span class="sxs-lookup"><span data-stu-id="5b53e-163">Install Docker for macOS</span></span>](https://docs.docker.com/docker-for-mac/install/)
- [<span data-ttu-id="5b53e-164">Instale docker para windows 10</span><span class="sxs-lookup"><span data-stu-id="5b53e-164">Install Docker for Windows 10</span></span>](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> <span data-ttu-id="5b53e-165">Se estiver a utilizar o Docker para windows, terá de partilhar a unidade que contém o seu diretório temporário (normalmente este é o `C:\` unidade) com o daemon do Docker.</span><span class="sxs-lookup"><span data-stu-id="5b53e-165">If you are using Docker for Windows, you will need to share the drive containing your temporary directory (usually this is the `C:\` drive) with the Docker daemon.</span></span> <span data-ttu-id="5b53e-166">Consulte a [documentação](https://docs.docker.com/docker-for-windows/#shared-drives) do Docker para mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="5b53e-166">See the [Docker documentation](https://docs.docker.com/docker-for-windows/#shared-drives) for more details.</span></span>

<span data-ttu-id="5b53e-167">Uma vez instalado o Docker, pode utilizar o módulo PowerShell fornecido com as amostras do Quantum Development Kit para executar a imagem, ou pode executar a imagem manualmente.</span><span class="sxs-lookup"><span data-stu-id="5b53e-167">Once you have Docker installed, you can either use the PowerShell module provided with the Quantum Development Kit samples to run the image, or you can run the image manually.</span></span>
<span data-ttu-id="5b53e-168">Detalhamos a utilização do PowerShell aqui; se quiser utilizar manualmente a imagem do Docker, consulte a [documentação fornecida com a imagem](https://hub.docker.com/r/nwchemorg/nwchem-qc/).</span><span class="sxs-lookup"><span data-stu-id="5b53e-168">We detail using PowerShell here; if you would like to use the Docker image manually, please see the [documentation provided with the image](https://hub.docker.com/r/nwchemorg/nwchem-qc/).</span></span>

#### <a name="running-nwchem-through-powershell-core"></a><span data-ttu-id="5b53e-169">Executando NWChem através do PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="5b53e-169">Running NWChem through PowerShell Core</span></span>

<span data-ttu-id="5b53e-170">Para utilizar a imagem NWChem Docker com o Kit de Desenvolvimento Quântico, fornecemos um pequeno módulo PowerShell que lida com ficheiros em movimento dentro e fora da NWChem para si.</span><span class="sxs-lookup"><span data-stu-id="5b53e-170">To use the NWChem Docker image with the Quantum Development Kit, we provide a small PowerShell module that handles moving files in and out of NWChem for you.</span></span>
<span data-ttu-id="5b53e-171">Se ainda não tiver o PowerShell Core instalado, pode descarregá-lo através da plataforma transversal a partir do [repositório PowerShell no GitHub](https://github.com/PowerShell/PowerShell#get-powershell).</span><span class="sxs-lookup"><span data-stu-id="5b53e-171">If you don't already have PowerShell Core installed, you can download it cross-platform from the [PowerShell repository on GitHub](https://github.com/PowerShell/PowerShell#get-powershell).</span></span>

> [!NOTE]
> <span data-ttu-id="5b53e-172">O PowerShell Core também é usado para algumas amostras para demonstrar interoperabilidade com a ciência dos dados e fluxos de trabalho de análise de negócios.</span><span class="sxs-lookup"><span data-stu-id="5b53e-172">PowerShell Core is also used for some samples to demonstrate interoperability with data science and business analytics workflows.</span></span>

<span data-ttu-id="5b53e-173">Assim que tiver o PowerShell Core instalado, importe `InvokeNWChem.psm1` para disponibilizar comandos NWChem na sua sessão atual:</span><span class="sxs-lookup"><span data-stu-id="5b53e-173">Once you have PowerShell Core installed, import `InvokeNWChem.psm1` to make NWChem commands available in your current session:</span></span>

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

<span data-ttu-id="5b53e-174">Isto disponibilizará o comando `Convert-NWChemToBroombridge` na sua atual sessão PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5b53e-174">This will make the `Convert-NWChemToBroombridge` command available in your current PowerShell session.</span></span>
<span data-ttu-id="5b53e-175">Para descarregar quaisquer imagens necessárias do Docker e usá-las para executar decks de entrada NWChem e capturar a saída para Broombridge, executar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5b53e-175">To download any needed images from Docker and use them to run NWChem input decks and capture output to Broombridge, run the following:</span></span>

```powershell
Convert-NWChemToBroombridge ./input.nw
```

<span data-ttu-id="5b53e-176">Isto criará um ficheiro Broombridge executando a NWChem na `input.nw`.</span><span class="sxs-lookup"><span data-stu-id="5b53e-176">This will create a Broombridge file by running NWChem on `input.nw`.</span></span>
<span data-ttu-id="5b53e-177">Por predefinição, a saída de Broombridge terá o mesmo nome e caminho que o convés de entrada, com a extensão `.nw` substituída por `.yaml`.</span><span class="sxs-lookup"><span data-stu-id="5b53e-177">By default, the Broombridge output will have the same name and path as the input deck, with the `.nw` extension replaced by `.yaml`.</span></span>
<span data-ttu-id="5b53e-178">Isto pode ser ultrapassado utilizando o parâmetro `-DestinationPath` para `Convert-NWChemToBroombridge`.</span><span class="sxs-lookup"><span data-stu-id="5b53e-178">This can be overridden by using the `-DestinationPath` parameter to `Convert-NWChemToBroombridge`.</span></span>
<span data-ttu-id="5b53e-179">Mais informações podem ser obtidas utilizando a funcionalidade de ajuda incorporada da PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5b53e-179">More information can be obtained by using PowerShell's built-in help functionality:</span></span>

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```
