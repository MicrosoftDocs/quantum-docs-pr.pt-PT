---
title: Programa quântico da amostra NWChem
description: Usando um deck de entrada NWChem, caminhe por um exemplo de obter contagens de portão para simulação de química quântica.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/23/2018
uid: microsoft.quantum.chemistry.examples.endtoend
ms.openlocfilehash: 7605676e05ee352e47791657eeaafceef5dbb493
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/10/2020
ms.locfileid: "79022499"
---
# <a name="end-to-end-with-nwchem"></a><span data-ttu-id="173a6-103">Ponto a ponto com NWChem</span><span class="sxs-lookup"><span data-stu-id="173a6-103">End-to-end with NWChem</span></span> #

<span data-ttu-id="173a6-104">Neste artigo, você vai passar por um exemplo de obter contagens de portão para simulação de química quântica, a partir de um deck de entrada [NWChem.](http://www.nwchem-sw.org/index.php/Main_Page)</span><span class="sxs-lookup"><span data-stu-id="173a6-104">In this article, you will walk through an example of getting gate counts for quantum chemistry simulation, starting from an [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) input deck.</span></span>
<span data-ttu-id="173a6-105">Antes de prosseguir com este exemplo, certifique-se de que instalou o Docker, seguindo o guia de [instalação e validação](xref:microsoft.quantum.chemistry.concepts.installation).</span><span class="sxs-lookup"><span data-stu-id="173a6-105">Before proceeding with this example, make sure that you've installed Docker, following the [installation and validation guide](xref:microsoft.quantum.chemistry.concepts.installation).</span></span>

<span data-ttu-id="173a6-106">Para obter mais informações:</span><span class="sxs-lookup"><span data-stu-id="173a6-106">For more information:</span></span>
- [<span data-ttu-id="173a6-107">Estrutura dos decks de entrada NWChem</span><span class="sxs-lookup"><span data-stu-id="173a6-107">Structure of NWChem input decks</span></span>](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [<span data-ttu-id="173a6-108">Comandos de deck de entrada para uso com o Kit de Desenvolvimento Quântico</span><span class="sxs-lookup"><span data-stu-id="173a6-108">Input deck commands for use with the Quantum Development Kit</span></span>](https://github.com/nwchemgit/nwchem/tree/master/contrib/quasar)
- [<span data-ttu-id="173a6-109">Instalação da biblioteca de química e dependências</span><span class="sxs-lookup"><span data-stu-id="173a6-109">Installing the chemistry library and dependencies</span></span>](xref:microsoft.quantum.chemistry.concepts.installation)
- [<span data-ttu-id="173a6-110">Contagem de recursos</span><span class="sxs-lookup"><span data-stu-id="173a6-110">Resource counting</span></span>](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> <span data-ttu-id="173a6-111">Este exemplo requer que o Windows PowerShell Core seja executado.</span><span class="sxs-lookup"><span data-stu-id="173a6-111">This example requires Windows PowerShell Core to run.</span></span>
> <span data-ttu-id="173a6-112">Baixe powerShell Core para Windows, macOS ou Linux em https://github.com/PowerShell/PowerShell.</span><span class="sxs-lookup"><span data-stu-id="173a6-112">Download PowerShell Core for Windows, macOS, or Linux at https://github.com/PowerShell/PowerShell.</span></span>

## <a name="importing-required-powershell-modules"></a><span data-ttu-id="173a6-113">Importação de módulos PowerShell necessários</span><span class="sxs-lookup"><span data-stu-id="173a6-113">Importing Required PowerShell Modules</span></span> ##

<span data-ttu-id="173a6-114">Se ainda não o fez, clone o [repositório Microsoft/Quantum,](https://github.com/Microsoft/Quantum)que contém amostras e utilidades para trabalhar com o Kit de Desenvolvimento Quântico:</span><span class="sxs-lookup"><span data-stu-id="173a6-114">If you haven't already done so, clone the [Microsoft/Quantum repository](https://github.com/Microsoft/Quantum), which contains samples and utilities for working with the Quantum Development Kit:</span></span>

```powershell
git clone https://github.com/Microsoft/Quantum
```

<span data-ttu-id="173a6-115">Depois de clonar `Microsoft/Quantum`, execute `cd` na pasta `utilities/` e importe o módulo PowerShell para trabalhar com Docker e NWChem:</span><span class="sxs-lookup"><span data-stu-id="173a6-115">Once you've cloned `Microsoft/Quantum`, perform `cd` into the `utilities/` folder and import the PowerShell module for working with Docker and NWChem:</span></span>

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> <span data-ttu-id="173a6-116">Por predefinição, o Windows impede a execução de quaisquer scripts ou módulos como medida de segurança.</span><span class="sxs-lookup"><span data-stu-id="173a6-116">By default, Windows prevents the execution of any scripts or modules as a security measure.</span></span>
> <span data-ttu-id="173a6-117">Para permitir que módulos como `Invoke-NWChem.psm1` a funcionar no Windows, poderá ter de alterar a política de execução.</span><span class="sxs-lookup"><span data-stu-id="173a6-117">To allow modules such as `Invoke-NWChem.psm1` to run on Windows, you may need to change the execution policy.</span></span>
> <span data-ttu-id="173a6-118">Para isso, dirija o comando `Set-ExecutionPolicy`:</span><span class="sxs-lookup"><span data-stu-id="173a6-118">To do so, run the `Set-ExecutionPolicy` command:</span></span>
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> <span data-ttu-id="173a6-119">A política de execução será revertida quando sair da PowerShell.</span><span class="sxs-lookup"><span data-stu-id="173a6-119">The execution policy will then be reverted when you exit PowerShell.</span></span>
> <span data-ttu-id="173a6-120">Se quiser salvar a política de execução, utilize um valor diferente para `-Scope`:</span><span class="sxs-lookup"><span data-stu-id="173a6-120">If you would like to save the execution policy, use a different value for `-Scope`:</span></span>
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

<span data-ttu-id="173a6-121">Deve agora ter o comando `Convert-NWChemToBroombridge` disponível:</span><span class="sxs-lookup"><span data-stu-id="173a6-121">You should now have the `Convert-NWChemToBroombridge` command available:</span></span>

```powershell
Get-Command -Module InvokeNWChem
```

<span data-ttu-id="173a6-122">Em seguida, importaremos o comando `Get-GateCount` fornecido com a amostra **GetGateCount.**</span><span class="sxs-lookup"><span data-stu-id="173a6-122">Next, we'll import the `Get-GateCount` command provided with the **GetGateCount** sample.</span></span>
<span data-ttu-id="173a6-123">Para mais detalhes, consulte as [instruções fornecidas com a amostra](https://github.com/Microsoft/Quantum/tree/master/samples/chemistry/GetGateCount).</span><span class="sxs-lookup"><span data-stu-id="173a6-123">For full details, see the [instructions provided with the sample](https://github.com/Microsoft/Quantum/tree/master/samples/chemistry/GetGateCount).</span></span>
<span data-ttu-id="173a6-124">Em seguida, execute o seguinte, substituindo `<runtime>` por `win10-x64`, `osx-x64`, ou `linux-x64`, dependendo do seu sistema operativo:</span><span class="sxs-lookup"><span data-stu-id="173a6-124">Next, run the following, substituting `<runtime>` with either `win10-x64`, `osx-x64`, or `linux-x64`, depending on your operating system:</span></span>

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

<span data-ttu-id="173a6-125">Deve agora ter o comando `Get-GateCount` disponível:</span><span class="sxs-lookup"><span data-stu-id="173a6-125">You should now have the `Get-GateCount` command available:</span></span>

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a><span data-ttu-id="173a6-126">Decks de entrada</span><span class="sxs-lookup"><span data-stu-id="173a6-126">Input Decks</span></span> ##

<span data-ttu-id="173a6-127">O pacote NWChem pega num ficheiro de texto chamado deck de _entrada_ que especifica um problema de química quântica a ser resolvido, juntamente com outros parâmetros, tais como definições de atribuição de memória.</span><span class="sxs-lookup"><span data-stu-id="173a6-127">The NWChem package takes a text file called an _input deck_ which specifies a quantum chemistry problem to be solved, along with other parameters such as memory allocation settings.</span></span>
<span data-ttu-id="173a6-128">Para este exemplo, usaremos um dos decks de entrada pré-fabricados que vem com a NWChem.</span><span class="sxs-lookup"><span data-stu-id="173a6-128">For this example, we'll use one of the pre-made input decks that comes with NWChem.</span></span>
<span data-ttu-id="173a6-129">Primeiro, clone o [repositório nwchemgit/nwchem:](https://github.com/nwchemgit/nwchem)</span><span class="sxs-lookup"><span data-stu-id="173a6-129">First, clone the [nwchemgit/nwchem repository](https://github.com/nwchemgit/nwchem):</span></span>

> [!NOTE]
> <span data-ttu-id="173a6-130">Uma vez que este é um repositório muito grande, podemos fazer um clone raso para poupar algum espaço de largura de banda e disco, usando o argumento `--depth 1`.</span><span class="sxs-lookup"><span data-stu-id="173a6-130">Since this is a very large repository, we can do a shallow clone to save some bandwidth and disk space, using the `--depth 1` argument.</span></span>
> <span data-ttu-id="173a6-131">Isto é opcional, no entanto.</span><span class="sxs-lookup"><span data-stu-id="173a6-131">This is optional, however.</span></span>
> <span data-ttu-id="173a6-132">A clonagem funcionará muito bem sem `--depth 1`.</span><span class="sxs-lookup"><span data-stu-id="173a6-132">Cloning will work just fine without `--depth 1`.</span></span>

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

<span data-ttu-id="173a6-133">O repositório `nwchemgit/nwchem` vem com uma variedade de decks de entrada destinados a ser utilizados com o Kit de Desenvolvimento Quântico, listado na [pasta`QA/chem_library_tests`](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests).</span><span class="sxs-lookup"><span data-stu-id="173a6-133">The `nwchemgit/nwchem` repository comes with a variety of input decks intended for use with the Quantum Development Kit, listed under the [`QA/chem_library_tests` folder](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests).</span></span>
<span data-ttu-id="173a6-134">Para este exemplo, usaremos o deck de entrada `H4`:</span><span class="sxs-lookup"><span data-stu-id="173a6-134">For this example, we'll use the `H4` input deck:</span></span>

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

<span data-ttu-id="173a6-135">A molécula em questão é um sistema de 4 átomos de hidrogénio que estão dispostos numa certa geometria que depende de um ângulo, o parâmetro `alpha` como indicado no nome `h4_sto6g_alpha.nw` do convés.</span><span class="sxs-lookup"><span data-stu-id="173a6-135">The molecule in question is a system of 4 hydrogen atoms that are arranged in a certain geometry that depends on one angle, the parameter `alpha` as indicated in the name `h4_sto6g_alpha.nw` of the deck.</span></span> <span data-ttu-id="173a6-136">H4 é uma [referência molecular](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) conhecida para química computacional desde a década de 1970.</span><span class="sxs-lookup"><span data-stu-id="173a6-136">H4 is a known [molecular benchmark](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) for computational chemistry since the 1970s.</span></span> <span data-ttu-id="173a6-137">O parâmetro `sto6g` indica que o convés implementa uma representação no que diz respeito a um orbital do tipo Slater, especificamente, uma representação em relação a uma [base STO-nG definida](https://en.wikipedia.org/wiki/STO-nG_basis_sets) com 6 funções de base gaussiana.</span><span class="sxs-lookup"><span data-stu-id="173a6-137">The parameter `sto6g` is indicative that the deck implements a representation with respect to a Slater-type orbital, specifically, a representation with respect to an [STO-nG basis set](https://en.wikipedia.org/wiki/STO-nG_basis_sets) with 6 Gaussian basis functions.</span></span> <span data-ttu-id="173a6-138">Este deck de entrada contém ainda várias instruções para o NWChem Tensor Contraction Engine (TCE) que direciona a NWChem para produzir as informações necessárias para interoperação com o Kit de Desenvolvimento Quântico:</span><span class="sxs-lookup"><span data-stu-id="173a6-138">This input deck furthermore contains several instructions to the NWChem Tensor Contraction Engine (TCE) that direct NWChem to produce the information needed for interoperating with the Quantum Development Kit:</span></span>

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a><span data-ttu-id="173a6-139">Produção e Consumo de Broombridge Output da NWChem</span><span class="sxs-lookup"><span data-stu-id="173a6-139">Producing and Consuming Broombridge Output from NWChem</span></span> ##

<span data-ttu-id="173a6-140">Agora tem tudo o que precisa para produzir e consumir documentos de Broombridge.</span><span class="sxs-lookup"><span data-stu-id="173a6-140">You now have everything you need to produce and consume Broombridge documents.</span></span>
<span data-ttu-id="173a6-141">Para executar a NWChem e produzir um documento broombridge para o deck de entrada `h4_sto6g_0.000.nw`, executar `Convert-NWChemToBroombridge`:</span><span class="sxs-lookup"><span data-stu-id="173a6-141">To run NWChem and produce a Broombridge document for the `h4_sto6g_0.000.nw` input deck, run `Convert-NWChemToBroombridge`:</span></span>

> [!NOTE]
> <span data-ttu-id="173a6-142">A primeira vez que dirigeeste este comando, o Docker vai descarregar a imagem `nwchemorg/nwchem-qc` para ti.</span><span class="sxs-lookup"><span data-stu-id="173a6-142">The first time you run this command, Docker will download the `nwchemorg/nwchem-qc` image for you.</span></span>
> <span data-ttu-id="173a6-143">Isto pode demorar um pouco, dependendo da sua velocidade de ligação, possivelmente proporcionando uma oportunidade de tomar uma xícara de café.</span><span class="sxs-lookup"><span data-stu-id="173a6-143">This may take a little while, depending on your connection speed, possibly providing an opportunity to get a cup of coffee.</span></span>

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

<span data-ttu-id="173a6-144">Isto produzirá um documento de Broombridge chamado `h4_sto6g_0.000.yaml` que pode usar com `Get-GateCount`:</span><span class="sxs-lookup"><span data-stu-id="173a6-144">This will produce a Broombridge document called `h4_sto6g_0.000.yaml` that you can use with `Get-GateCount`:</span></span>

```powershell
Get-GateCount -Format YAML h4_sto6g_0.000.yaml
```

<span data-ttu-id="173a6-145">Deve agora ver a saída da consola que contém estimativas de recursos, tais como contagem de T, contagem de rotações, contagem de CNOT, etc. para vários métodos de simulação quântica:</span><span class="sxs-lookup"><span data-stu-id="173a6-145">You should now see console output which contains resource estimation such as T-count, rotations count, CNOT count, etc. for various quantum simulation methods:</span></span>

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

<span data-ttu-id="173a6-146">Há muitas coisas para fazer a partir daqui:</span><span class="sxs-lookup"><span data-stu-id="173a6-146">There are many things to go do from here:</span></span> 
- <span data-ttu-id="173a6-147">Experimente diferentes decks de entrada predefinidos, por exemplo, variando o parâmetro `alpha` em `h4_sto6g_alpha.nw`,</span><span class="sxs-lookup"><span data-stu-id="173a6-147">Try out different predefined input decks, e.g., by varying the parameter `alpha` in `h4_sto6g_alpha.nw`,</span></span> 
- <span data-ttu-id="173a6-148">Tente modificar os decks editando diretamente os decks NWChem, por exemplo, explorando `STO-nG` modelos para várias escolhas de n,</span><span class="sxs-lookup"><span data-stu-id="173a6-148">Try modifying the decks by editing the NWChem decks directly, e.g., exploring `STO-nG` models for various choices of n,</span></span> 
- <span data-ttu-id="173a6-149">Experimente outros decks de entrada PRÉ-definidos da NWChem que estão disponíveis em `nwchem/qa/chem_library_tests`,</span><span class="sxs-lookup"><span data-stu-id="173a6-149">Try other predefined NWChem input decks that are available at `nwchem/qa/chem_library_tests`,</span></span>
- <span data-ttu-id="173a6-150">Experimente um conjunto de referências YAML de Broombridge pré-definidas que foram geradas a partir da NWChem e estão disponíveis como parte do [repositório Microsoft/Quantum](https://github.com/Microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML).</span><span class="sxs-lookup"><span data-stu-id="173a6-150">Try out a suite of predefined Broombridge YAML benchmarks that were generated from NWChem and are available as part of the [Microsoft/Quantum repository](https://github.com/Microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML).</span></span> <span data-ttu-id="173a6-151">Estes critérios incluem:</span><span class="sxs-lookup"><span data-stu-id="173a6-151">These benchmarks include:</span></span> 
    - <span data-ttu-id="173a6-152">pequenas moléculas como o hidrogénio molecular (H2), Beryllium (Be), o hidreto de lítio (LiH),</span><span class="sxs-lookup"><span data-stu-id="173a6-152">small molecules such as molecular hydrogen (H2), Beryllium (Be), Lithium hydride (LiH),</span></span>
    - <span data-ttu-id="173a6-153">moléculas maiores como o ozono (O3), beta-caroteno, citosina, e muito mais.</span><span class="sxs-lookup"><span data-stu-id="173a6-153">larger molecules such as ozone (O3), beta-carotene, cytosine, and many more.</span></span> 
- <span data-ttu-id="173a6-154">Experimente as [setas emslémicas](https://arrows.emsl.pnnl.gov/api/qsharp_chem) de ponta gráfica que possui uma interface para o Kit de Desenvolvimento Quântico da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="173a6-154">Try out the graphical front-end [EMSL Arrows](https://arrows.emsl.pnnl.gov/api/qsharp_chem) that features an interface to the Microsoft Quantum Development Kit.</span></span> 


## <a name="producing-broombridge-output-from-emsl-arrows"></a><span data-ttu-id="173a6-155">Produção de saída de Broombridge a partir de setas EMSL</span><span class="sxs-lookup"><span data-stu-id="173a6-155">Producing Broombridge Output from EMSL Arrows</span></span> ##

<span data-ttu-id="173a6-156">Para começar com as setas EMSL front-based web, navegue um navegador [aqui](https://arrows.emsl.pnnl.gov/api/qsharp_chem).</span><span class="sxs-lookup"><span data-stu-id="173a6-156">To get started with web-based front end EMSL Arrows, navigate a browser [here](https://arrows.emsl.pnnl.gov/api/qsharp_chem).</span></span> 

> [!NOTE]
> <span data-ttu-id="173a6-157">Executar setas EMSL num navegador web requer que o JavaScript seja ativado.</span><span class="sxs-lookup"><span data-stu-id="173a6-157">Running EMSL Arrows in a web browser requires JavaScript to be enabled.</span></span> <span data-ttu-id="173a6-158">Consulte estas [instruções](https://www.enable-javascript.com/) sobre como ativar o JavaScript no seu navegador.</span><span class="sxs-lookup"><span data-stu-id="173a6-158">Please refer to these [instructions](https://www.enable-javascript.com/) on how to enable JavaScript in your browser.</span></span> 

<span data-ttu-id="173a6-159">Primeiro, introduza uma molécula na caixa de consulta que diz ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.``</span><span class="sxs-lookup"><span data-stu-id="173a6-159">First, enter a molecule in the query box that says ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.``</span></span> 

<span data-ttu-id="173a6-160">Pode introduzir muitas moléculas pelo seu nome coloquial, como "cafeína" em vez de "1,3,7-Trimetilxantina".</span><span class="sxs-lookup"><span data-stu-id="173a6-160">You can enter many molecules by their colloquial name, such as "caffeine" instead of "1,3,7-Trimethylxanthine".</span></span> 

<span data-ttu-id="173a6-161">Em seguida, clique no botão que diz ``theory{qsharp_chem}``.</span><span class="sxs-lookup"><span data-stu-id="173a6-161">Next, click the button that says ``theory{qsharp_chem}``.</span></span> <span data-ttu-id="173a6-162">Isto irá povoar ainda mais a caixa de consulta com uma instrução que dirá a corrida para exportar a produção no formato Broombridge YAML.</span><span class="sxs-lookup"><span data-stu-id="173a6-162">This will populate the query box further with an instruction that will tell the run to export output in the Broombridge YAML format.</span></span> 

<span data-ttu-id="173a6-163">Agora, o relógio na ``Run Arrows``.</span><span class="sxs-lookup"><span data-stu-id="173a6-163">Now, clock on ``Run Arrows``.</span></span> <span data-ttu-id="173a6-164">Dependendo do tamanho da entrada, isto pode demorar um pouco.</span><span class="sxs-lookup"><span data-stu-id="173a6-164">Depending on the size of the input, this might take a while.</span></span> <span data-ttu-id="173a6-165">Ou, caso o modelo em particular já tenha sido calculado antes, pode ser feito extremamente rápido, uma vez que só será procurado numa base de dados.</span><span class="sxs-lookup"><span data-stu-id="173a6-165">Or, in case the particular model has already been computed before, it can be done extremely fast as it will only amount to a lookup in a database.</span></span> <span data-ttu-id="173a6-166">Em qualquer dos casos, você será levado para uma nova página que contém uma infinidade de informações sobre a execução particular de NWChem contra o deck especificado pela sua entrada.</span><span class="sxs-lookup"><span data-stu-id="173a6-166">In either case, you will be taken to a new page that contains a plethora of information about the particular run of NWChem against the deck specified by your input.</span></span> 

<span data-ttu-id="173a6-167">Pode descarregar e guardar o ficheiro Broombridge YAML da secção que começa com o seguinte cabeçalho:</span><span class="sxs-lookup"><span data-stu-id="173a6-167">You can download and save the Broombridge YAML file from the section that starts with the following header:</span></span> 
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

<span data-ttu-id="173a6-168">Clique em ``download``, que guarda uma cópia local com um nome de ficheiro único, como ``qsharp_chem48443.yaml`` (o nome em particular será diferente para cada execução).</span><span class="sxs-lookup"><span data-stu-id="173a6-168">Click on ``download``, which saves a local copy with a unique file name such as ``qsharp_chem48443.yaml`` (the particular name will be different for each run).</span></span> <span data-ttu-id="173a6-169">Em seguida, pode processar ainda mais este ficheiro como acima, por exemplo, com</span><span class="sxs-lookup"><span data-stu-id="173a6-169">You can then further process this file as above, e.g., with</span></span> 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
<span data-ttu-id="173a6-170">para obter contagens de recursos.</span><span class="sxs-lookup"><span data-stu-id="173a6-170">to get resource counts.</span></span> 

<span data-ttu-id="173a6-171">Você pode desfrutar do construtor de moléculas 3D que pode ser acedido a partir do separador ``Arrows Entry - 3D Builder`` na página de início de Setas EMSL.</span><span class="sxs-lookup"><span data-stu-id="173a6-171">You might enjoy the 3D molecule builder that can be accessed from the ``Arrows Entry - 3D Builder`` tab on the EMSL Arrows start page.</span></span> <span data-ttu-id="173a6-172">Clicar na imagem 3D de [JSMol](http://wiki.jmol.org/index.php/JSmol) da molécula mostrada permitirá que a edite.</span><span class="sxs-lookup"><span data-stu-id="173a6-172">Clicking the [JSMol](http://wiki.jmol.org/index.php/JSmol) 3D picture of the shown molecule will let you allow to edit it.</span></span> <span data-ttu-id="173a6-173">Pode mover átomos, arrastar átomos para que as suas distâncias intermoleculares mudem, adicione/remova átomos, etc. Para cada uma destas escolhas, uma vez adicionado``theory{qsharp_chem}`` na caixa de consulta, pode então gerar uma instância do esquema YAML de Broombridge e explorá-lo ainda mais usando a Biblioteca de Química Quântica.</span><span class="sxs-lookup"><span data-stu-id="173a6-173">You can move atoms around, drag atoms apart so that their inter-molecular distances change, add/remove atoms, etc. For each of these choices, once you added ``theory{qsharp_chem}`` in the query box, you can then generate an instance of the Broombridge YAML schema and further explore it using the Quantum Chemistry Library.</span></span> 
