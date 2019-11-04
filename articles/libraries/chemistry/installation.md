---
title: Instalação e validação da biblioteca de química | Microsoft Docs
description: Instalação e validação da biblioteca de química
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: fd43c783fa82c7219e143a57759919606fdd197f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184207"
---
# <a name="chemistry-library-installation-and-validation"></a><span data-ttu-id="8bc8a-103">Instalação e validação da biblioteca de química</span><span class="sxs-lookup"><span data-stu-id="8bc8a-103">Chemistry Library Installation and Validation</span></span>

<span data-ttu-id="8bc8a-104">O kit de desenvolvimento Quantum fornece suporte para aplicativos químicas da Quantum por meio do pacote NuGet [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) .</span><span class="sxs-lookup"><span data-stu-id="8bc8a-104">The Quantum Development Kit provides support for quantum chemistry applications through the [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) NuGet package.</span></span>
<span data-ttu-id="8bc8a-105">Assim como acontece com outros pacotes NuGet, é simples adicionar a biblioteca química ao seu projeto.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-105">As with other NuGet packages, it's straightforward to add the chemistry library to your project.</span></span>

<span data-ttu-id="8bc8a-106">**Visual Studio 2019:** Se você estiver usando o Visual Studio 2019, poderá adicionar os pacotes de química do Quantum usando o Gerenciador de pacotes NuGet.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-106">**Visual Studio 2019:** If you are using Visual Studio 2019, you can add the quantum chemistry packages by using the NuGet Package Manager.</span></span>
<span data-ttu-id="8bc8a-107">Para abrir o Gerenciador de pacotes, clique com o botão direito do mouse no projeto ao qual você deseja adicionar a biblioteca de química e selecione "gerenciar pacotes NuGet...", como na captura de tela abaixo.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-107">To open the Package Manager, right-click on the project you'd like to add the chemistry library to and select "Manage NuGet Packages...," as in the screenshot below.</span></span>

![](~/media/vs2017-nuget-manage-packages.png)

<span data-ttu-id="8bc8a-108">Na guia procurar, procure o nome do pacote "Microsoft. Quantum. química".</span><span class="sxs-lookup"><span data-stu-id="8bc8a-108">From the Browse tab, search for the package name "Microsoft.Quantum.Chemistry."</span></span>

> [!NOTE]
> <span data-ttu-id="8bc8a-109">Certifique-se de marcar "incluir pré-lançamento".</span><span class="sxs-lookup"><span data-stu-id="8bc8a-109">Make sure to tick "Include prerelease."</span></span>

![](~/media/vs2017-nuget-package-search.png)

<span data-ttu-id="8bc8a-110">Isso listará os pacotes disponíveis para download.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-110">This will list the packages available for download.</span></span>
<span data-ttu-id="8bc8a-111">Clique no "Microsoft. Quantum. química no painel esquerdo, selecione a versão de pré-lançamento mais recente no painel direito e clique em" instalar ":</span><span class="sxs-lookup"><span data-stu-id="8bc8a-111">Click on the "Microsoft.Quantum.Chemistry on the left-hand pane, select the latest pre-release version on the right-hand pane, and click "Install":</span></span>

![](~/media/vs2017-nuget-select-chem.png)

<span data-ttu-id="8bc8a-112">Para obter mais detalhes, consulte o [Guia de interface do usuário do Gerenciador de pacotes](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="8bc8a-112">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="8bc8a-113">Como alternativa, você pode usar o console do Gerenciador de pacotes para adicionar a biblioteca química do Quantum ao seu projeto com uma interface de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-113">Alternatively, you can use the Package Manager Console to add the quantum chemistry library to your project with a command line interface.</span></span>

![](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="8bc8a-114">No console do Gerenciador de pacotes, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8bc8a-114">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Chemistry
```

<span data-ttu-id="8bc8a-115">Para obter mais detalhes, consulte o [Guia do console do Gerenciador de pacotes](https://docs.microsoft.com/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="8bc8a-115">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="8bc8a-116">**Linha de comando ou Visual Studio Code:** Usando a linha de comando por conta própria ou de dentro Visual Studio Code, você pode usar o comando `dotnet` para adicionar a referência do pacote NuGet ao seu projeto:</span><span class="sxs-lookup"><span data-stu-id="8bc8a-116">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```bash
dotnet add package Microsoft.Quantum.Chemistry
```

## <a name="verifying-your-installation"></a><span data-ttu-id="8bc8a-117">Verificando sua instalação</span><span class="sxs-lookup"><span data-stu-id="8bc8a-117">Verifying Your Installation</span></span> 

<span data-ttu-id="8bc8a-118">Assim como o restante do kit de desenvolvimento Quantum, a biblioteca química do Quantum vem com uma série de amostras totalmente documentadas para ajudá-lo a entrar em funcionamento rapidamente.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-118">Like the rest of the Quantum Development Kit, the quantum chemistry library comes with a number of fully documented samples to help you get up and running quickly.</span></span>
<span data-ttu-id="8bc8a-119">Para testar a instalação usando esses exemplos, clone o [repositório principal de exemplos](https://github.com/Microsoft/Quantum)e, em seguida, execute um dos exemplos.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-119">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum), then run one of the samples.</span></span>  <span data-ttu-id="8bc8a-120">Por exemplo, para executar o exemplo de [`MolecularHydrogen`](https://github.com/Microsoft/Quantum/tree/master/Chemistry/MolecularHydrogen) :</span><span class="sxs-lookup"><span data-stu-id="8bc8a-120">For example, to run the [`MolecularHydrogen`](https://github.com/Microsoft/Quantum/tree/master/Chemistry/MolecularHydrogen) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Chemistry/MolecularHydrogen
dotnet run
```

<span data-ttu-id="8bc8a-121">Para verificar a instalação da biblioteca química do Quantum usando Microsoft Visual Studio depois de clonar o repositório:</span><span class="sxs-lookup"><span data-stu-id="8bc8a-121">To verify the installation of the quantum chemistry library using Microsoft Visual Studio after cloning the repository:</span></span>
    1. <span data-ttu-id="8bc8a-122">Abra a solução ChemistrySamples. sln na pasta química.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-122">Open the ChemistrySamples.sln solution in the Chemistry folder.</span></span>  
    2. <span data-ttu-id="8bc8a-123">Selecione amostras/1.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-123">Select Samples/1.</span></span> <span data-ttu-id="8bc8a-124">Moléculas/MolecularHydrogen simples como o projeto de inicialização.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-124">Simple Molecules/MolecularHydrogen as the StartUp project.</span></span>
    3. <span data-ttu-id="8bc8a-125">Pressione F5 para executar a demonstração de estimativa da fase Quantum do molecular Hydrogen.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-125">Press F5 to run the molecular Hydrogen quantum phase estimation demo.</span></span>

<span data-ttu-id="8bc8a-126">Consulte [obtendo estimativas de nível de energia](xref:microsoft.quantum.chemistry.examples.energyestimate) para obter mais informações sobre como estimar os valores dos níveis de energia.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-126">See [Obtaining energy level estimates](xref:microsoft.quantum.chemistry.examples.energyestimate) for more information on estimating the values of energy levels.</span></span>   


## <a name="using-the-quantum-development-kit-with-nwchem"></a><span data-ttu-id="8bc8a-127">Usando o kit de desenvolvimento Quantum com NWChem</span><span class="sxs-lookup"><span data-stu-id="8bc8a-127">Using the Quantum Development Kit with NWChem</span></span> ##

<span data-ttu-id="8bc8a-128">O exemplo MolecularHydrogen usa os dados de entrada do molecular que são configurados manualmente.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-128">The MolecularHydrogen sample uses molecular input data that is manually configured.</span></span>  <span data-ttu-id="8bc8a-129">Embora isso seja bom para exemplos pequenos, o quantum química em escala exige Hamiltonians com milhões ou bilhões de termos.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-129">While this is fine for small examples, quantum chemistry at scale require Hamiltonians with millions or billions of terms.</span></span> <span data-ttu-id="8bc8a-130">Esses Hamiltonians, gerados por pacotes de química computacional escalonáveis, são muito grandes para serem importados manualmente.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-130">Such Hamiltonians, generated by scalable computational chemistry packages are too large to import by hand.</span></span> 

<span data-ttu-id="8bc8a-131">A biblioteca química do Quantum para o kit de desenvolvimento Quantum foi projetada para funcionar bem com pacotes químicas computacionais, mais notavelmente a plataforma química computacional [**NWChem**](http://www.nwchem-sw.org/) desenvolvida pelo laboratório de Ciências molecular ambiental ( EMSL) no laboratório nacional do noroeste do Pacífico.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-131">The quantum chemistry library for the Quantum Development Kit is designed to work well with computational chemistry packages, most notably the [**NWChem**](http://www.nwchem-sw.org/) computational chemistry platform developed by the Environmental Molecular Sciences Laboratory (EMSL) at Pacific Northwest National Laboratory.</span></span>
<span data-ttu-id="8bc8a-132">Em particular, o pacote de `Microsoft.Quantum.Chemistry` fornece ferramentas para carregar instâncias de problemas de simulação de química do Quantum representados no [esquema Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), também com suporte para exportação por versões recentes do NWChem.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-132">In particular, the `Microsoft.Quantum.Chemistry` package provides tools for loading instances of quantum chemistry simulation problems represented in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), also supported for export by recent versions of NWChem.</span></span>

<span data-ttu-id="8bc8a-133">Para começar a usar o NWChem junto com o kit de desenvolvimento Quantum, sugerimos um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="8bc8a-133">To get up and running using NWChem together with the Quantum Development Kit, we suggest one of the following methods:</span></span>
- <span data-ttu-id="8bc8a-134">Comece a usar os arquivos Broombridge existentes fornecidos com os exemplos em [IntegralData/YAML](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML).</span><span class="sxs-lookup"><span data-stu-id="8bc8a-134">Get started using existing Broombridge files provided with the samples at [IntegralData/YAML](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML).</span></span>
- <span data-ttu-id="8bc8a-135">Use o [Construtor de setas EMSL para o Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) que é um front-end baseado na Web para NWChem, para gerar novos arquivos de entrada molecular Broombridge.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-135">Use the [EMSL Arrows Builder for the Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) which is a web-based frontend to NWChem, to generate new Broombridge-formated molecular input files.</span></span>  
- <span data-ttu-id="8bc8a-136">Use a [imagem do Docker](https://hub.docker.com/r/nwchemorg/nwchem-qc/) fornecida pelo PNNL para executar NWChem ou</span><span class="sxs-lookup"><span data-stu-id="8bc8a-136">Use the [Docker image](https://hub.docker.com/r/nwchemorg/nwchem-qc/) provided by PNNL to run NWChem, or</span></span>
- <span data-ttu-id="8bc8a-137">[Compile o NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) para sua plataforma.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-137">[Compile NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) for your platform.</span></span>

<span data-ttu-id="8bc8a-138">Consulte de [ponta a ponta com NWChem](xref:microsoft.quantum.chemistry.examples.endtoend) para obter mais informações sobre como trabalhar com o NWChem para modelos químicos para analisar com a biblioteca do Quantum Developer Kit química.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-138">See [End-to-end with NWChem](xref:microsoft.quantum.chemistry.examples.endtoend) for more information on how to work with NWChem to chemical models to analyze with the Quantum Developmen Kit chemistry library.</span></span>

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a><span data-ttu-id="8bc8a-139">Introdução ao uso de arquivos Broombridge fornecidos com os exemplos</span><span class="sxs-lookup"><span data-stu-id="8bc8a-139">Getting started using Broombridge files provided with the samples</span></span>
<span data-ttu-id="8bc8a-140">A pasta [IntegralData/YAML](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML) no repositório de exemplos do kit de desenvolvimento do Quantum contém arquivos de dados molécula com formato Broombridge.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-140">The [IntegralData/YAML](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML) folder in the Quantum Development Kit Samples repository contains Broombridge-formated molecule data files.</span></span>  

<span data-ttu-id="8bc8a-141">Como um exemplo simples, use o exemplo de biblioteca de química, [GetGateCount](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount) para carregar o Hamiltonian de um dos arquivos Broombridge e executar estimativas de portão de algorigthms de simulação de Quantum:</span><span class="sxs-lookup"><span data-stu-id="8bc8a-141">As a simple example, use the chemistry library sample, [GetGateCount](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount) to load the Hamiltonian from one of Broombridge files and perform gate estimates of quantum simulation algorigthms:</span></span>

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

<span data-ttu-id="8bc8a-142">Consulte [carregando um Hamiltonian do arquivo](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) para obter mais informações sobre como inserir moléculas representado pelo esquema Broombridge.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-142">See [Loading a Hamiltonian from file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) for more information on how to input molecules represented by the Broombridge schema.</span></span>  

<span data-ttu-id="8bc8a-143">Confira [obtendo contagens de recursos](xref:microsoft.quantum.chemistry.examples.resourcecounts) para obter mais informações sobre a estimativa de recursos.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-143">See [Obtaining resource counts](xref:microsoft.quantum.chemistry.examples.resourcecounts) for more information on resource estimation.</span></span>  

### <a name="getting-started-using-the-emsl-arrows-builder"></a><span data-ttu-id="8bc8a-144">Introdução ao uso do construtor de setas EMSL</span><span class="sxs-lookup"><span data-stu-id="8bc8a-144">Getting started using the EMSL Arrows Builder</span></span>

<span data-ttu-id="8bc8a-145">EMSL Arrows é uma ferramenta que usa bancos de dados computacionais NWChem e químicas para gerar molécula.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-145">EMSL Arrows is a tool that uses NWChem and chemical computational databases to generate molecule data.</span></span>  <span data-ttu-id="8bc8a-146">[O EMSL Arrows Builder para o Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) permite que você insira seu modelo usando vários construtores de modelo molecular e gere o arquivo de configuração do Broombridge para ser usado pelo kit de desenvolvimento Quantum.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-146">[EMSL Arrows Builder for the Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) allows you to enter your model using multiple molecular model builders and generate the Broombridge datafile to be used by the Quantum Development Kit.</span></span>  

<span data-ttu-id="8bc8a-147">Na página EMSL, clique na guia [' instuctions '] e siga as instruções [' exemplos simples '] para gerar arquivos Broombridge.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-147">From the EMSL page, click on the ['Instuctions'] tab, and follow the ['Simple Examples'] instructions to generate Broombridge files.</span></span>  <span data-ttu-id="8bc8a-148">Em seguida, tente executar [' GetGateCount '] para ver as estimativas de recursos Quantum para esses moléculas.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-148">Then try running the ['GetGateCount'] to see the quantum resource estimates for these molecules.</span></span>

### <a name="installing-nwchem-from-source"></a><span data-ttu-id="8bc8a-149">Instalando o NWChem da origem</span><span class="sxs-lookup"><span data-stu-id="8bc8a-149">Installing NWChem from Source</span></span>

<span data-ttu-id="8bc8a-150">Instruções completas sobre como instalar o NWChem da origem [são fornecidas pelo PNNL](http://www.nwchem-sw.org/index.php/Compiling_NWChem).</span><span class="sxs-lookup"><span data-stu-id="8bc8a-150">Full instructions on how to install NWChem from source [are provided by PNNL](http://www.nwchem-sw.org/index.php/Compiling_NWChem).</span></span>

> [!TIP]
> <span data-ttu-id="8bc8a-151">Se você quiser usar o NWChem do Windows 10, o subsistema do Windows para Linux é uma ótima opção.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-151">If you wish to use NWChem from Windows 10, the Windows Subsystem for Linux is a great option.</span></span>
> <span data-ttu-id="8bc8a-152">Depois de instalar o [Ubuntu 18, 4 LTS para Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab), execute `ubuntu18.04` do seu terminal favorito e siga as instruções acima para instalar o NWChem da origem.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-152">Once you have installed [Ubuntu 18.04 LTS for Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab), run `ubuntu18.04` from your favorite terminal and follow the instructions above to install NWChem from source.</span></span>

<span data-ttu-id="8bc8a-153">Depois de ter compilado o NWChem da origem, você pode executar o script de `yaml_driver` fornecido com NWChem para produzir rapidamente instâncias de Broombridge de baralhos de entrada NWChem:</span><span class="sxs-lookup"><span data-stu-id="8bc8a-153">Once you have compiled NWChem from source, you can run the `yaml_driver` script provided with NWChem to quickly produce Broombridge instances from NWChem input decks:</span></span>

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

<span data-ttu-id="8bc8a-154">Esse comando criará um novo arquivo de `input.yaml` no formato Broombridge no diretório atual.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-154">This command will create a new `input.yaml` file in the Broombridge format within your current directory.</span></span>

### <a name="using-nwchem-with-docker"></a><span data-ttu-id="8bc8a-155">Usando o NWChem com o Docker</span><span class="sxs-lookup"><span data-stu-id="8bc8a-155">Using NWChem with Docker</span></span>

<span data-ttu-id="8bc8a-156">As imagens predefinidas para usar o NWChem estão disponíveis para a plataforma cruzada por meio do [Hub do Docker](https://hub.docker.com).</span><span class="sxs-lookup"><span data-stu-id="8bc8a-156">Pre-built images for using NWChem are available cross-platform via [Docker Hub](https://hub.docker.com).</span></span>
<span data-ttu-id="8bc8a-157">Para começar, siga as instruções de instalação do Docker para sua plataforma:</span><span class="sxs-lookup"><span data-stu-id="8bc8a-157">To get started, follow the Docker installation instructions for your platform:</span></span>

- [<span data-ttu-id="8bc8a-158">Instalar o Docker para Ubuntu</span><span class="sxs-lookup"><span data-stu-id="8bc8a-158">Install Docker for Ubuntu</span></span>](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [<span data-ttu-id="8bc8a-159">Instalar o Docker para macOS</span><span class="sxs-lookup"><span data-stu-id="8bc8a-159">Install Docker for macOS</span></span>](https://docs.docker.com/docker-for-mac/install/)
- [<span data-ttu-id="8bc8a-160">Instalar o Docker for Windows 10</span><span class="sxs-lookup"><span data-stu-id="8bc8a-160">Install Docker for Windows 10</span></span>](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> <span data-ttu-id="8bc8a-161">Se estiver usando Docker for Windows, você precisará compartilhar a unidade que contém seu diretório temporário (geralmente, essa é a unidade `C:\`) com o daemon do Docker.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-161">If you are using Docker for Windows, you will need to share the drive containing your temporary directory (usually this is the `C:\` drive) with the Docker daemon.</span></span> <span data-ttu-id="8bc8a-162">Consulte a [documentação do Docker](https://docs.docker.com/docker-for-windows/#shared-drives) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-162">See the [Docker documentation](https://docs.docker.com/docker-for-windows/#shared-drives) for more details.</span></span>

<span data-ttu-id="8bc8a-163">Depois de instalar o Docker, você pode usar o módulo do PowerShell fornecido com os exemplos do kit de desenvolvimento do Quantum para executar a imagem ou pode executar a imagem manualmente.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-163">Once you have Docker installed, you can either use the PowerShell module provided with the Quantum Development Kit samples to run the image, or you can run the image manually.</span></span>
<span data-ttu-id="8bc8a-164">Nós detalhamos o uso do PowerShell aqui; Se você quiser usar a imagem do Docker manualmente, consulte a [documentação fornecida com a imagem](https://hub.docker.com/r/nwchemorg/nwchem-qc/).</span><span class="sxs-lookup"><span data-stu-id="8bc8a-164">We detail using PowerShell here; if you would like to use the Docker image manually, please see the [documentation provided with the image](https://hub.docker.com/r/nwchemorg/nwchem-qc/).</span></span>

#### <a name="running-nwchem-through-powershell-core"></a><span data-ttu-id="8bc8a-165">Executando o NWChem por meio do PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="8bc8a-165">Running NWChem through PowerShell Core</span></span>

<span data-ttu-id="8bc8a-166">Para usar a imagem do Docker NWChem com o kit de desenvolvimento Quantum, fornecemos um pequeno módulo do PowerShell que lida com a movimentação de arquivos para dentro e fora do NWChem para você.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-166">To use the NWChem Docker image with the Quantum Development Kit, we provide a small PowerShell module that handles moving files in and out of NWChem for you.</span></span>
<span data-ttu-id="8bc8a-167">Se você ainda não tiver o PowerShell Core instalado, poderá baixá-lo entre plataformas do [repositório do PowerShell no GitHub](https://github.com/PowerShell/PowerShell#get-powershell).</span><span class="sxs-lookup"><span data-stu-id="8bc8a-167">If you don't already have PowerShell Core installed, you can download it cross-platform from the [PowerShell repository on GitHub](https://github.com/PowerShell/PowerShell#get-powershell).</span></span>

> [!NOTE]
> <span data-ttu-id="8bc8a-168">O PowerShell Core também é usado para alguns exemplos para demonstrar a interoperabilidade com fluxos de trabalho de ciência de dados e análise de negócios.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-168">PowerShell Core is also used for some samples to demonstrate interoperability with data science and business analytics workflows.</span></span>

<span data-ttu-id="8bc8a-169">Depois de instalar o PowerShell Core, importe `InvokeNWChem.psm1` para disponibilizar os comandos do NWChem em sua sessão atual:</span><span class="sxs-lookup"><span data-stu-id="8bc8a-169">Once you have PowerShell Core installed, import `InvokeNWChem.psm1` to make NWChem commands available in your current session:</span></span>

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

<span data-ttu-id="8bc8a-170">Isso tornará o comando `Convert-NWChemToBroombridge` disponível em sua sessão atual do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-170">This will make the `Convert-NWChemToBroombridge` command available in your current PowerShell session.</span></span>
<span data-ttu-id="8bc8a-171">Para baixar todas as imagens necessárias do Docker e usá-las para executar os baralhos de entrada do NWChem e capturar a saída para Broombridge, execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8bc8a-171">To download any needed images from Docker and use them to run NWChem input decks and capture output to Broombridge, run the following:</span></span>

```powershell
Convert-NWChemToBroombridge ./input.nw
```

<span data-ttu-id="8bc8a-172">Isso criará um arquivo Broombridge executando NWChem em `input.nw`.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-172">This will create a Broombridge file by running NWChem on `input.nw`.</span></span>
<span data-ttu-id="8bc8a-173">Por padrão, a saída de Broombridge terá o mesmo nome e caminho que o baralho de entrada, com a extensão de `.nw` substituída por `.yaml`.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-173">By default, the Broombridge output will have the same name and path as the input deck, with the `.nw` extension replaced by `.yaml`.</span></span>
<span data-ttu-id="8bc8a-174">Isso pode ser substituído usando o parâmetro `-DestinationPath` para `Convert-NWChemToBroombridge`.</span><span class="sxs-lookup"><span data-stu-id="8bc8a-174">This can be overridden by using the `-DestinationPath` parameter to `Convert-NWChemToBroombridge`.</span></span>
<span data-ttu-id="8bc8a-175">Mais informações podem ser obtidas usando a funcionalidade interna de ajuda do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8bc8a-175">More information can be obtained by using PowerShell's built-in help functionality:</span></span>

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```


