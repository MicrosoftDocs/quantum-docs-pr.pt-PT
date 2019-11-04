---
title: De ponta a ponta com NWChem | Microsoft Docs
description: Ponta a ponta com o NWChem docs
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/23/2018
uid: microsoft.quantum.chemistry.examples.endtoend
ms.openlocfilehash: 8f727ea4599e06b41ced561c624c4e773b9887d9
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185822"
---
# <a name="end-to-end-with-nwchem"></a><span data-ttu-id="cbcec-103">Ponta a ponta com NWChem</span><span class="sxs-lookup"><span data-stu-id="cbcec-103">End-to-end with NWChem</span></span> #

<span data-ttu-id="cbcec-104">Nesta página, veremos um exemplo de como obter contagens de portão para a simulação química do Quantum, a partir de um baralho de entrada [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) .</span><span class="sxs-lookup"><span data-stu-id="cbcec-104">In this page, we will walk through an example of getting gate counts for quantum chemistry simulation, starting from an [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) input deck.</span></span>
<span data-ttu-id="cbcec-105">Antes de continuar com este exemplo, verifique se você instalou o Docker, seguindo o [Guia de instalação e validação](xref:microsoft.quantum.chemistry.concepts.installation).</span><span class="sxs-lookup"><span data-stu-id="cbcec-105">Before proceeding with this example, make sure that you've installed Docker, following the [installation and validation guide](xref:microsoft.quantum.chemistry.concepts.installation).</span></span>

<span data-ttu-id="cbcec-106">Para mais informações:</span><span class="sxs-lookup"><span data-stu-id="cbcec-106">For more information:</span></span>
- [<span data-ttu-id="cbcec-107">Estrutura de baralhos de entrada NWChem</span><span class="sxs-lookup"><span data-stu-id="cbcec-107">Structure of NWChem input decks</span></span>](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [<span data-ttu-id="cbcec-108">Comandos de baralho de entrada para uso com o kit de desenvolvimento Quantum</span><span class="sxs-lookup"><span data-stu-id="cbcec-108">Input deck commands for use with the Quantum Development Kit</span></span>](https://github.com/nwchemgit/nwchem/tree/master/contrib/quasar)
- [<span data-ttu-id="cbcec-109">Instalando a biblioteca e as dependências química</span><span class="sxs-lookup"><span data-stu-id="cbcec-109">Installing the chemistry library and dependencies</span></span>](xref:microsoft.quantum.chemistry.concepts.installation)
- [<span data-ttu-id="cbcec-110">Contagem de recursos</span><span class="sxs-lookup"><span data-stu-id="cbcec-110">Resource counting</span></span>](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> <span data-ttu-id="cbcec-111">Este exemplo requer que o Windows PowerShell Core seja executado.</span><span class="sxs-lookup"><span data-stu-id="cbcec-111">This example requires Windows PowerShell Core to run.</span></span>
> <span data-ttu-id="cbcec-112">Baixe o PowerShell Core para Windows, macOS ou Linux em https://github.com/PowerShell/PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cbcec-112">Download PowerShell Core for Windows, macOS, or Linux at https://github.com/PowerShell/PowerShell.</span></span>

## <a name="importing-required-powershell-modules"></a><span data-ttu-id="cbcec-113">Importando módulos do PowerShell necessários</span><span class="sxs-lookup"><span data-stu-id="cbcec-113">Importing Required PowerShell Modules</span></span> ##

<span data-ttu-id="cbcec-114">Se você ainda não fez isso, clone o [repositório Microsoft/Quantum](https://github.com/Microsoft/Quantum), que contém exemplos e utilitários para trabalhar com o kit de desenvolvimento Quantum:</span><span class="sxs-lookup"><span data-stu-id="cbcec-114">If you haven't already done so, clone the [Microsoft/Quantum repository](https://github.com/Microsoft/Quantum), which contains samples and utilities for working with the Quantum Development Kit:</span></span>

```powershell
git clone https://github.com/Microsoft/Quantum
```

<span data-ttu-id="cbcec-115">Depois de clonar `Microsoft/Quantum`, execute `cd` na pasta `utilities/` e importe o módulo do PowerShell para trabalhar com Docker e NWChem:</span><span class="sxs-lookup"><span data-stu-id="cbcec-115">Once you've cloned `Microsoft/Quantum`, perform `cd` into the `utilities/` folder and import the PowerShell module for working with Docker and NWChem:</span></span>

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> <span data-ttu-id="cbcec-116">Por padrão, o Windows impede a execução de qualquer script ou módulo como uma medida de segurança.</span><span class="sxs-lookup"><span data-stu-id="cbcec-116">By default, Windows prevents the execution of any scripts or modules as a security measure.</span></span>
> <span data-ttu-id="cbcec-117">Para permitir que módulos como `Invoke-NWChem.psm1` sejam executados no Windows, talvez seja necessário alterar a política de execução.</span><span class="sxs-lookup"><span data-stu-id="cbcec-117">To allow modules such as `Invoke-NWChem.psm1` to run on Windows, you may need to change the execution policy.</span></span>
> <span data-ttu-id="cbcec-118">Para fazer isso, execute o comando `Set-ExecutionPolicy`:</span><span class="sxs-lookup"><span data-stu-id="cbcec-118">To do so, run the `Set-ExecutionPolicy` command:</span></span>
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> <span data-ttu-id="cbcec-119">A política de execução será revertida quando você sair do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cbcec-119">The execution policy will then be reverted when you exit PowerShell.</span></span>
> <span data-ttu-id="cbcec-120">Se você quiser salvar a política de execução, use um valor diferente para `-Scope`:</span><span class="sxs-lookup"><span data-stu-id="cbcec-120">If you would like to save the execution policy, use a different value for `-Scope`:</span></span>
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

<span data-ttu-id="cbcec-121">Agora você deve ter o comando `Convert-NWChemToBroombridge` disponível:</span><span class="sxs-lookup"><span data-stu-id="cbcec-121">You should now have the `Convert-NWChemToBroombridge` command available:</span></span>

```powershell
Get-Command -Module InvokeNWChem
```

<span data-ttu-id="cbcec-122">Em seguida, importaremos o comando `Get-GateCount` fornecido com o exemplo **GetGateCount** .</span><span class="sxs-lookup"><span data-stu-id="cbcec-122">Next, we'll import the `Get-GateCount` command provided with the **GetGateCount** sample.</span></span>
<span data-ttu-id="cbcec-123">Para obter detalhes completos, consulte as [instruções fornecidas com o exemplo](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount).</span><span class="sxs-lookup"><span data-stu-id="cbcec-123">For full details, see the [instructions provided with the sample](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount).</span></span>
<span data-ttu-id="cbcec-124">Em seguida, execute o seguinte, substituindo `<runtime>` pelo `win10-x64`, `osx-x64`ou `linux-x64`, dependendo do seu sistema operacional:</span><span class="sxs-lookup"><span data-stu-id="cbcec-124">Next, run the following, substituting `<runtime>` with either `win10-x64`, `osx-x64`, or `linux-x64`, depending on your operating system:</span></span>

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

<span data-ttu-id="cbcec-125">Agora você deve ter o comando `Get-GateCount` disponível:</span><span class="sxs-lookup"><span data-stu-id="cbcec-125">You should now have the `Get-GateCount` command available:</span></span>

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a><span data-ttu-id="cbcec-126">Baralhos de entrada</span><span class="sxs-lookup"><span data-stu-id="cbcec-126">Input Decks</span></span> ##

<span data-ttu-id="cbcec-127">O pacote NWChem pega um arquivo de texto chamado um _baralho de entrada_ que especifica um problema de química do Quantum a ser resolvido, juntamente com outros parâmetros, como configurações de alocação de memória.</span><span class="sxs-lookup"><span data-stu-id="cbcec-127">The NWChem package takes a text file called an _input deck_ which specifies a quantum chemistry problem to be solved, along with other parameters such as memory allocation settings.</span></span>
<span data-ttu-id="cbcec-128">Para este exemplo, usaremos um dos baralhos de entrada predefinidos que vem com NWChem.</span><span class="sxs-lookup"><span data-stu-id="cbcec-128">For this example, we'll use one of the pre-made input decks that comes with NWChem.</span></span>
<span data-ttu-id="cbcec-129">Primeiro, clone o [repositório nwchemgit/nwchem](https://github.com/nwchemgit/nwchem):</span><span class="sxs-lookup"><span data-stu-id="cbcec-129">First, clone the [nwchemgit/nwchem repository](https://github.com/nwchemgit/nwchem):</span></span>

> [!NOTE]
> <span data-ttu-id="cbcec-130">Como esse é um repositório muito grande, podemos fazer um clone superficial para economizar alguma largura de banda e espaço em disco, usando o argumento `--depth 1`.</span><span class="sxs-lookup"><span data-stu-id="cbcec-130">Since this is a very large repository, we can do a shallow clone to save some bandwidth and disk space, using the `--depth 1` argument.</span></span>
> <span data-ttu-id="cbcec-131">No entanto, isso é opcional.</span><span class="sxs-lookup"><span data-stu-id="cbcec-131">This is optional, however.</span></span>
> <span data-ttu-id="cbcec-132">A clonagem funcionará bem sem `--depth 1`.</span><span class="sxs-lookup"><span data-stu-id="cbcec-132">Cloning will work just fine without `--depth 1`.</span></span>

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

<span data-ttu-id="cbcec-133">O repositório de `nwchemgit/nwchem` vem com uma variedade de baralhos de entrada destinados ao uso com o kit de desenvolvimento Quantum, listado na [pasta`QA/chem_library_tests`](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests).</span><span class="sxs-lookup"><span data-stu-id="cbcec-133">The `nwchemgit/nwchem` repository comes with a variety of input decks intended for use with the Quantum Development Kit, listed under the [`QA/chem_library_tests` folder](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests).</span></span>
<span data-ttu-id="cbcec-134">Para este exemplo, usaremos o baralho de entrada `H4`:</span><span class="sxs-lookup"><span data-stu-id="cbcec-134">For this example, we'll use the `H4` input deck:</span></span>

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

<span data-ttu-id="cbcec-135">O molécula em questão é um sistema de 4 Hydrogen Atoms que são organizados em uma determinada geometria que depende de um ângulo, o parâmetro `alpha` conforme indicado no nome `h4_sto6g_alpha.nw` do baralho.</span><span class="sxs-lookup"><span data-stu-id="cbcec-135">The molecule in question is a system of 4 hydrogen atoms that are arranged in a certain geometry that depends on one angle, the parameter `alpha` as indicated in the name `h4_sto6g_alpha.nw` of the deck.</span></span> <span data-ttu-id="cbcec-136">H4 é um parâmetro de [comparação molecular](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) conhecido para química computacional desde o 70.</span><span class="sxs-lookup"><span data-stu-id="cbcec-136">H4 is a known [molecular benchmark](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) for computational chemistry since the 1970s.</span></span> <span data-ttu-id="cbcec-137">O parâmetro `sto6g` é indica que o baralho implementa uma representação em relação a um orbital de tipo Slater, especificamente, uma representação com relação a um [conjunto de base ARM-ng](https://en.wikipedia.org/wiki/STO-nG_basis_sets) com 6 funções de base gaussianas.</span><span class="sxs-lookup"><span data-stu-id="cbcec-137">The parameter `sto6g` is indicative that the deck implements a representation with respect to a Slater-type orbital, specifically, a representation with respect to an [STO-nG basis set](https://en.wikipedia.org/wiki/STO-nG_basis_sets) with 6 Gaussian basis functions.</span></span> <span data-ttu-id="cbcec-138">Esse baralho de entrada contém várias instruções para o mecanismo de NWChem tensor (TCE) que direciona o NWChem para produzir as informações necessárias para interoperar com o kit de desenvolvimento Quantum:</span><span class="sxs-lookup"><span data-stu-id="cbcec-138">This input deck furthermore contains several instructions to the NWChem Tensor Contraction Engine (TCE) that direct NWChem to produce the information needed for interoperating with the Quantum Development Kit:</span></span>

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a><span data-ttu-id="cbcec-139">Produzindo e consumindo a saída de Broombridge de NWChem</span><span class="sxs-lookup"><span data-stu-id="cbcec-139">Producing and Consuming Broombridge Output from NWChem</span></span> ##

<span data-ttu-id="cbcec-140">Agora temos tudo o que precisamos para produzir e consumir documentos Broombridge.</span><span class="sxs-lookup"><span data-stu-id="cbcec-140">We now have everything we need to produce and consume Broombridge documents.</span></span>
<span data-ttu-id="cbcec-141">Para executar o NWChem e produzir um documento Broombridge para o baralho de entrada `h4_sto6g_0.000.nw`, execute `Convert-NWChemToBroombridge`:</span><span class="sxs-lookup"><span data-stu-id="cbcec-141">To run NWChem and produce a Broombridge document for the `h4_sto6g_0.000.nw` input deck, run `Convert-NWChemToBroombridge`:</span></span>

> [!NOTE]
> <span data-ttu-id="cbcec-142">Na primeira vez que você executar esse comando, o Docker baixará a imagem de `nwchemorg/nwchem-qc` para você.</span><span class="sxs-lookup"><span data-stu-id="cbcec-142">The first time you run this command, Docker will download the `nwchemorg/nwchem-qc` image for you.</span></span>
> <span data-ttu-id="cbcec-143">Isso pode demorar um pouco, dependendo da velocidade da sua conexão, possivelmente oferecendo uma oportunidade de café.</span><span class="sxs-lookup"><span data-stu-id="cbcec-143">This may take a little while, depending on your connection speed, possibly providing an opportunity to get a cup of coffee.</span></span>

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

<span data-ttu-id="cbcec-144">Isso produzirá um documento Broombridge chamado `h4_sto6g_0.000.yaml` que podemos usar com `Get-GateCount`:</span><span class="sxs-lookup"><span data-stu-id="cbcec-144">This will produce a Broombridge document called `h4_sto6g_0.000.yaml` that we can use with `Get-GateCount`:</span></span>

```powershell
Get-GateCount -Format YAML h4_sto6g_0.000.yaml
```

<span data-ttu-id="cbcec-145">Agora você deve ver a saída do console que contém a estimativa de recurso, como contagem de T, contagem de rotações, contagem de CNOT, etc. para vários métodos de simulação de Quantum:</span><span class="sxs-lookup"><span data-stu-id="cbcec-145">You should now see console output which contains resource estimation such as T-count, rotations count, CNOT count, etc. for various quantum simulation methods:</span></span>

```powershell 
IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Trotter
TCount              : 0
RotationsCount      : 92
CNOTCount           : 520
ElapsedMilliseconds : 327

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Qubitization
TCount              : 438
RotationsCount      : 516
CNOTCount           : 2150
ElapsedMilliseconds : 528

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Optimized Qubitization
TCount              : 3540
RotationsCount      : 18
CNOTCount           : 7932
ElapsedMilliseconds : 721
```

<span data-ttu-id="cbcec-146">Há muitas coisas a serem passadas aqui:</span><span class="sxs-lookup"><span data-stu-id="cbcec-146">There are many things to go do from here:</span></span> 
- <span data-ttu-id="cbcec-147">Experimente os baralhos de entrada predefinidos diferentes, por exemplo, variando o parâmetro `alpha` em `h4_sto6g_alpha.nw`,</span><span class="sxs-lookup"><span data-stu-id="cbcec-147">Try out different predefined input decks, e.g., by varying the parameter `alpha` in `h4_sto6g_alpha.nw`,</span></span> 
- <span data-ttu-id="cbcec-148">Tente modificar os baralhos editando os barNWChems diretamente, por exemplo, explorando modelos de `STO-nG` para várias opções de n,</span><span class="sxs-lookup"><span data-stu-id="cbcec-148">Try modifying the decks by editing the NWChem decks directly, e.g., exploring `STO-nG` models for various choices of n,</span></span> 
- <span data-ttu-id="cbcec-149">Tente outros barNWChem de entrada predefinidos que estejam disponíveis em `nwchem/qa/chem_library_tests`,</span><span class="sxs-lookup"><span data-stu-id="cbcec-149">Try other predefined NWChem input decks that are available at `nwchem/qa/chem_library_tests`,</span></span>
- <span data-ttu-id="cbcec-150">Experimente um conjunto de benchmarks predefinidos do Broombridge YAML que foram gerados do NWChem e estão disponíveis como parte do [repositório Microsoft/Quantum](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML).</span><span class="sxs-lookup"><span data-stu-id="cbcec-150">Try out a suite of predefined Broombridge YAML benchmarks that were generated from NWChem and are available as part of the [Microsoft/Quantum repository](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML).</span></span> <span data-ttu-id="cbcec-151">Esses parâmetros de comparação incluem:</span><span class="sxs-lookup"><span data-stu-id="cbcec-151">These benchmarks include:</span></span> 
    - <span data-ttu-id="cbcec-152">moléculas pequeno, como molecular Hydrogen (H2), Beryllium (ser), lítio hydride (LiH),</span><span class="sxs-lookup"><span data-stu-id="cbcec-152">small molecules such as molecular hydrogen (H2), Beryllium (Be), Lithium hydride (LiH),</span></span>
    - <span data-ttu-id="cbcec-153">moléculas maiores, como ozônio (O3), beta-carotene, cytosine e muito mais.</span><span class="sxs-lookup"><span data-stu-id="cbcec-153">larger molecules such as ozone (O3), beta-carotene, cytosine, and many more.</span></span> 
- <span data-ttu-id="cbcec-154">Experimente as [setas de EMSL](https://arrows.emsl.pnnl.gov/api/qsharp_chem) de front-end gráficas que apresenta uma interface para a Microsoft Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="cbcec-154">Try out the graphical front-end [EMSL Arrows](https://arrows.emsl.pnnl.gov/api/qsharp_chem) that features an interface to the Microsoft Quantum Development Kit.</span></span> 


## <a name="producing-broombridge-output-from-emsl-arrows"></a><span data-ttu-id="cbcec-155">Produzindo saída Broombridge de setas EMSL</span><span class="sxs-lookup"><span data-stu-id="cbcec-155">Producing Broombridge Output from EMSL Arrows</span></span> ##

<span data-ttu-id="cbcec-156">Para começar a usar as setas EMSL de front-end baseadas na Web, navegue até um navegador [aqui](https://arrows.emsl.pnnl.gov/api/qsharp_chem).</span><span class="sxs-lookup"><span data-stu-id="cbcec-156">To get started with web-based front end EMSL Arrows, navigate a browser [here](https://arrows.emsl.pnnl.gov/api/qsharp_chem).</span></span> 

> [!NOTE]
> <span data-ttu-id="cbcec-157">A execução de setas EMSL em um navegador da Web requer que o JavaScript esteja habilitado.</span><span class="sxs-lookup"><span data-stu-id="cbcec-157">Running EMSL Arrows in a web browser requires JavaScript to be enabled.</span></span> <span data-ttu-id="cbcec-158">Veja estas [instruções](https://www.enable-javascript.com/) sobre como habilitar o JavaScript em seu navegador.</span><span class="sxs-lookup"><span data-stu-id="cbcec-158">Please refer to these [instructions](https://www.enable-javascript.com/) on how to enable JavaScript in your browser.</span></span> 

<span data-ttu-id="cbcec-159">Primeiro, insira um molécula na caixa de consulta que diz ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.``</span><span class="sxs-lookup"><span data-stu-id="cbcec-159">First, enter a molecule in the query box that says ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.``</span></span> 

<span data-ttu-id="cbcec-160">Você pode inserir muitos moléculas por seu nome de uso coloquial, como "cafeína" em vez de "1, 3, 7-Trimethylxanthine".</span><span class="sxs-lookup"><span data-stu-id="cbcec-160">You can enter many molecules by their colloquial name, such as "caffeine" instead of "1,3,7-Trimethylxanthine".</span></span> 

<span data-ttu-id="cbcec-161">Em seguida, clique no botão que indica ``theory{qsharp_chem}``.</span><span class="sxs-lookup"><span data-stu-id="cbcec-161">Next, click the button that says ``theory{qsharp_chem}``.</span></span> <span data-ttu-id="cbcec-162">Isso preencherá a caixa de consulta mais detalhadamente com uma instrução que dirá a execução para exportar a saída no formato Broombridge YAML.</span><span class="sxs-lookup"><span data-stu-id="cbcec-162">This will populate the query box further with an instruction that will tell the run to export output in the Broombridge YAML format.</span></span> 

<span data-ttu-id="cbcec-163">Agora, o relógio ``Run Arrows``.</span><span class="sxs-lookup"><span data-stu-id="cbcec-163">Now, clock on ``Run Arrows``.</span></span> <span data-ttu-id="cbcec-164">Dependendo do tamanho da entrada, isso pode levar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="cbcec-164">Depending on the size of the input, this might take a while.</span></span> <span data-ttu-id="cbcec-165">Ou, caso o modelo específico já tenha sido computado antes, ele pode ser feito de forma muito rápida, uma vez que será apenas uma pesquisa em um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="cbcec-165">Or, in case the particular model has already been computed before, it can be done extremely fast as it will only amount to a lookup in a database.</span></span> <span data-ttu-id="cbcec-166">Em ambos os casos, você será levado para uma nova página que contém uma grande quantidade de informações sobre a execução específica de NWChem em relação ao baralho especificado por sua entrada.</span><span class="sxs-lookup"><span data-stu-id="cbcec-166">In either case, you will be taken to a new page that contains a plethora of information about the particular run of NWChem against the deck specified by your input.</span></span> 

<span data-ttu-id="cbcec-167">Você pode baixar e salvar o arquivo Broombridge YAML da seção que começa com o seguinte cabeçalho:</span><span class="sxs-lookup"><span data-stu-id="cbcec-167">You can download and save the Broombridge YAML file from the section that starts with the following header:</span></span> 
```powershell
+==================================================+
||              Molecular Calculation             ||
+==================================================+

Id     = 48443

NWOutput = Link to NWChem Output (download)

Datafiles:
qsharp_chem.yaml-2018-10-23-14:37:42 (download)
...
```

<span data-ttu-id="cbcec-168">Clique em ``download``, que salva uma cópia local com um nome de arquivo exclusivo, como ``qsharp_chem48443.yaml`` (o nome específico será diferente para cada execução).</span><span class="sxs-lookup"><span data-stu-id="cbcec-168">Click on ``download``, which saves a local copy with a unique file name such as ``qsharp_chem48443.yaml`` (the particular name will be different for each run).</span></span> <span data-ttu-id="cbcec-169">Em seguida, você pode processar esse arquivo como acima, por exemplo, com</span><span class="sxs-lookup"><span data-stu-id="cbcec-169">You can then further process this file as above, e.g., with</span></span> 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
<span data-ttu-id="cbcec-170">para obter contagens de recursos.</span><span class="sxs-lookup"><span data-stu-id="cbcec-170">to get resource counts.</span></span> 

<span data-ttu-id="cbcec-171">Você pode desfrutar do construtor de molécula 3D que pode ser acessado na guia ``Arrows Entry - 3D Builder`` na página inicial das setas EMSL.</span><span class="sxs-lookup"><span data-stu-id="cbcec-171">You might enjoy the 3D molecule builder that can be accessed from the ``Arrows Entry - 3D Builder`` tab on the EMSL Arrows start page.</span></span> <span data-ttu-id="cbcec-172">Clicar na imagem 3D [JSMol](http://wiki.jmol.org/index.php/JSmol) do molécula mostrado permitirá que você o edite.</span><span class="sxs-lookup"><span data-stu-id="cbcec-172">Clicking the [JSMol](http://wiki.jmol.org/index.php/JSmol) 3D picture of the shown molecule will let you allow to edit it.</span></span> <span data-ttu-id="cbcec-173">Você pode mover os átomos, arrastar Atoms para que suas distâncias entre molecular sejam alteradas, adicionar/remover Atoms, etc. Para cada uma dessas opções, depois de adicionar ``theory{qsharp_chem}`` na caixa de consulta, você pode gerar uma instância do esquema Broombridge YAML e explorá-la ainda mais usando a biblioteca química do Quantum.</span><span class="sxs-lookup"><span data-stu-id="cbcec-173">You can move atoms around, drag atoms apart so that their inter-molecular distances change, add/remove atoms, etc. For each of these choices, once you added ``theory{qsharp_chem}`` in the query box, you can then generate an instance of the Broombridge YAML schema and further explore it using the Quantum Chemistry Library.</span></span> 
